Using `1-counter.md` or `2-counter.md` from the easy section, can you create a
clock that shows you the current machine time?

Can you make it so that it updates every second, and shows time in the following formats - 

 - HH:MM::SS (Eg. 13:45:23)

Solution:(bigger to understand different uses of option and date methods)

const { clear } = require("console");

const time = () => {
  const currentDate = new Date();
  const options = { timeZone: 'Asia/Kolkata' }; //Sets time zone(I am from kolkata!)

  //hour12:false ensures it keeps 24 hour format.

  let hours = currentDate.toLocaleString("en-IN",{hour: "numeric", hour12: false, ...options })
  let minutes = currentDate.toLocaleString("en-IN",{minute: "numeric", ...options })
  let seconds = currentDate.toLocaleString("en-IN",{second: "numeric", ...options })

  return {hours, minutes, seconds};
};

setInterval(() => {
  const {hours, minutes, seconds} = time(); //destructing the retunred object.
  console.clear();
  console.log(hours + ":", minutes + ":", seconds);
}, 2000);


 - HH:MM::SS AM/PM (Eg 01:45:23 PM)

Solution:(better one)

const { clear } = require("console");

setInterval(() => {
  const currentDate = new Date();
  const options = { timeZone: "Asia/Kolkata" }; //Sets time zone(I am from kolkata!)

  let data = currentDate.toLocaleString("en-IN", {
    hour: "numeric",
    minute: "2-digit",
    second: "2-digit",
    hour12: true,
    ...options,
  });
  console.clear();
  console.log(data);
}, 1000);
