Canva Frontend Engineer Test Solution
--

I found this code on my computer and decided to post it to github for future reference. 
This was my first ever work with HTML canvas.

Canva didn't quite like my submission because it was too simple for them. They wanted to see more web worker magic and other fancy stuff. As I had to spend time learning HTML canvas, I didn't have much time left to make a super-performant and testable solution.
The only fancy thing in this submission is the use of promises to make it easier to work with batches of pixels asynchronously.

Hope you find this repo useful.


Photo mosaic
------------

The goal of this task is to implement the following flow in a client-side app.
1. A user selects a local image file.
2. The app loads that image, divides the image into tiles, computes the average
   color of each tile, fetches a tile from the server for that color, and
   composites the results into a photomosaic of the original image.
3. The composited photomosaic should be displayed according to the following
   constraints:
    - tiles should be rendered a complete row at a time (a user should never
      see a row with some completed tiles and some incomplete)
    - the mosaic should be rendered from the top row to the bottom row.
4. The client app should make effective use of parallelism and asynchrony.

The project skeleton contains a lightweight server (written in node) for
serving the client app and the tile images.  Install dependencies with
npm install, then run the server with npm start.  Those scripts assume a Mac
environment, but are trivial enough to replicate on Linux if required.
  /              serves mosaic.html
  /js/*          serves static resources
  /color/<hex>   serves a mosaic tile for color <hex>.  e.g., /color/0e4daa
The tile server generates tile images, and caches them in memory; subsequent
tile requests should be noticably faster.

The tile size should be configurable via the code constants in js/mosaic.js.
The project skeleton is already set up to include those constants in both the
mosaic client and the mosaic server.  The default size is 16x16.

You should:
 - pretend you're submitting this as production-quality code for review; i.e.,
   - write effective comments;
   - make the code modular;
   - make the code testable;
 - avoid using JS libraries (e.g., jQuery, Modernizr, React) as browser APIs
   are sufficient for the exercise and we're not testing for familiarity with
   any particular tools;
 - use HTML5 features where appropriate;
 - allocate about 3 hours to do the task.

You may:
 - edit /etc/hosts;
 - use any HTML5 feature supported by current Chrome (e.g., Promise, Worker);
 - be as creative as you like with the submission UI (file input, drag & drop,
   etc); however, it is not the focus of the task, a minimal UI is fine.

Have fun!