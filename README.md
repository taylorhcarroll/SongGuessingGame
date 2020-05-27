# SongGuessingGame
## About
Song guessing Game. Users will be able to select by genre and be given a song to listen to.
Pending on difficulty may be given multiple choice answers or have to free-text the answer.
May earn and use hints per game
Game will have number of round to guess.
Users will receive score based on correct answer, number of incorrect guesses, and time left on clock.


## ERD

table users {
  id int
  picURL varchar
  username varchar
  name varchar
  email varchar
}

table Game { 
  id int
  Rounds int
  Genre varchar
  WinnerId varchar
}

table GameUsers {
  id int
  userID varchar
  gameId int
}

table GameRounds {
  id int
  GameId int
  SongId varchar
  
}

table friends {
  id int
  userId int
  friendId int
}

Ref: "users"."id" < "friends"."userId"

Ref: "friends"."friendId" < "users"."id"

Ref: "GameUsers"."userID" < "users"."id"

Ref: "GameUsers"."gameId" < "Game"."id"

Ref: "GameRounds"."GameId" < "Game"."id"

## Tech to be Used
SQL database
Spotify API
C# backend
React FrontEnd
