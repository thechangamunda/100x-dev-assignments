## Write to a file
Using the fs library again, try to write to the contents of a file.
You can use the fs library to as a black box, the goal is to understand async tasks.

Solution:

//make a file a.txt

const fs = require("fs");

const content = " boombaclatttttt!!";

//Overwrites the file
fs.writeFile("a.txt", content, (err) => {
  if(err){ 
    console.log(err);
  }
});

//Appends(adds) to the existing file.
fs.appendFile("a.txt", content, (err) => {
  if(err){ 
    console.log(err);
  }
});
  
fs.readFile("a.txt", "utf-8", (err, data) => {
  console.log(data);
});