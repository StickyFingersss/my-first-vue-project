<template>
  <div class="resume">
    <h1>Мое резюме</h1>

    <div class="personal-info">
      <h2>Личная информация</h2>
      <p class="personal-info-item">Имя: {{ personalInfo.name }}</p>
      <p class="personal-info-item">Почта: {{ personalInfo.email }}</p>
      <p class="personal-info-item">Проживает: {{ personalInfo.address }}</p>
      <p class="personal-info-item">Гражданство: {{ personalInfo.citizenship }}</p>
      <p class="personal-info-item">Разрешение на работу: {{ personalInfo.workPermit }}</p>
      <p class="personal-info-item">Готов к переезду: {{ personalInfo.readyToRelocate }}</p>
      <p class="personal-info-item">
        Готов к командировкам: {{ personalInfo.readyForBusinessTrips }}
      </p>
    </div>

    <div class="desired-position">
      <h2>Желаемая должность и зарплата</h2>
      <p class="desired-position-item">Должность: {{ desiredPosition.title }}</p>
      <p class="desired-position-item">Специализации: {{ desiredPosition.specializations }}</p>
      <p class="desired-position-item">Занятость: {{ desiredPosition.employment }}</p>
      <p class="desired-position-item">График работы: {{ desiredPosition.workSchedule }}</p>
      <p class="desired-position-item">
        Желательное время в пути до работы: {{ desiredPosition.commuteTime }}
      </p>
    </div>

    <div class="work-experience">
      <h2>Опыт работы</h2>
      <ul>
        <li v-for="experience in workExperience" :key="experience.id">
          <p class="work-experience-item">
            <strong>{{ experience.position }}</strong>
          </p>
          <p class="work-experience-item">{{ experience.company }}</p>
          <p class="work-experience-item">{{ experience.duration }}</p>
          <p class="work-experience-item">{{ experience.description }}</p>
        </li>
      </ul>
    </div>

    <div class="education">
      <h2>Образование</h2>
      <p class="education-item">{{ education.degree }}</p>
      <p class="education-item">{{ education.university }}</p>
      <p class="education-item">{{ education.year }}</p>
      <p class="education-item">{{ education.faculty }}</p>
    </div>

    <div class="skills">
      <h2>Ключевые навыки</h2>
      <p class="skills-item">Знание языков: {{ skills.languages }}</p>
      <p class="skills-item">Навыки: {{ skills.technicalSkills }}</p>
    </div>

    <div class="additional-info">
      <h2>Дополнительная информация</h2>
      <p class="additional-info-item">Обо мне: {{ additionalInfo.aboutMe }}</p>
      <p class="additional-info-item">
        Telegram: <a :href="additionalInfo.telegram">{{ additionalInfo.telegram }}</a>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CV',
  data() {
    return {
      personalInfo: {
        name: 'Валерий',
        email: 'dynko.valerii@gmail.com',
        address: 'Москва',
        citizenship: 'Россия',
        workPermit: 'Россия, Казахстан',
        readyToRelocate: 'Да',
        readyForBusinessTrips: 'Да',
      },
      desiredPosition: {
        title: 'Frontend-разработчик',
        specializations: 'Программист, разработчик',
        employment: 'полная занятость',
        workSchedule: 'полный день',
        commuteTime: 'не имеет значения',
      },
      workExperience: [
        {
          id: 1,
          position: 'Full Stack разработчик',
          company: 'CustomeX',
          duration: 'Март 2022 — настоящее время (1 год 8 месяцев)',
          description:
            'Совместно с командой создаю user-friendly CRM с гибкой кастомизацией под потребности бизнеса. Ответственен за разработку модуля управления задачами, инструмента для массовой загрузки данных и многие другие задачи. Соотношение front/back: 70/30. Технологический стек: React, Redux, MUI, TypeScript, PostgreSQL, React-router, Axios, WebSocket, Sequelize.',
        },
        {
          id: 2,
          position: 'Frontend-разработчик',
          company: 'Форсайт, ООО',
          duration: 'Сентябрь 2020 — Март 2022 (1 год 7 месяцев)',
          description:
            'Работал над CRM для компании Газпром. Перевел приложение на React, провел рефакторинг кода, создал конструктор для шаблонизации документов с использованием Drag-and-drop. Технологический стек: ReactJS, TypeScript, React-router, Axios, Redux, React-paginate.',
        },
      ],
      education: {
        degree: 'Высшее',
        university:
          'Новосибирский национальный исследовательский государственный университет, Новосибирск',
        year: '2020',
        faculty: 'Факультет информационных технологий, Информационные технологии',
      },
      skills: {
        languages: 'Русский — Родной\nАнглийский — B1 — Средний',
        technicalSkills:
          'Git; JavaScript; HTML5; CSS3; TypeScript; Node.js; Redux; ReactJS; SCSS; Jest; Express.js; WebSocket; PostgreSQL; Sequelize; REST API; Babel; Axios; Bootstrap; API; Next.js; БЭМ',
      },
      additionalInfo: {
        aboutMe:
          'Frontend разработчик с 3 годами опыта коммерческой разработки. Мои навыки включают HTML, CSS, JavaScript (ES6+), React.js, Redux, Webpack, Babel, RESTful API, Git, Jest. Всегда готов углубить знания и освоить новые технологии.',
        telegram: 'https://t.me/dynkovalerii',
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.resume {
  font-family: Arial, sans-serif;
  margin: 20px;
  padding: 20px;
  border: 2px solid #3498db;
  border-radius: 10px;
  background-color: #f0f0f0;

  h1 {
    font-size: 24px;
    color: #3498db;
    border-bottom: 2px solid #3498db;
    padding-bottom: 10px;
  }

  h2 {
    font-size: 18px;
    margin-top: 20px;
    color: #555;
  }

  .personal-info,
  .desired-position,
  .work-experience,
  .education,
  .skills,
  .additional-info {
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 5px;
    padding: 20px;
    margin: 20px 0;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }

  ul {
    list-style: none;
    padding: 0;
  }

  li {
    margin-bottom: 20px;
    p {
      line-height: 1.5;
    }
  }

  a {
    text-decoration: none;
    color: #3498db;
  }

  a:hover {
    text-decoration: underline;
  }
}
</style>
