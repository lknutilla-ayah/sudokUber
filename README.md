<h2>Overview:</h2> 
<p>SudokUber is a sudoku puzzle generator web-app. Sudoku is a number placement puzzle where users place numbers 1-9 in a 9x9 board. Each 3x3 block, row, and col contains numbers 1-9, without duplicates.</p> 
</br>
<h2>Structure:</h2></br>
  <h4>index.html:</h4>
  <ul>
    <li>includes: style.css and scripts.js</li>
    <li>User Interaction:</li> 
    <ul>
      <li>Buttons:</li> 
        <ul>
          <li>"New Game": creates puzzle and begins timer</li>
          <li>"Done!": checks board and returns an alert on whether the board is valid or not. If valid, the timer is stopped. </li>
        </ul>
      <li>Board:</li>
          <ul>
            <li>The user may enter numbers 1-9 on any open cell. If the user inputs an invalid entry, when the user clicks off the cell (onBlur), SudokUber will send an alert if the entry is not 1-9, or will turn the matching invalid cells red. Pre-filled cells are read-only.</li>
          </ul>
        </ul>
      <li>Decisions and Trade-offs:</li>
        <ul>
          <li>SudokUber works with latest Firefox/Chrome and IE10. This decision was made to improve user experience and capability of SudokUber.</li>
        </ul>
    </ul>
</br>
  <h4>scripts.js:</h4>
    <ul>
      <li>On page load, SudokuUber creates the blank framework for the board</li>
        <ul>Functions called: createSudoku()</ul>
      <li>On "New Game", SudokUber creates a unique complete board, then hides cells in order to create the puzzle. This is done by filling the board with a complete base sudoku board, then scrambling the rows/cols/and numbers and hiding the cells. The algorithm is based on the sudoku generator by David J. Rager at http://blog.fourthwoods.com/2011/02/05/sudoku-in-javascript/.</li>
        <ul>Functions called: fillBoard()->hideCells()</ul>
      <li>On "New Game", the timer begins</li>
        <ul>Functions called: startClock();</ul>
      <li>On cell entry blur, SudokUber validates that the new entry is 1-9, and is not the same as any entry in it's row, col, or block.</li>
        <ul>Functions called: checkValid()</ul>
      <li>On "Done!", SudokUber checks all cells if valid, and stops the timer if valid.</li>
        <ul>Functions called: checkBoard()->checkValid()</ul>
      <li>Decisions and Trade-offs:</li>
        <ul>
        <li>Originally, I implemented an algorithm for creating boards using backtracking, this proved too long and so the scrambling board algorithm was implemented. Upon further refinement, the backtracking algorithm could be used, but the scrammbling algorithm was faster to implement and executes faster.</li>
        <li>A naiive algorithm for hiding cells was used due to lack of time. It will normally create a unique board, but because this is not guaranteed the algorithm will need future modifications.</li>
        </ul>
      </ul>
  

  <h4>style.css:</h4>
    <ul>
      <li>Font: Raleway</li>
      <li>Colors:</li>
        <ul>
            <li>$blue: #B8DBFF; //for sidebar and puzzle</li>
            <li>$dark-grey: #E6E6E6; //for separating blocks</li>
            <li>$light-blue: #E6F3FF; //for background</li>
        </ul>
      <li>Desktop vs. Phone/Tablet:</li>
        <ul>
          <li>Desktop: sidebar and puzzle are side-by-side</li>
          <li>Tablet (780px): sidebar is above puzzle and puzzle cells shrink to 1.5em</li>
          <li>Phone (480px): sidebar is above puzzle and puzzle cells shrink to 1em</li>
        </ul>
      <li>Decisions and Trade-offs:</li>
      <ul>SASS was used to increase ease of use, and improve readability of code</ul>
</br>      
<h2>Technology:</h2>
  <ul>
  <li>index.html: HTML5</li>
  <li>scripts.js: Javascript</li>
  <li>style.css: CSS3, SASS</li>
  </ul>
</br>
<h2>Improvements:</h2>
  <ul>
  <li>UI:</li>
    <ul>
    <li>Add annotation capability so that users can mark potential numbers for a cell</li>
    <li>Improve look and feel of UI by animating the board creation (ex. cells flip during puzzle creation)</li>
    <li>Further browser testing is necessary for phone and tablet</li>
    </ul>
  <li>Functionality:</li>
    <ul>
    <li>Allow for user to input differing skill levels</li>
    <li>Modify validity check to automatically terminate/ send congatulations alert when puzzle is complete</li>
    <li>Modify cell hiding function to difinitivly create unique boards</li>
    </ul>
  </ul>


