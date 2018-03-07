# hotel-mangment
lab project
create database labproj1
create table roomType9 (
typeId int not null primary key,
price int not null,
persons int not null,
);
create table room9(
id int not null primary key ,
roomTypeID int not null,
status varchar(12) not null, -- availiability status
foreign key (roomTypeId) references roomType9(typeID),
);
create table customer9 (
 id int not null primary key,
 phoneNo int,
 address varchar(40) ,
 cnicNO char(15) not null ,
 password varchar(20) not null,
 gender varchar(7) not null,
 regDate date not null,
 BirthDate date ,
 reservationDate date ,
 reservationTime time,
 regTime time,
 roomNo int not null,
 foreign key (roomNO) references room9(id),
);


create table payment9 ( 
--bookingId int not null,
Id int not null,
amount int not null,
status varchar(15) not null,
foreign key (ID) references customer9(id),
);
create table facilities9 (
facId int not null primary key,
price int not null,
name varchar(20) not null,
);
create table facilityCust9(
customerId int not null,
facid int not null,
foreign key (facId) references facilities9(facId),
foreign key (customerId) references customer9(id),
);
create table discounts9 ( 
discountID int not null,
name varchar(15) not null,
discountPercent int ,
);
create table employee9(
type varchar(30) not null,
EmployeeID int not null primary key,
phoneNo int not null,
address varchar(40) not null,
cnicNo char(15) not null,
BirthDate date,
);
create table food9(
id int not null primary key,
name varchar(30) not null,
price int not null,
type varchar(10),
);
create table foodBill9 (
customerId int not null ,
foodId int not null ,
foreign key (foodId) references food9(id),
foreign key (customerid) references customer9(id), 
);
create table bonusCal9(
id int not null primary key,
detail varchar(30) not null,
percentage int not null,
);
create table bonusLink(
usingid int not null,
bonusid int not null,
foreign key (bonusId) references bonusCal9(id),
foreign key (usingId) references customer9(id),
foreign key (usingId) references employee9(employeeid),
);










