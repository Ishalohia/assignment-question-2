The provided repository code consists of two main parts: A highlightHTMLContent.js file for a JavaScript function named highlightHTMLContent and a Jest test case  file highlightHTMLContent.test.js that tests the functionality of this function. 

## highlightHTMLContent Function Explanation:

This code defines a function named highlightHTMLContent that takes three arguments: htmlContent (the HTML content to be modified), plainText (the corresponding plain text of the HTML content), and plainTextPositions (an array of objects specifying the positions to be highlighted in the plain text)

1- A helper function named escapeHTML is defined within the highlightHTMLContent function. This function is used to escape HTML special characters (&, <, >, etc.) by replacing them with their corresponding HTML entities. This is essential to avoid unintentional HTML interpretation.

2- An empty array named highlightedSegments is initialized. This array will be used to store information about the segments of HTML content that need to be highlighted.

3- A loop is initiated to iterate through each object in the plainTextPositions array. Each object represents a start and end position in the plain text that needs to be highlighted.
Inside the loop, the code extracts the corresponding segment of plain text based on the start and end positions from the plainText string.

4- The code then searches for the extracted plain text segment within the htmlContent using the indexOf method. This determines the start and end positions of the segment in the HTML content.

5- Using the found htmlStart and htmlEnd positions, the code extracts the segment from the htmlContent and wraps it in a <mark> element, creating the highlighted HTML segment. The highlighted segment information, including htmlStart, htmlEnd, and highlightedSegment, is added to the highlightedSegments array.

6-  After looping through all plainTextPositions, the highlightedSegments array is sorted in descending order based on the htmlStart positions. This is done to ensure that we insert the highlighted segments from the end to the beginning, preventing interference with other positions.

7- Another loop iterates through the sorted highlightedSegments array. For each segment, the original htmlContent is modified by inserting the highlightedSegment at the appropriate htmlStart position and removing the corresponding characters until htmlEnd.

8- After all highlighted segments have been inserted, the function returns the modified htmlContent.

9- An example usage is provided at the end of the code. The htmlContent, plainText, and plainTextPositions are defined, and the highlightHTMLContent function is called with these values to generate highlighted HTML content. The modified HTML is then logged to the console.


<img width="845" alt="Screenshot 2023-08-06 at 6 06 38 PM" src="https://github.com/Ishalohia/assignment-question-2/assets/104261885/887a6bf5-59c1-42ce-b162-ca482de1a059">


## Jest test case file Exaplaination

This Jest test case is responsible for testing the functionality of the highlightHTMLContent function. It imports the function from the module, defines a helper function removeHTMLTags to remove HTML tags from a string, and then sets up a test scenario using the provided HTML content, plain text, and positions to be highlighted. The expected output after highlighting is also defined.

The test case then calls the highlightHTMLContent function with the provided data, captures the received output, and compares it with the expected output. If the two outputs match after removing HTML tags, the test case will pass; otherwise, it will fail.

