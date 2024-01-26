## File cleaner
Read a file, remove all the extra spaces and write it back to the same file.

For example, if the file input was
```
hello     world    my    name   is       raman
```

After the program runs, the output should be

```
hello world my name is raman
```
Solution:

const fs = require("fs");

const content = fs.readFileSync("a.txt", "utf-8");

console.log("The file contains: " + content);

const mfdata = content.replace(/\s+/g, " ");

fs.writeFile("a.txt", mfdata, "utf-8", (err) => {
  if (err) {
    console.log(err);
  }
});

fs.readFile("a.txt", "utf-8", (err, data) => {
  if (err) {
    console.log(err);
  } else {
    console.log("The file contains after updating: " + data);
  }
});
s