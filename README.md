# Movies Recommendation System

## How to run

Just open the browser, search movies, and rate at least 2 movies. <br />
Calculate button will propose movies based on Pearson correlation coefficient.

## Basic Implementation

User is able to search a movie only by typing alphanumerical. Only english letters and non-special characters are
allowed.<br />
User must type at least 3 characters.<br />
User must rate at least 2 movies and maximum 5 movies.<br />
User is able to re-rate the same movies but not more than 5. In case user tries to rate a 6th movie, an alert message
will be appeared in the screen.<br />
Calculation button once is clicked, it gets disabled. Need to re-rate to be enabled again.<br />
In order for the algorithm to recommend movies, there must be users that have been scored with >= 0.7 pearson.<br />
If none filtered user found with more than 0.7 pearson, alert message will be appeared in the screen.<br />

## Pearson Implementation

1. Retrieve the rating dataset from the external API.<br />
2. Push every nested array to one array that contains all movie ratings.<br />
3. Sort userId by ASC order.<br />
4. Create a map of userId and count (rating) from this sorted array in this format: --> userId: count(rating)<br />
5. Keeping 5.000 unique userIds of those who have been rated the same or -1 from the total size.<br />
6. Keeping only the duplicate userIds, because the user must rate at least 2 movies.<br />
7. Creating custom object: userId: { movieRating: [{movieId: rating}] }.<br />
8. Using reduce function in the arrayOfUserMovieRatedFromInput to have this format: movieId: rating.<br />
9. Comparing the whole dataset with my review ('geokall') and with every compared user while keeping recommended movies
   from
   maximum 5 users.<br />
10. Show alert in case none filtered users, fetched with more than 0.7 pearson score.<br />
11. For every pearson score that is > 0.7, 3 random movies are selected.<br />
12. Getting movie information and show the table with these movies.<br />

## Credits

Below you can find all the credits I'd like to give. <br />
[https://www.digitalvidya.com/blog/collaborative-filtering/](https://www.digitalvidya.com/blog/collaborative-filtering/) <br/>
[https://becominghuman.ai/introduction-to-recommendation-system-in-javascript-74209c7ff2f7](https://becominghuman.ai/introduction-to-recommendation-system-in-javascript-74209c7ff2f7) <br/>
[https://stackoverflow.com/questions/1069666/sorting-object-property-by-values](https://stackoverflow.com/questions/1069666/sorting-object-property-by-values) <br/>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) <br/>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) <br/>
[https://coderedirect.com/questions/547235/await-with-array-foreach-containing-async-await](https://coderedirect.com/questions/547235/await-with-array-foreach-containing-async-await) <br/>
[https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await) <br/>
[https://stackoverflow.com/questions/4550505/getting-a-random-value-from-a-javascript-array](https://stackoverflow.com/questions/4550505/getting-a-random-value-from-a-javascript-array) <br/>
[https://stackoverflow.com/questions/15148659/how-can-i-use-queryselector-on-to-pick-an-input-element-by-name](https://stackoverflow.com/questions/15148659/how-can-i-use-queryselector-on-to-pick-an-input-element-by-name) <br/>
[https://stackoverflow.com/questions/7271490/delete-all-rows-in-an-html-table](https://stackoverflow.com/questions/7271490/delete-all-rows-in-an-html-table) <br/>
