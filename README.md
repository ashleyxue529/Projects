Projects
========

Senior year Computer Systems Lab research project

!!It is currently only connected to my personal computer, not the school server, so components of it don't successfully load on the website!!


OVERVIEW: I made a website that people can visit to practice their endgame tactics. For those of you who don’t play chess, an endgame is the final stage of a chess game when there are relatively few pieces left on the board. Each move you make is critical. Even if you’re originally winning, you could possibly lose because of a minor error you make. 
How this website helps people learn is that first, it provides hints for the user rather than simply giving the answer. This allows the user to think the problem through more carefully. Second, the website gives the user progressively harder problems to solve, which helps the user gradually improve over time. 

WEBSITE OVERVIEW: The web interface consist of a general layout, a chess board and two buttons. These two buttons access information from the database and output it onto the chessboard. The "Get a Position" button lets the user start the game by pulling out the easiest position to solve in the database. The position is represented by a string in fen notation, which stands for Forsyth Edwards Notation. This notation is a widely used format by the chess community when you want to know the orientation of the board. The "Need Help?" button gives the player a hint for the problem. 
To solve the problem, the user can simply click and drag. If you make the correct move, the code accesses the database and pulls out the corresponding response or a window will pop up saying, “Good job!” and the database will give you a harder problem to solve. If you are unable to solve it, a window will pop up saying, “Sorry, try an easier one!” and the database will give you an easier problem.

DIFFICULTY: The difficulty of a problem is determined by the number of times it has been gotten wrong before. So a position that has been gotten wrong 10 times would be harder than a position that has been gotten wrong 4 times. The number of times a problem has been incorrectly solved is kept track of in the database. 

DATABASE: There is a MySQL database connected to my website. It has a table called pos that contains 6 columns labeled: id, position, solution, response, difficulty, and hint. ID is a reference number used when retrieving the positions to display on the website. Position is the FEN representation of the problem position. Solution, which is also represented in FEN notation, contains the correct moves White should make in order to correctly solve the position. Response contains the sequence of moves that black plays in response to White’s moves. The difficulty column contains the number of times the position has been solved incorrectly. As I explained before, the higher the number it has in this column, the harder the position is to solve. Basically, the harder it is, the more likely it is for people to solve it incorrectly, which is why the number is higher. The hint column contains a brief hint to help solve the position. 
