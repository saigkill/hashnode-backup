## Adding a estimated time to read to a .NET Core Blog with Razor

This week i implemented a feature what shows you, how many time you have to spend, to read a blog article. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1610912171513/3nMbRagan.html)

In the first step, i used my model BlogStory to get the content. Then Razor does the following:

1. It counts the spaces between the words and adds 1. So now we knowing how many words we have in that article.
2. The most people can read 200 to 250 in one minute. So we need to divide the counted words with 250. Then we knowing, how many minutes it takes to read.
3. Then we combine a modulo with a divide to get the seconds.

```
@{
    var word_count = @Model.Body;
    var counts = word_count.Count(ch => ch == ' ') + 1;    
    var minutes = counts / 250;
    var seconds = counts % 250 / (250 / 60);
    var str_minutes = (minutes == 1) ? "Minute " : "Minutes ";
    var str_seconds = (seconds == 1) ? "Second " : "Seconds ";    
}
```

Now we placing the code for displaying the estimated time to read

```
<i class="fas fa-clock"></i> @minutes @str_minutes  @seconds @str_seconds
```

On the place, where this snipped is, will be the estimated time to read.

Currently it is placed on client side. It is planned to move that function to server side in future.

[![Creative Commons License](https://cdn.hashnode.com/res/hashnode/image/upload/v1610912173356/7x_z3_BsQ.png)](https://creativecommons.org/licenses/by-sa/3.0/de/deed.en)

 This work by [Sascha Manns](https://saschamanns.de) is licensed under a [Attribution-ShareAlike 3.0 Germany License (CC BY-SA 3.0 DE)](https://creativecommons.org/licenses/by-sa/3.0/de/deed.en/).  
 Based on a work at [saschamanns.de](https://saschamanns.de).