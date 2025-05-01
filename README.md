# Мөнгөндент - Шүдний эмнэлгийн вэбсайт

Мөнгөндент шүдний эмнэлгийн танилцуулга вэбсайт. Next.js 15.3.1, TypeScript, TailwindCSS, Shadcn UI, Framer Motion, Prisma ORM ашиглан хийгдсэн.

## Технологиуд

- Next.js 15.3.1 (App Router, TypeScript)
- TailwindCSS
- Shadcn UI
- Framer Motion
- Lodash
- Prisma ORM + PostgreSQL (Neon)

## Суулгах заавар

1. Прожектийг клон хийх:

```bash
git clone <repository-url>
cd dental-clinic
```

2. Хамаарлуудыг суулгах:

```bash
npm install
```

3. Тохиргооны файл үүсгэх:

`.env` файл үүсгэж дараах мэдээллийг оруулна:

```
# Локал PostgreSQL ашиглах бол:
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/dental_clinic"

# Эсвэл Neon PostgreSQL ашиглах бол (зөвлөмж):
# DATABASE_URL="postgresql://username:password@ep-some-id.region.aws.neon.tech/dbname?sslmode=require"

ADMIN_API_KEY="your-secure-api-key-here"
NODE_ENV="development"
```

**Neon PostgreSQL ашиглах (зөвлөмж):**

1. [Neon](https://neon.tech) дээр бүртгүүлж, шинэ төсөл үүсгэнэ
2. Холболтын мэдээллийг авч `.env` файлд оруулна
3. Холболтын мэдээлэл нь ийм хэлбэртэй байна: `postgresql://username:password@endpoint/dbname?sslmode=require`

4. Өгөгдлийн сан үүсгэх ба өгөгдөл оруулах:

```bash
# Өгөгдлийн сан үүсгэх, миграци ажиллуулах
npm run setup-db

# Жишээ өгөгдөл оруулах
npm run seed-db

# Эсвэл хоёуланг нь нэг дор ажиллуулах
npm run setup-and-seed
```

5. Хөгжүүлэлтийн серверийг ажиллуулах:

```bash
npm run dev
```

6. Админ хэсэгт нэвтрэх:

Админ хэсэгт нэвтрэхийн тулд дараах мэдээллийг ашиглана:

- URL: http://localhost:3000/admin/login
- Имэйл: admin@example.com
- Нууц үг: password

## Сайтны бүтэц

- **Нүүр хуудас** (`/`) - Эмнэлгийн танилцуулга, үйлчилгээнүүд
- **Мөнгөнзул эмчийн тухай** (`/mungunzul`) - Эмчийн намтар, мэргэшил
- **Хүүхдийн эмчилгээ** (`/services/children-dentistry`) - Хүүхдийн шүдний эмчилгээний тухай
- **Циркон бүрээс** (`/services/zircon`) - Циркон бүрээсний үйлчилгээний тухай
- **Цаг захиалга** (`/booking`) - Цаг захиалах форм
- **eShop** (`/shop`) - Шүдний эрүүл мэндийн бүтээгдэхүүний дэлгүүр
- **Холбоо барих** (`/contact`) - Холбоо барих мэдээлэл, хаяг

## Өгөгдлийн сангийн моделууд

- `Booking` - Цаг захиалгын мэдээлэл
- `Product` - Бүтээгдэхүүний мэдээлэл
- `Order` - Захиалгын мэдээлэл
- `OrderItem` - Захиалгын бүтээгдэхүүний мэдээлэл

## API Endpoints

### Бүтээгдэхүүнүүд
- `GET /api/products` - Бүх бүтээгдэхүүнийг авах
- `GET /api/products/:id` - Тодорхой бүтээгдэхүүний мэдээлэл авах
- `POST /api/products` - Шинэ бүтээгдэхүүн үүсгэх (админ эрхтэй)
- `PUT /api/products/:id` - Бүтээгдэхүүний мэдээлэл шинэчлэх (админ эрхтэй)
- `DELETE /api/products/:id` - Бүтээгдэхүүн устгах (админ эрхтэй)

### Цаг захиалга
- `GET /api/bookings` - Бүх цаг захиалгыг авах (админ эрхтэй)
- `GET /api/bookings/:id` - Тодорхой цаг захиалгын мэдээлэл авах (админ эрхтэй)
- `POST /api/bookings` - Шинэ цаг захиалга үүсгэх
- `PUT /api/bookings/:id` - Цаг захиалгын мэдээлэл шинэчлэх (админ эрхтэй)
- `DELETE /api/bookings/:id` - Цаг захиалга устгах (админ эрхтэй)

### Захиалгууд
- `GET /api/orders` - Бүх захиалгыг авах (админ эрхтэй)
- `GET /api/orders/:id` - Тодорхой захиалгын мэдээлэл авах
- `POST /api/orders` - Шинэ захиалга үүсгэх
- `PUT /api/orders/:id` - Захиалгын мэдээлэл шинэчлэх (админ эрхтэй)
- `DELETE /api/orders/:id` - Захиалга устгах (админ эрхтэй)

### Тохиргоо
- `GET /api/settings` - Сайтын тохиргоог авах
- `POST /api/settings` - Сайтын тохиргоог шинэчлэх (админ эрхтэй)

## Лиценз

Мөнгөндент шүдний эмнэлгийн вэбсайт © 2024