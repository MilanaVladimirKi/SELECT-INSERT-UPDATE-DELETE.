# Теория баз данных

## Тема: Запросы SELECT, INSERT, UPDATE, DELETE.

Запросы:

1. Вывести таблицу кафедр, но расположить ее поля в обратном порядке.
SELECT Name, Financing, Id FROM Departments;

![текст](https://sun9-34.userapi.com/impg/TEaVCcAf337DYpTzNiG_0OVS_cOB7C4qKe4feQ/wqcz3ynIsh8.jpg?size=1920x1080&quality=95&sign=77da14de5f880f281a1af72e160ca837&type=album)

2. Вывести названия групп и их рейтинги с уточнением имен полей именем таблицы.
SELECT `Groups`.Name AS Groups_Name, `Groups`.Rating AS Groups_Rating FROM `Groups`;

![текст](https://sun9-12.userapi.com/impg/6xK-Do9Ieex0Iv_jDua3JwfqPxxQfoBBIERRmw/tU1iHgAC7v0.jpg?size=1920x1080&quality=95&sign=5fb8e0a69aec80a95f6e642b0e48a69e&type=album)

SELECT `Groups`.Name, `Groups`.Rating FROM `Groups`;

3. Вывести для преподавателей их фамилию, процент ставки по отношению к надбавке и процент ставки по отношению к зарплате (сумма ставки и надбавки).
SELECT Name, Salary * 100 / Premium, Salary * 100 / (Salary + Premium) FROM Teachers;
4. Вывести таблицу факультетов в виде одного поля в следующем формате: “The dean of faculty [faculty] is [dean].”.
SELECT CONCAT("The dean of faculty ", Name, " is ", Dean) FROM Faculties;
5. Вывести фамилии преподавателей, которые являются профессорами и ставка которых превышает 1050.
SELECT Surname FROM Teachers WHERE isProfessor = 1 AND Salary > 1050;

![текст](https://sun9-12.userapi.com/impg/wg9aHMcFMr23skusZZkTsst0csqbT1xwuRdsBQ/Ts_vXTbiAtA.jpg?size=1920x1080&quality=95&sign=d8b61a7283e6ad7a98126c0597786d77&type=album)

6. Вывести названия кафедр, фонд финансирования которых меньше 11000 или больше 25000. 
SELECT Name FROM Departments WHERE Financing < 11000 OR Financing > 25000;
7. Вывести названия факультетов кроме факультета “Computer Science”.
SELECT Name FROM Faculties WHERE Name != "Computer Science";
8. Вывести фамилии и должности преподавателей, которые не являются профессорами. 
SELECT Surname, Position FROM Teachers WHERE isProfessor != 1;
9. Вывести фамилии, должности, ставки и надбавки ассистентов, у которых надбавка в диапазоне от 160 до 550.
SELECT Surname, Position, Salary, Premium FROM Teachers WHERE isAssistant = 1 AND Premium BETWEEN 160 AND 550;

![текст](https://sun9-12.userapi.com/impg/BR5rk0fWRN2s4vqjQ4GuAnmWRI_ET1wFreMB9w/0-NC6QwdspI.jpg?size=1920x1080&quality=95&sign=b26db67136b6b4c420129fb4422f6d0e&type=album)

SELECT Surname, Position, Salary, Premium FROM Teachers WHERE isAssistant = 1 AND Premium > 160 AND Premium < 550;

10. Вывести фамилии и ставки ассистентов.
SELECT Surname, Salary FROM Teachers WHERE isAssistant = 1;

![текст](https://sun9-6.userapi.com/impg/DXYBswwH_9Ph2qqIAIiNbgSbaTKRamWRGXEs7A/eEP4WRdQjns.jpg?size=1920x1080&quality=95&sign=5977bb9fa73fd42cff5f9f73c3df305f&type=album)

11. Вывести фамилии и должности преподавателей, которые были приняты на работу до 01.01.2000.
SELECT Surname, Position FROM Teachers WHERE EmploymentDate < "2000-01-01";
12. Вывести названия кафедр, которые в алфавитном порядке располагаются до кафедры “Software Development”. Выводимое поле должно иметь название “Name of De­part­ment”.
SELECT Name AS `Name of Department` FROM Departments WHERE Name < "Software Development";
13. Вывести фамилии ассистентов, имеющих зарплату (сумма ставки и надбавки) не более 1200.
SELECT Surname FROM Teachers WHERE isAssistant = 1 AND (Salary + Premium) < 1200;
14. Вывести названия групп 5-го курса, имеющих рейтинг в диапазоне от 2 до 4.
SELECT Name FROM `Groups` WHERE Year = 5 AND Rating BETWEEN 2 AND 4;

![текст](https://sun9-52.userapi.com/impg/0_1RThHS6pqWOYaVRU8wc4Rm4WxYScQYdlyxEw/l_ofq0fUzBU.jpg?size=1920x1080&quality=95&sign=f4ecf05a0d38dd3c0b99411236334567&type=album)

SELECT Name FROM `Groups` WHERE Year = 5 AND Rating <= 4 AND Rating >= 2;

15. Вывести фамилии ассистентов со ставкой меньше 550 или надбавкой меньше 200. 
SELECT Surname FROM Teachers WHERE isAssistant = 1 AND (Salary < 550 OR Premium < 200); 

![текст](https://sun9-36.userapi.com/impg/s_Ou7JK2VrMaZukml1sMX6jWwgrhZtP_xsKh0g/dQw6UYcriAY.jpg?size=1920x1080&quality=95&sign=ed350749a399ed857f185f4811e754ec&type=album)
