class ChessGame:
    def __init__(self):
        self.board = self.initialize_board()
        self.current_player = "white"

    def initialize_board(self):
        board = [[" " for _ in range(8)] for _ in range(8)]
        # Initialize Pawns
        for i in range(8):
            board[1][i] = "P"
            board[6][i] = "p"
        # Initialize Rooks
        board[0][0], board[0][7] = "R", "R"
        board[7][0], board[7][7] = "r", "r"
        # Initialize Knights
        board[0][1], board[0][6] = "N", "N"
        board[7][1], board[7][6] = "n", "n"
        # Initialize Bishops
        board[0][2], board[0][5] = "B", "B"
        board[7][2], board[7][5] = "b", "b"
        # Initialize Queens
        board[0][3], board[7][3] = "Q", "q"
        # Initialize Kings
        board[0][4], board[7][4] = "K", "k"
        return board

    def print_board(self):
        for row in self.board:
            print(" ".join(row))

    def is_valid_move(self, start, end):
        # Implement chess move validation logic here
        pass

    def make_move(self, start, end):
        if self.is_valid_move(start, end):
            # Implement move execution logic here
            pass
        else:
            print("Invalid move!")

    def switch_player(self):
        self.current_player = "black" if self.current_player == "white" else "white"

    def play(self):
        while True:
            self.print_board()
            print(f"{self.current_player}'s turn.")
            start = input("Enter start position (e.g., 'a2'): ")
            end = input("Enter end position (e.g., 'a4'): ")
            self.make_move(start, end)
            self.switch_player()

if __name__ == "__main__":
    game = ChessGame()
    game.play()
