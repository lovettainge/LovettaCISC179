def print_board(board):
    for row in board:
        print("|".join(row))
        print("-" * 5)

def check_winner(board):
    # Check rows
    for row in board:
        if all(cell == row[0] for cell in row if cell != ' '):
            return row[0]

    # Check columns
    for col in range(3):
        if all(row[col] == board[0][col] for row in board if row[col] != ' '):
            return board[0][col]

    # Check diagonals
    if board[0][0] == board[1][1] == board[2][2] != ' ':
        return board[0][0]
    if board[0][2] == board[1][1] == board[2][0] != ' ':
        return board[0][2]

    return None

def is_board_full(board):
    return all(cell != ' ' for row in board for cell in row)

def main():
    board = [[' ']*3 for _ in range(3)]
    current_player = 'X'

    print("Welcome to Tic Tac Toe!")

    while True:
        print_board(board)

        row = int(input(f"Player {current_player}, enter row (1-3): ")) - 1
        col = int(input(f"Player {current_player}, enter column (1-3): ")) - 1

        if board[row][col] != ' ':
            print("That cell is already taken. Try again.")
            continue

        board[row][col] = current_player

        winner = check_winner(board)
        if winner:
            print_board(board)
            print(f"Player {winner} wins!")
            break
        elif is_board_full(board):
            print_board(board)
            print("It's a tie!")
            break

        current_player = 'O' if current_player == 'X' else 'X'

if __name__ == "__main__":
    main()
