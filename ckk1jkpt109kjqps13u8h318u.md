## Animated Typing Utility with JavaScript

Ever wished a animated typing effect in your webproject? If yes, you should definitive check out the typit.js library. Last days i stumbled upon that interesting library.

The effect looks like:

![(https://cdn.hashnode.com/res/hashnode/image/upload/v1610912272420/8mrlr5nqd.plain)

How could you implement it?

Let we say, you would like to use this effect to show others your different job experiences.

First place a tag inside your code like that one:

```
<p id="replaceJobs"></p>
```

Then create a `typeit.js` file with the content

```
new TypeIt('#replaceJobs', {
	strings: ["Job1", "Job2", "Job3"],
	speed: 200,
	cursorSpeed: 1000,
	nextStringDelay: 750,
	loop: true,
	breakLines: false,
	waitUntilVisible: true
}).go();
```

Now add the JavaScript to your Layout Section:

```
<script src="https://cdn.jsdelivr.net/npm/typeit@VERSION_NUMBER/dist/typeit.min.js"></script>
```

and refer your `typeit.js` to that page, where your "replaceJobs" tag is placed. Now your type effect will start :-)

More on: [https://typeitjs.com/](https://typeitjs.com/)
