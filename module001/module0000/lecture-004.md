Title: Java Part 4

# Title: Java

### Table of Contents

| Sr No. | Question                                                                                                                                            |
| ------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0      | [How to clear buffer after processing small portion of the large file?](https://jcoding09.github.io/interviewprep/module001/module0000/lecture-004) |

## \*. How to clear buffer after processing small portion of the large file (also add CSV to JSON logic)?

To convert a large CSV file to JSON while processing it in small chunks to avoid memory issues, you can follow a similar approach. You'll read the CSV file line by line, convert each line to a JSON object, and then write the JSON object to a file incrementally.

Here is an example of how you can do this in Java:

```java
import java.io.*;
import org.json.JSONObject;

public class CsvToJsonConverter {

    public static void main(String[] args) {
        String inputFilePath = "path/to/large/input/file.csv";
        String outputFilePath = "path/to/output/file.json";

        convertCsvToJson(inputFilePath, outputFilePath);
    }

    public static void convertCsvToJson(String inputFilePath, String outputFilePath) {
        try (BufferedReader reader = new BufferedReader(new FileReader(inputFilePath));
             BufferedWriter writer = new BufferedWriter(new FileWriter(outputFilePath, true))) { // true for append mode

            String line;
            String[] headers = reader.readLine().split(","); // Assuming first line contains headers

            writer.write("["); // Start of JSON array
            writer.newLine();

            boolean firstLine = true;
            while ((line = reader.readLine()) != null) {
                if (!firstLine) {
                    writer.write(","); // Add a comma between JSON objects
                    writer.newLine();
                }
                String[] values = line.split(",");
                JSONObject jsonObject = new JSONObject();

                for (int i = 0; i < headers.length; i++) {
                    jsonObject.put(headers[i], values[i]);
                }

                writer.write(jsonObject.toString());
                firstLine = false;

                // Flush the writer to clear the buffer
                writer.flush();
            }

            writer.newLine();
            writer.write("]"); // End of JSON array
            writer.newLine();

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Key Points:

1. **BufferedReader**: Used to read the CSV file line by line to avoid loading the entire file into memory.
2. **BufferedWriter**: Used to write the JSON objects to the output file incrementally in append mode.
3. **Flush the Buffer**: `writer.flush()` is called after writing each JSON object to ensure that the buffer is cleared and data is written to the file.
4. **JSON Conversion**: The `org.json.JSONObject` class is used to create JSON objects from CSV lines.

This approach ensures that the entire CSV file is not loaded into memory, preventing memory issues while processing large files.
