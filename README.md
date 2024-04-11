# Projeto Sistema de Jogo de Xadrez

# Sobre o projeto

Aplicar os conhecimentos aprendidos em programação Orientado a Objetos com java.


 
 
## Primeira classe: Cargo
 
### Checklist: 
- Class Position [public] 
- OOP Topics: 
- Encapsulation 
- Constructors 
- ToString (Object / overriding) 
 
 
 
 
## Come�ando a implementar Board and Piece
 
### Checklist: 
- Classes Piece, Board [public] 
- OOP Topics: 
       - Associations 
       - Encapsulation / Access Modifiers 
Data Structures Topics: 
       - Matrix 
 
 
## Camada de xadrez e impress�o do tabuleiro/placa
 
8 - - - - - - - - 
7 - - - - - - - - 
6 - - - - - - - - 
5 - - - - - - - - 
4 - - - - - - - - 
3 - - - - - - - - 
2 - - - - - - - - 
1 - - - - - - - -       
  a b c d e f g h 
 
### Checklist: 
- Methods: Board.Piece(row, column) and Board.Piece(position) 
- Enum Chess.Color 
- Class Chess.ChessPiece [public] 
- Class Chess.ChessMatch [public]  	
- Class ChessConsole.UI  	
- OOP Topics: 
- Enumerations 
- Encapsulation / Access Modifiers 
- Inheritance 
- Downcasting 
- Static members 
- Layers pattern 
- Data Structures Topics: 
- Matrix 
 
 
## Coloca��o de pe�as no tabuleiro
 
### Checklist: 
- Method: Board.PlacePiece(piece, position) 
- Classes: Rook, King [public] 
- Method: ChessMatch.InitialSetup 
- OOP Topics:
- Inheritance 
- Overriding 
- Polymorphism (ToString) 
 
 
## BoardException e programa��o defensiva
 
### Checklist: 
- Class BoardException [public] 
- Methods: Board.PositionExists, Board.ThereIsAPiece 
- Implement defensive programming in Board methods  
- OOP Topics: 
- Exceptions 
- Constructors (a string must be informed to the exception) 
 
 
## ChessException e ChessPosition
 
### Checklist: 
- Class ChessException [public] 
- Class ChessPosition [public] 
- Refactor ChessMatch.InitialSetup 
- OOP Topics: 
- Exceptions 
- Encapsulation 
- Constructors (a string must be informed to the exception) 
- Overriding 
- Static members 
- Layers pattern 
 
 
## Pouca melhoria na impress�o de placas
 
Color in terminal: 
- Windows: Git Bash 
- Mac: Google "osx terminal color" 
 
### Checklist: 
- Place more pieces on the board 
- Distinguish piece colors in UI.PrintPiece method 
 
 
## Pe�as m�veis
 
### Checklist: 
- Method Board.RemovePiece 
- Method UI.ReadChessPosition 
- Method ChessMatch.PerformChessMove 
- Method ChessMatch.MakeMove 
- Method ChessMatch.ValidadeSourcePosition 
- Write basic logic on Program.cs 
- OOP Topics: 
- Exceptions 
- Encapsulation 


## Manipulando exce��es e limpando a tela
 
Clear screen using Java / Limpar a tela para cada a��o nula ou jogada nova.
 
// https://stackoverflow.com/questions/2979383/java-clear-the-console 	
public static void clearScreen() {  
     System.out.print("\033[H\033[2J");       
     System.out.flush();   
}   
 
 
### Checklist: 
- ChessException 
- InputMismatchException 
 
 
 
 
 	 

## Poss�veis movimentos de uma pe�a
 
Imagens ilustrando tal movimento em um tabuleiro � Aplica��o � rodada via terminal

 
 
 
 
 
 
 
### Checklist: 
- Methods in Piece: 
- PossibleMoves [abstract] o 	PossibleMove 
- IsThereAnyPossibleMove 
- Basic PossibleMove implementation for Rook and King 
- Update ChessMatch.ValidadeSourcePosition 
 
- OOP Topics: 
- Abstract method / class 
- Implementando poss�veis movimentos de Rook Exceptions 
# Implementando poss�veis movimentos de Rook
 
