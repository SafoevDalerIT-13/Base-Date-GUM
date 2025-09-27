=====1.Залы======
CREATE TABLE gyms (
    gym_id INT PRIMARY KEY AUTO_INCREMENT,
    gym_name VARCHAR(100) NOT NULL,
    address VARCHAR(200) NOT NULL,
    gym_phone VARCHAR(20),
    open_time TIME NOT NULL,
    close_time TIME NOT NULL
);

====2. Клиенты======
CREATE TABLE clients (
    client_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    phone VARCHAR(20) UNIQUE,
    email VARCHAR(100),
    date_of_birth DATE,
    registration_date DATETIME DEFAULT CURRENT_TIMESTAMP
);

=====3. Посещения======
CREATE TABLE visits (
    visit_id INT PRIMARY KEY AUTO_INCREMENT,
    client_id INT NOT NULL,
    gym_id INT NOT NULL,
    check_in_time DATETIME NOT NULL,
    check_out_time DATETIME,
    FOREIGN KEY (client_id) REFERENCES clients(client_id),
    FOREIGN KEY (gym_id) REFERENCES gyms(gym_id)
);

=====4. Сотрудники======
CREATE TABLE employees (
    employee_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    emp_phone VARCHAR(20),
    emp_email VARCHAR(100),
    gym_id INT,
    hire_date DATE NOT NULL,
    post VARCHAR(50) NOT NULL,
    salary DECIMAL(10,2) NOT NULL,
    FOREIGN KEY (gym_id) REFERENCES gyms(gym_id)
);

=====5. Оборудование =====
CREATE TABLE equipment (
    equipment_id INT PRIMARY KEY AUTO_INCREMENT,
    equipment_name VARCHAR(100) NOT NULL,
    buy_date DATE,
    equipment_status VARCHAR(20) DEFAULT 'active',
    gym_id INT NOT NULL,
    FOREIGN KEY (gym_id) REFERENCES gyms(gym_id)
);

==========6. Тарифы ======
CREATE TABLE rates (
    rate_id INT PRIMARY KEY AUTO_INCREMENT,
    rate_name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    duration_days INT NOT NULL,
    description TEXT
);

====== 7. Абонементы =========
CREATE TABLE subscriptions (
    subscription_id INT PRIMARY KEY AUTO_INCREMENT,  
    client_id INT NOT NULL,                          
    rate_id INT NOT NULL,                            
    start_date DATE NOT NULL,                        
    end_date DATE NOT NULL,                          
    subscription_status VARCHAR(20) DEFAULT 'active', 
    FOREIGN KEY (client_id) REFERENCES clients(client_id),
    FOREIGN KEY (rate_id) REFERENCES rates(rate_id)
);
