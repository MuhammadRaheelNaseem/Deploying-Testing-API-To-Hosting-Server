# Deploying-Testing-API-To-Hosting-Server

# Now Deploying API script into `pythonanywhere.com`

# What is pythonanywhere.com?
PythonAnywhere is a web hosting platform that allows you to run your Python applications and websites in the cloud. It provides a fully integrated environment for Python development, deployment, and web hosting, eliminating the need for managing servers and infrastructure.

With PythonAnywhere, you can easily deploy and host Python applications, including web applications built with frameworks like Flask and Django. It offers features such as web-based code editors, a Python console, scheduled tasks, and support for various Python versions and libraries.

PythonAnywhere also provides access to databases like MySQL, PostgreSQL, and SQLite, allowing you to store and retrieve data for your applications. It offers a web-based file system for managing your project files and allows you to install additional Python packages using the package manager.

The platform supports various web technologies and frameworks, making it suitable for a wide range of Python web development projects. PythonAnywhere offers free accounts with limited resources, as well as paid plans with additional features and higher resource allocations.

Overall, PythonAnywhere simplifies the process of hosting and deploying Python applications, allowing developers to focus on building and scaling their projects without the hassle of managing infrastructure.

![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/d715dde0-f7ff-4c11-b1da-ee3a2cd493b0)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/9457bf21-3f4a-4cd0-87a8-9bdbb1db7d3b)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/f2ba9132-0115-4c83-93dc-4c1c66c1f746)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/0bce4e90-7964-4d42-a728-8647a8a792d0)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/a59cd8cc-d878-421f-b292-ee6b337485f8)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/c14ea896-60d2-43ca-83e7-3dcc758985c7)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/2fe17db1-6121-42d1-aa0e-deef63c608e9)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/f5c852e3-217c-4c3b-85f3-8df7773c2a56)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/5e37db1f-5857-4229-8167-62e068e3b592)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/e8328405-c938-4359-80fe-6e8ecac214d2)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/7b0bd521-3b74-4c2c-bea2-2860a2d964c4)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/2fe85e28-b094-47bd-9b6e-2ef9a8aa5959)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/3dc50fb3-36cb-4755-b040-cb2cfc23fe32)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/9ceccd1c-b80e-4da9-8752-fadcfa4beb5c)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/a51342fd-c679-4ae3-969c-51d5a6772105)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/02a87e13-b5bd-4ae7-a70b-8b417612d4de)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/f02826c7-7e3a-47b7-80e1-952f26f3c056)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/c9463db9-a959-4175-911f-67d0711e63cc)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/a5ffe4cb-aba0-4917-ae56-7efc972070ac)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/8059551d-db12-4845-9695-b7ef50abe2c7)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/36fbceca-ec3e-4b8c-828f-57e17d2a1826)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/1f38109c-b220-4712-8352-ecfa8e974b79)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/e26a0433-845e-4278-8020-6ccbbd349da8)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/0225618f-2eed-4f8c-ab1b-096a4cd708be)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/ef2190f8-75b5-4a50-96d2-582b14883a3d)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/71a18d96-d8a8-4e19-93e2-321b2a612dac)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/8a7aa96c-b41c-4c3c-9b0b-ed877d790b28)

# Paste this API script into flasK_app.py and don't forgot to comment app.run() in last line of the script
```Python
from flask import Flask, request, jsonify
import mysql.connector

app = Flask(__name__)

# MySQL configurations
db = mysql.connector.connect(
    host='your_mysql_host',
    user='your_mysql_user',
    password='your_mysql_password',
    database='your_mysql_database'
)

# Create a table in the database if it doesn't exist
def create_table():
    cur = db.cursor()
    cur.execute("CREATE TABLE IF NOT EXISTS temp_emp_3 (ID INT PRIMARY KEY AUTO_INCREMENT, Name VARCHAR(100), Email VARCHAR(100), Address VARCHAR(100))")
    db.commit()
    cur.close()

# API route to get all users
@app.route('/api/users', methods=['GET'])
def get_users():
    cur = db.cursor()
    cur.execute("SELECT * FROM temp_emp_3")
    users = cur.fetchall()
    cur.close()
    user_list = []
    for user in users:
        user_dict = {
            'id': user[0],
            'name': user[1],
            'email': user[2],
            'address': user[3]
        }
        user_list.append(user_dict)
    return jsonify(user_list)

# API route to create a new user
@app.route('/api/users/add', methods=['POST'])
def create_user():
    name = request.json.get('name')
    email = request.json.get('email')
    addr = request.json.get('address')
    cur = db.cursor()
    cur.execute("INSERT INTO temp_emp_3 (Name, Email, Address) VALUES (%s, %s, %s)", (name, email, addr))
    db.commit()
    cur.close()
    return jsonify({'message': 'User created successfully'})

# API route to update an existing user
@app.route('/api/users/update/<string:user_id>', methods=['PUT'])
def update_user(user_id):
    name = request.json.get('name')
    email = request.json.get('email')
    addr = request.json.get('address')
    cur = db.cursor()
    cur.execute("UPDATE temp_emp_3 SET Name = %s, Email = %s, Address = %s WHERE ID = %s", (name, email, addr, user_id))
    db.commit()
    cur.close()
    return jsonify({'message': 'User updated successfully'})

# API route to delete a user
@app.route('/api/users/delete/<int:user_id>', methods=['DELETE'])
def delete_user(user_id):
    cur = db.cursor()
    cur.execute("DELETE FROM temp_emp_3 WHERE ID = %s", (user_id,))
    db.commit()
    cur.close()
    return jsonify({'message': 'User deleted successfully'})

if __name__ == '__main__':
    create_table()
    # app.run()

```

![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/d17cfecf-dc38-450d-bc80-9173e0b3257c)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/6100d08f-3453-4b16-b268-ba95ed0d7669)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/8ab0c9cf-e1b3-4ee1-b3e1-ea48fe122efe)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/3ce29301-0294-4190-9270-5828871978f1)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/51bcd4ef-ce3a-474e-9daa-05548c48a5a1)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/a75a104a-394f-4b1d-ad78-117a04b02afa)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/e035777a-5e20-46c8-b825-6bf91af0262c)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/e56dfe94-30b4-4762-bcd6-86a49ce61fe2)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/a54f3405-b213-47da-8728-50dac1125681)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/f4707672-95be-445f-832f-c22642330f34)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/d6fcb2f2-9c08-4306-ab76-c84e3a09ac7f)
![image](https://github.com/MuhammadRaheelNaseem/Flask-API-Development/assets/63813881/8e20d293-e8e8-4547-a4ac-118861561b3e)
