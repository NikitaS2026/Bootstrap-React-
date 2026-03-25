ЗДЕСЬ ОПИСАНА РАБОТА С Bootstrap

Теория:

    <Container>: Обертка.

        fluid: растягивается на 100% ширины экрана.

        без fluid: имеет фиксированную ширину по центру (с отступами по бокам).

    <Row>: Строка. Внутри неё живут колонки.

    <Col>: Колонка.

        Всего в строке 12 виртуальных колонок.

        Ты говоришь колонке, сколько места занимать. xs={12} (весь ряд), md={6} (половина), lg={3} (четверть).

Твой инструмент — брейкпоинты (Breakpoints):

    xs (extra small) — телефоны (<576px)

    md (medium) — планшеты/ноуты (≥768px)

    xxl (extra extra large) — большие мониторы (≥1400px)

Если ты пишешь <Col xs={12} md={6}>, это читается так: "На мобиле займи всё место, а начиная с планшета и шире — занимай только половину". 

fluid — это "На весь экран". Всегда.

Представь себе ведро с водой.

    Обычный <Container> — это КИРПИЧ в ведре.

        Ты кидаешь его, он падает на дно.

        Слева и справа от кирпича есть пустое место (вода).

        На мониторе это выглядит так: контент по центру, а по бокам белые (или какие там у тебя) полосы.

    <Container fluid> — это ВОДА в ведре.

        Она растекается от стенки до стенки.

        Нет никаких пустых полос по бокам.

        Если ты растянешь экран (ведро станет шире) — вода (контент) тоже растянется.


🧠 НАПОМИНАЛКА: Bootstrap + React

🔗 0. Как они работают вместе
React = логика + компоненты
Bootstrap = сетка + стили

👉 Ты описываешь структуру в React,
👉 а Bootstrap делает красиво и адаптивно

⚙️ 1. Два способа работы
 Через className (чистый Bootstrap)
<div className="container">
  <div className="row">
    <div className="col-12 col-md-6"></div>
  </div>
</div>

 Через React-Bootstrap
import { Container, Row, Col } from "react-bootstrap";

<Container>
  <Row>
    <Col xs={12} md={6}></Col>
  </Row>
</Container>

 2. Основные элементы (СЕТКА)
Container
container → фиксированная ширина
container-fluid → 100%

 В React:

<Container fluid />
Row
Создаёт строку
Делит пространство на 12 частей
<Row></Row>
Col
Занимает часть строки
<Col xs={12} md={6} lg={3} />


📱 3. Брейкпоинты
Размер	Что значит
xs	телефон
sm	≥576px
md	≥768px
lg	≥992px
xl	≥1200px
xxl	≥1400px


🎯 4. Часто используемые "команды" (классы)
 Размеры колонок
col-6
col-md-4
col-lg-3
📐 Отступы (margin / padding)

Формат:

m / p + сторона + размер

Примеры:

mt-3   // margin-top
mb-2   // margin-bottom
p-4    // padding
px-5   // по бокам

Размеры:

0–5
📍 Выравнивание
d-flex
justify-content-center
align-items-center
📦 Flex
d-flex
flex-column
flex-row
flex-wrap
📏 Ширина / высота
w-100
h-100
🎨 Цвета
bg-primary
bg-dark
text-white
text-center
🧠 5. Как React усиливает Bootstrap

Вот где начинается магия 👇

🔁 Условные классы
<div className={isActive ? "bg-success" : "bg-danger"} />
🔄 Динамическая сетка
{items.map(item => (
  <Col md={4} key={item.id}>
    {item.name}
  </Col>
))}
📱 Адаптивность + логика
<Container fluid={isMobile} />
🧱 6. Часто используемые компоненты (React-Bootstrap)
<Button />
<Card />
<Form />
<Navbar />
<Nav />
<Modal />
<Alert />
<Spinner />

Пример:

import { Button } from "react-bootstrap";

<Button variant="primary">Нажми</Button>
⚡ 7. Важные правила
❗ 1. Всегда:
Container → Row → Col
❗ 2. В строке максимум 12
<Col md={6} />
<Col md={6} />
❗ 3. Mobile-first

Сначала xs, потом md, lg

❗ 4. React = управление

Bootstrap = отображение

🪣 Твоя метафора (финал)
Container = ведро
Row = слой внутри
Col = куски пространства
Bootstrap = форма воды
React = решает, сколько воды и куда лить
🚀 Мини-шпаргалка
<Container>
  <Row>
    <Col xs={12} md={6} className="p-3">
      Контент
    </Col>
    <Col xs={12} md={6} className="p-3">
      Контент
    </Col>
  </Row>
</Container>        