### Checklist: 
- Method ChessPiece.IsThereOpponentPiece(position) [protected] 
- Implement Rook.PossibleMoves 
- Method ChessMatch.ValidateTargetPosition 
- OOP Topics: 
- Polymorphism 
- Encapsulation / access modifiers [protected] 
- Exceptions 
 
 
 
## Imprimindo poss�veis movimentos
 
### Checklist: 
- Method ChessMatch.PossibleMoves 
- Method UI.PrintBoard [overload] 
- Refactor main program logic 
- OOP Topics: 
- Overloading 
 
 
 
## Implementando poss�veis movimentos de King
 
### Checklist: 
- Method King.CanMove(position) [private]
-  Implement King.PossibleMoves
-  OOP Topics: 
- Encapsulation 
- Polymorphism 
 
 
 
## Troca de jogador a cada turno 

### Checklist: 
- Class ChessMatch
       - Properties Turn, CurrentPlayer [private set] 
       - Method NextTurn [private] 
       -  Update PerformChessMove 
       - Update ValidadeSourcePosition 
- Method UI.PrintMatch 
- Class ChessMatch
       - Encapsulation 
       - Exceptions 
 
 	 
## Manuseio de pe�as capturadas
 
### Checklist: 
- Method UI.PrintCapturedPieces 
- Update UI.PrintMatch 
- Update Program logic 
- Lists in ChessMatch: _piecesOnTheBoard, _capturedPieces 
- Update constructor 
- Update PlaceNewPiece 
- Update MakeMove 
-     OOP Topics: 
- Encapsulation 
- Constructors 
- Data Structures Topics: 
- List 
 	
 
 
## L�gica de check
 
Rules: 
- Check means your king is under threat by at least one opponent piece 
- You can't put yourself in check 
 
### Checklist: 
- Property ChessPiece.ChessPosition [get] 
- Class ChessMatch: 
- Method UndoMove 
- Property Check [private set] 
- Method Opponent [private] 
- Method King(color) [private] 
- Method TestCheck 
- Update PerformChessMove 
- Update UI.PrintMatch 
 
 
 
 
 
## L�gica de checkmate 

### Checklist: 
- Class ChessMatch: 
- PropertyCheckmate[privateset]
- MethodTestCheckmate[private] 
- Update PerformChessMove 
- Update UI.PrintMatch 
- Update Program logic 
 
 
 
## Contagem de movimentos de pe�as
 
### Checklist: 
- Class ChessPiece: 
   -  Property MoveCount [private set] 
   - Method IncreaseMoveCount [internal] 
   - Method DecreaseMoveCount [internal] 
- Class ChessMatch: 
- Update MakeMove 
- Update UndoMove 
- OOP Topics: 
   - Encapsulation 
 
 
## Pe�o
 
### Checklist: 
- Class Pawn 
- Update ChessMatch.InitialSetup
-  OOP Topics: 
-  Encapsulation 
-  Inheritance 
-  Polymorphism 
 
 
 
## Bispo
 
### Checklist: 
- Class Bishop 
- Update ChessMatch.InitialSetup 
- OOP Topics: 
-  Encapsulation 
-  Inheritance 
- Polymorphism 
 
 
 
### ## Cavalo 
 
Checklist: 
- Class Knight 
- Update ChessMatch.InitialSetup 
- OOP Topics: 
- Encapsulation 
- Inheritance 
- Polymorphism 
 
 
## Rainha
 
### Checklist: 
- Class Queen 
- Update ChessMatch.InitialSetup 
- OOP Topics: 
- Encapsulation 
- Inheritance 
- Polymorphism 
 
 
 
 
## Movimento especial - Roque
 
 
 
### Checklist: 
- Update King 
- Update ChessMatch.MakeMove 
- Update ChessMatch.UndoMove 
 
 
 
 	 
## Movimento especial - En Passant 
 
 
 
### Checklist: 
- Register a pawn which can be captured by en passant on next turn 
- Property ChessMatch.EnPassantVulnerable 
- Update ChessMatch.PerformChessMove 
- Update Pawn.PossibleMoves 
- Update ChessMatch.MakeMove 
- Update ChessMatch.UndoMove 
- Update ChessMatch.InitialSetup 
 
 
## Movimento especial - Promotion 
 
 
 
### Checklist: 
- Property ChessMatch.Promoted 
- Update ChessMatch.PerformChessMove 
- Method ChessMatch.ReplacePromotedPiece 
- Update Program logic 