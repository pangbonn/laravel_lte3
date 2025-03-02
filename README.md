# Laravel Admin Panel with AdminLTE 3

ระบบจัดการข้อมูลสำหรับผู้ดูแลระบบที่พัฒนาด้วย Laravel และ AdminLTE 3 Template

## คุณสมบัติหลัก

- ระบบจัดการผู้ใช้งาน (User Management)
- หน้า Dashboard แสดงสถิติและข้อมูลสำคัญ
- ระบบรักษาความปลอดภัยและการยืนยันตัวตน (Authentication)
- ส่วนติดต่อผู้ใช้ที่สวยงามด้วย AdminLTE 3
- รองรับการใช้งานบน PHP 8.2 และ Laravel 10/11

## ความต้องการของระบบ

- PHP >= 8.2
- Composer
- MySQL หรือ MariaDB
- Node.js และ NPM
- Git

## การติดตั้ง

1. Clone โปรเจคจาก Git repository

```bash
git clone https://github.com/username/my-admin-project.git
cd my-admin-project
```

2. ติดตั้ง Dependencies ผ่าน Composer

```bash
composer install
```

3. สร้างไฟล์ .env และกำหนดค่าที่จำเป็น

```bash
cp .env.example .env
php artisan key:generate
```

4. ตั้งค่าฐานข้อมูลในไฟล์ .env

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=my_admin_db
DB_USERNAME=root
DB_PASSWORD=
```

5. ทำการ Migrate เพื่อสร้างโครงสร้างฐานข้อมูล

```bash
php artisan migrate
```

6. ติดตั้ง NPM Dependencies และ Compile Assets

```bash
npm install
npm run dev
```

7. เริ่มใช้งานเซิร์ฟเวอร์

```bash
php artisan serve
```

เข้าใช้งานผ่าน URL: http://localhost:8000

## โครงสร้างโปรเจค

```
my-admin-project/
├── app/                    # โค้ดหลักของแอปพลิเคชัน
│   ├── Http/
│   │   ├── Controllers/    # Controllers
│   │   │   └── Admin/      # Controllers สำหรับส่วน Admin
│   │   └── Middleware/     # Middleware
│   └── Models/             # Models
├── config/                 # ไฟล์การตั้งค่าต่างๆ
│   └── adminlte.php        # การตั้งค่า AdminLTE
├── database/               # ส่วนจัดการฐานข้อมูล
│   ├── migrations/         # Database migrations
│   └── seeders/           # Seeders สำหรับข้อมูลเริ่มต้น
├── public/                 # ไฟล์ static และจุดเข้าของแอป
├── resources/              # ส่วนจัดการ Views และ Assets
│   ├── js/                 # JavaScript files
│   ├── css/                # CSS files
│   └── views/              # Blade view templates
│       └── admin/          # Views สำหรับส่วน Admin
├── routes/                 # การกำหนด Routes
│   └── web.php             # Web routes
└── vendor/                 # Dependencies จาก Composer
```

## การใช้งาน

1. **เข้าสู่ระบบ**
   - เข้าที่ http://localhost:8000/login
   - ใช้ข้อมูลบัญชีที่ลงทะเบียนไว้หรือสร้างบัญชีใหม่

2. **Dashboard**
   - หลังเข้าสู่ระบบจะถูกนำไปที่ Dashboard
   - แสดงข้อมูลสถิติและกราฟต่างๆ

3. **การจัดการผู้ใช้**
   - เพิ่ม แก้ไข ลบ ข้อมูลผู้ใช้งาน
   - กำหนดสิทธิ์ให้ผู้ใช้งาน

4. **การตั้งค่าระบบ**
   - ปรับแต่งการตั้งค่าต่างๆ ของระบบ

## การพัฒนาเพิ่มเติม

1. **เพิ่มโมดูลใหม่**
   - สร้าง Controller ใหม่ใน `app/Http/Controllers/Admin`
   - สร้าง Views ใหม่ใน `resources/views/admin`
   - เพิ่ม Routes ใน `routes/web.php`
   - เพิ่มรายการเมนูใน `config/adminlte.php`

2. **การปรับแต่ง UI**
   - แก้ไขการตั้งค่า AdminLTE ใน `config/adminlte.php`
   - แก้ไข CSS เพิ่มเติมใน `public/css/admin_custom.css`

## การแก้ไขปัญหาเบื้องต้น

- **ปัญหาการเข้าถึงไฟล์ storage**
  ```bash
  php artisan storage:link
  ```

- **รีเซ็ต Cache เมื่อมีการเปลี่ยนแปลงการตั้งค่า**
  ```bash
  php artisan config:clear
  php artisan cache:clear
  ```

## การอัพเดตระบบ

```bash
git pull
composer update
npm update
php artisan migrate
npm run dev
```

## รายละเอียดเวอร์ชัน

- เวอร์ชัน: 1.0.0
- PHP: 8.2
- Laravel: 10.x
- AdminLTE: 3.x

## ผู้พัฒนา

- ชื่อบริษัท/ผู้พัฒนา
- เว็บไซต์: https://example.com
- อีเมล: contact@example.com

## License

โปรเจคนี้อยู่ภายใต้ [MIT License](LICENSE)
