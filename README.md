# swe-sr-1-2

## Setup

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/how-tos/working-with-assignments#how-to-work-on-assignments).

Here are some useful commands to remember.

```sh
npm i                   # install dependencies
git checkout -b draft   # switch to the draft branch before starting

git add -A              # add a changed file to the staging area
git commit -m 'message' # create a commit with the changes
git push                # push the new commit to the remote repo
```

## Prompt

You are building an app and have to store data about user profiles. Each user profile is represented by an Object with an `id`, `username` and `password`. Below you will find two ways of grouping together these user objects, an array of objects and an object of objects:

```js
const usersArray = [
  {
    id: 214,
    username: "Spongebob",
    password: "dandelion",
  },
  {
    id: 592,
    username: "Squidward",
    password: "clarinet",
  },
  {
    id: 723,
    username: "Patrick",
    password: "whoareyoupeople???",
  },
];

const usersObject = {
  Spongebob: {
    id: 214,
    username: "Spongebob",
    password: "dandelion",
  },
  Squidward: {
    id: 592,
    username: "Squidward",
    password: "clarinet",
  },
  Patrick: {
    id: 723,
    username: "Patrick",
    password: "whoareyoupeople???",
  },
};
```

Compare and contrast these two options. Which would _you_ choose and why? What are the tradeoffs of each container? Consider how the container you choose makes it easy / difficult to find a user, to iterate through the users, etc...

### Response

As to finding a _specific user_, I would choose the `usersObject`, but for _iterating_ through users, I would prefer to use `usersArray`, just because I’m more used to using array methods to loop through data.

Finding a specific user in `usersObject` would involve checking if the `username` exists using an `if statement` (for example, `if (usersObject['Spongebob'])`) to make sure the key is found without accidentally adding a new property. In contrast, with `usersArray`, a user would have to be found by checking through each element in the array, accessing each object’s username key, and either using an `if statement` to compare the value or using methods like `.find()` or `.filter()`.

The advantage of `usersArray` is that we can use various array methods to iterate according to our needs. On the other hand, `usersObject` makes it faster and easier to look up a specific user and also has its own object methods, I'm just personally not as familiar with them.

Arrays are generally preferred when **the order of elements matters**, but in this case, the order of users isn’t important for either finding or iterating through them. Therefore, using an object would be ideal for **finding a user**, while I would personally prefer to use an array when **iterating** through the users.
