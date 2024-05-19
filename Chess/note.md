# Overview
    the system consist of 3 main components:
    - client app: 
        it can be web application, mobile app
        it provides the user interface to interact with the game
        it handles rendering the chessboard, moves, and user input
    - Server: 
        it manage game state
        it enforces the game rules
        it facilitates communication between the clients
        it validates the moves, track the state of the game & ensures fair play
    - database:
        it stores game data, including [player profiels, ongoing game states & move history]
        it provides persistence and allows players to resume games
    
# Game logic / Game store:
    it gandles the rules and mechanics of chess
    - board representation:
        a 2D array that stores the position and state of each piece
        each piece have attributes like type, color and position
    - validating moves:
        the validation should base on the current game state, pieve types and rules
        handle checks, checkmates, castling, pawn promotion and other special moves
    - check detection:
        the game logic should detect when a player's king is under threat
    - game termination:
        the game logic should determine when the game is over, 
        either due to checkmate, stalemate, draw conditions or player resignation

# User interface:
    it should provide an intuitive adn responsive experience to players
    - chessboard representation:
        the client app should render the chessboard, diplaying the position and state of each piece
    - move input:
        players should be able to select a pieve and a target position to make a move
        the interface could provide visual cues for valid moves and handle move submission
    - game notifications:
        the interface should display game-related notifications: [check, checkmate, stalemate etc.]

# Server:
    server handles game synchronization, validation, and communication between clients
    - API endpoints:
        it expose APIs to handle client requests, such as 
            [creating new game, making moves, retrieving game state and handling resignation]
    - game manager:
        it manages game instances, store game state, and handle game-related operations like 
            [validating moves, determining game outcomes]
    - websocket / long polling
        it enables real-time communication, the server can use tech to push udpates to clients whenever game state changes

# Communication protocal:
    it facilitates communication between the client and the server.
    it should support rea-time updates, and handle move requests, game state updates and error handling
    websocket can be used to establish a bidirectional communication channel between the client server

# Database:
    it stores game-related data to provide persistence and support game resumption
    it gandles player profiles, ongoing game states, move history, and other info
    commonly used db for this purpose include SQL database(MySQL, PostgreSQL) or NoSQL database(MongoDB)

