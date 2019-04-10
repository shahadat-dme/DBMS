# DBMS
Database Management System Project : Flower Shop
drop table store cascade constraints;
drop table employee cascade constraints;
drop table items cascade constraints;
drop table proprietor;
drop table customer;
drop table transport cascade constraints;
drop table transfer;

create table proprietor(prop_id varchar (30) not null,
	name varchar(30),
	city varchar(30),
	state varchar(30),
	phone number(30),
    primary key(prop_id));


create table store(st_id varchar(30) not null,
prop1_id varchar(30),
name varchar(30),
address varchar(30),
primary key(st_id),
foreign key(prop1_id) references proprietor(prop_id) on delete cascade);



create table employee(emp_id varchar(30),
prop2_id varchar(30),	
emp_name varchar(27),
emp_city varchar(27),
emp_country varchar(27),
primary key(emp_id),
foreign key(prop2_id) references proprietor(prop_id) on delete cascade);


create table customer(cust_id varchar(30),
emp1_id varchar(30),	
cust_name varchar(30),
phone number(30),
cust_city varchar(30),
primary key(cust_id),
foreign key(emp1_id) references employee(emp_id) on delete cascade);

create table items(item_id varchar(30),
prop3_id varchar(30),
cust1_id varchar(30),	
item_name varchar(30),
item_type varchar(30),
primary key(item_id),
foreign key(prop3_id) references proprietor(prop_id),
foreign key(cust1_id) references customer(cust_id) on delete cascade);

create table transport(car_no varchar(30),
driv_name varchar(30),
emp4_id varchar(30),	
item4_id varchar(30),	
driv_phone number(30),
car_name varchar(30),
primary key(car_no),
foreign key(emp4_id) references employee(emp_id) ,
foreign key(item4_id) references items(item_id) on delete cascade);	

create table transfer(item_id1 varchar2(25),
	car_no1 varchar2(30),
foreign key(item_id1) references items(item_id),
foreign key(car_no1) references transport(car_no) on delete cascade);

insert into proprietor values('171-15-0051', 'hasan','noakhali','Bangladesh',01764155252);
insert into proprietor values('171-15-0062', 'sarker','narsingdi','Bangladesh',01961048554);
insert into proprietor values('171-15-0000', 'rafiq','chittagong','Bangladesh',01994386640);
insert into proprietor values('171-15-0086', 'biswas','feni','Bangladesh',0177210452);

insert into store values('1451-12','171-15-0051', 'maa flower1','sonaimuri');		
insert into store values('1451-13', '171-15-0062', 'maa flower2','mirpur1');
insert into store values('1451-14','171-15-0000','maa flower3','dhanmondi');
insert into store values('1451-15',  '171-15-0086','maa flower4','maijdee');


insert into Employee values('123-45','171-15-0051','shovo','dhaka','Bangladesh');
insert into Employee values('123-46','171-15-0062','shanto','cumilla','Bangladesh');
insert into Employee values('123-47','171-15-0000','soyket','barisal','Bangladesh');
insert into Employee values('123-48','171-15-0086','robuil','chottgram','Bangladesh');


insert into Customer values('2-23','123-45','arif',01915267787,'mirpur2');
insert into Customer values('3-24','123-45','asraf',01915267734,'mirpur2');
insert into Customer values('4-25','123-45','joy',01915267743,'ashulia');
insert into Customer values('5-26','123-45','noor',01915267345,'ashulia');


insert into items values('12-123','171-15-0051','2-23','rose','any');
insert into items values('12-124','171-15-0062','3-24','belly','any');
insert into items values('12-125','171-15-0000','4-25','amaryllis','any');
insert into items values('12-126','171-15-0086','5-26','daffodil','any');	

insert into transport values('1234567','anik','123-45','12-123',0176554544,'cycle1');
insert into transport values('1234568','abbas','123-46','12-124',0176554545,'cycle2');
insert into transport values('1234569','joynal','123-47','12-125',0176554546,'cycle3');
insert into transport values('1234560','saidur','123-48','12-126',0176554547,'cycle4');

insert into transfer values('12-123','1234567');
insert into transfer values('12-124','1234568');
insert into transfer values('12-125','1234569');
insert into transfer values('12-126','1234560');	
