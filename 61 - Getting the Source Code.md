##Getting the Source Code

In this section (and in the next sections as well) you would need to use Github repository[https://github.com/vp-online-courses/webpack-tutorial] associated with this course.
We'll use the source code from `starting-point-for-use-cases` branch as a starting point.

Let me show you how you can get the source code:

1. First, you need to clone the Github repository.

```
git clone https://github.com/vp-online-courses/webpack-tutorial.git
cd webpack-tutorial
```

2. Second, you need to checkout the branch `starting-point-for-use-cases`.

```
git checkout -b starting-point-for-use-cases remotes/origin/starting-point-for-use-cases
```

3. Finally, you need to install the project dependencies after switching to the new branch.

```
rm -rf node_modules
npm install
```
Now you are ready to start with this section.



P. S. You would need to repeat these steps every time you start one of the following sections:

1. Integration with jQuery.

2. Using ESLint.
