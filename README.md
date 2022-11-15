# 2211-GHP-Students

# Lab/ Workshop Code and Solutions

Not all have solution code - some have built-in hints and answers on the Canvas page.

Please get as far as you can with each before looking at answer code.

### Week 1

- Day 1 (No solutions for these)
    
    
    | Git Lab | Vanilla DOM: Practicing Git |  |
    | --- | --- | --- |
    | Git Workshop | Vanilla DOM: Git Workflow | Starter Code |
- Day 2
    
    
    | CSS Drill Lab | Lab in Canvas | Solution Code |  |  |
    | --- | --- | --- | --- | --- |
    |  Landing Page Liftoff | Workshop Page | Starter Code | Solution Code | Solution Video |
- Day 3
    
    
    | Assistive Tooling | Lab Page |  |  |
    | --- | --- | --- | --- |
    | Practical Debugging | Workshop Page | Starter Code |  |
    | Manipulating the DOM | Lab Page |  | Solution - See Below |
       
       <details>
<summary>Manipulating the DOM Lab Walkthrough</summary>

```
  // To be run in console @ [https://en.wikipedia.org/wiki/Document_Object_Model](https://en.wikipedia.org/wiki/Document_Object_Model)
        
        /*
        I use the elements tab to find the main title of the article:
        <h1 id="firstHeading" class="firstHeading">Document Object Model</h1>
        which I select and style like this:
        */
        const mainTitle = document.querySelector("#firstHeading"); // Using the id.
        mainTitle.style.color = "red"; // The text is now red!
        
        /*
        Extra Challenges
        */
        
        // -----------------------------------------------------
        
        // Turn every <p> node's text green
        const allParagraphElements = document.querySelectorAll("p"); // Select all <p>.
        const asArray = Array.from(allParagraphElements); // Turn that array-like object in to a REAL array.
        asArray.forEach(pElement => { // Loop through ...
        pElement.style.color = "green"; // ... update the inline CSS style for each element to have color:green;
        });
        
        // -----------------------------------------------------
        
        // Change every <a> node so that it will link to the page for Star Wars.
        const allLinkElements = Array.from(document.querySelectorAll("a")); // Combining some steps from previous example.
        allLinkElements.forEach(a => {
        a.href = "[https://en.wikipedia.org/wiki/Star_Wars](https://en.wikipedia.org/wiki/Star_Wars)"; // Setting the "href" attribute of each <a>.
        });
        
        // -----------------------------------------------------
        
        // Make the page much cuter by replacing the main picture in the article with a picture of a puppy.
        
        // This image does not have its own ID or class, so this is the most reliable way of selecting I could find.
        // There is a <td> element it has as a parent that has the class .infobox-image,
        // I use that and ask for the <img> element found as a descendant.
        const mainImage = document.querySelector(".infobox-image img");
        // Update the <img src> attribute.
        mainImage.src = "[https://learndotresources.s3.amazonaws.com/workshop/5a7b63826759b0000495a518/dom-cody.png](https://learndotresources.s3.amazonaws.com/workshop/5a7b63826759b0000495a518/dom-cody.png)";
        
        // -----------------------------------------------------
        
        /*
        Extra challenging!
        
        ```
        Write a function that will search the DOM tree recursively for all instances of the term "DOM",
        and replace it with the term "KITTEN".
        
        ```
        
        - /
        
        // This recursive function will first be called with the body element/node of the page, and recursive visit child nodes.
        const replaceTextAndLookAtChildren = (domNode) => {
        
        ```
        // While not an element, text nodes on the page are tree nodes that contain the text content of an element.
        // For example: <h1>Hi!</h1> is actually not just one node, but two: the h1, and a childNode with the name "#text" that contains "Hi!"
        // This strategy may be confusing, but is the easiest what I can make sure that I'm only updating text, and not other attributes,
        // like href's on links. This would be an issue when using .innerHTML.
        if (domNode.nodeName === "#text") {
            domNode.textContent = domNode.textContent.replaceAll("DOM", "Kitten");
        }
        
        // After seeing if this node is a text node and possibly updating its content,
        // I access the child nodes of this node with .childNodes and then turn it into an array.
        const thisElementsChildNodes = Array.from(domNode.childNodes);
        
        thisElementsChildNodes.forEach(childNode => { // I loop over that array ...
            replaceTextAndLookAtChildren(childNode); // ... and recursively call this function, which allows me to traverse the whole tree.
        });
        
        ```
        
        };
        
        // I start my recursive traversal at the top node of the visual page, and let the recursive calls eventually visit every node on the page.
        replaceTextAndLookAtChildren(document.body);
```
</details>
        
    
    Day 3 Bonus Lab (Optional)
    
    | Selector Workshop | Canvas Page | Starter Code | Solution Video |
    | --- | --- | --- | --- |
    
    
- Day 4
    
    
    | Whack-A-Mole |  Lab Page | Starter Code |  |  |
    | --- | --- | --- | --- | --- |
    | Pixelate | Workshop Page | Starter Code | Solution Code | Solution Videos |
    | Node Basics  | Lab Page |  | Solution Code |  |
    | Node Shell | Workshop Page |  | Solution Code |  |
- Week 1 Checkpoint
    
    DOMCheckpoint ([Coffee Clicker](https://github.com/FullstackAcademy/Checkpoint.DOM)) | [Solution](https://github.com/FullstackAcademy/Checkpoint.DOM.Solution) | [Video](https://youtu.be/3EtAyIhudF0)
    

### Week 2

- Day 5
    
    
    | Express First Contact | Lab Page |  |  |  |
    | --- | --- | --- | --- | --- |
    | Async Await Lab | Lab Page | Starter Code | Solution Code |  |
    | Wizard News 1 | Workshop Page | Starter Code | Solution Code | Review / Solution Video |
- Day 6
