# Send_Message
Задан следующий интерфейс 
public interface EJBDemo { 
   boolean login(String login, String psw); 
   String getMessage (String login); 
} 
   EJB-компонент , реализующий данный интерфейс в виде компонента типа 
Stateful. Компонент позволяет клиенту вызывать методы интерфейса EJBDemo 
в произвольном порядке. Приложение работает следующим образом: 

• ​Клиент приложения может находится в статусе зарегистрированного пользователя 
или незарегистрированного пользователя. Статус клиента определяет и хранит только 
EJB-компонент. 

• ​По умолчанию клиенту присваивается статус незарегистрированного пользователя. 

• ​Метод login() определяет и изменяет статус клиента на основании сравнения 
значений параметров метода login и psw со  стандартными значениями (значениями 
по умолчанию). Стандартные значения login и psw задаются разработчиком. 

• ​Если клиент вызывает метод login() с параметрами, которые равны стандартным, то 
метод login() возвращает значение true, а клиенту присваивается статус 
зарегистрированного пользователя. 

• ​Если клиент вызывает метод login() с параметрами, которые не равны стандартным, 
то метод login() возвращает значение false и присваивает клиенту статус 
незарегистрированного пользователя. 

• ​Статус зарегистрированного пользователя позволяет клиенту при вызове метода 
getMessage() получить стандартное сообщение (задается разработчиком). 
• ​Зарегистрированный пользователь может получить стандартное сообщение не более 
трёх раз подряд. После получения третьего сообщения статус клиента автоматически 
меняется на статус незарегистрированного пользователя. 

• ​При вызове метода getMessage() клиентом в статусе незарегистрированного 
пользователя клиенту возвращается  стандартное сообщение об отсутствии 
регистрации(задается разработчиком). 

Клиент реализован в виде web-клиента. 
