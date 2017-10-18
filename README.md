# DB-script-My-Movies
This is a DB-script for MySQL that I use in a YouTube video.


CREATE DATABASE My_Movies;

USE My_Movies;

CREATE TABLE `Movie` (
  `Title` VARCHAR(100),
  `MovieID` INT,
  `DurationMin` INT,
  `ReleaseYear` INT,
  `DirID` INT,
  `Genre` VARCHAR(50),
  `Format` VARCHAR(50),
  `CountryID` INT,
  PRIMARY KEY (`MovieID`),
  KEY `FK` (`DirID`, `CountryID`)
);

CREATE TABLE `Location` (
  `MovieID` INT,
  `Location` VARCHAR(50),
  KEY `FK` (`MovieID`)
);

CREATE TABLE `Country` (
  `ID` INT,
  `CountryName` VARCHAR(100),
  PRIMARY KEY (`ID`)
);

CREATE TABLE `ActorInMovie` (
  `MovieID` INT,
  `ActorID` INT,
  KEY `FK` (`MovieID`, `ActorID`)
);

CREATE TABLE `Actor` (
  `ID` INT,
  `FirstName` VARCHAR(100),
  `LastName` VARCHAR(100),
  `BirthYear` INT,
  `Gender` VARCHAR(30),
  PRIMARY KEY (`ID`)
);

CREATE TABLE `Director` (
  `ID` INT,
  `FirstName` VARCHAR(100),
  `LastName` VARCHAR(100),
  `BirthYear` INT,
  `Gender` VARCHAR(30),
  PRIMARY KEY (`ID`)
);


INSERT INTO Movie(Title, MovieID, DurationMin, ReleaseYear, DirID, Genre, Format, CountryID)
VALUES ('Titanic', '1', '195', '1997', '1', 'Romantic Drama', 'DVD', '1');

INSERT INTO Location(MovieID, Location)
VALUES ('1', 'Home');

INSERT INTO Director(ID, FirstName, LastName, BirthYear, Gender)
VALUES ('1', 'James', 'Cameron', '1954', 'Male');

INSERT INTO Country(ID, CountryName)
VALUES ('1', 'United States');

INSERT INTO ActorInMovie(MovieID, ActorID)
VALUES ('1', '1'),
				('1', '2'),
                ('1', '3');

INSERT INTO Actor(ID, FirstName, LastName, BirthYear, Gender)
VALUES ('1', 'Leonardo', 'DiCaprio', '1974', 'Male'),
				('2', 'Kate', 'Winslet', '1975', 'Female');
                

