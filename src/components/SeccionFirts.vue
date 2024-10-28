<template>
  <div class="container">
    <header class="header">
      <img src="@/assets/vue.png" alt="aunar" class="logo" />
      <nav class="nav">
        <a>Inicio</a>
        <a>Nosotros</a>
        <a>Cursos</a>
        <a>Certificados</a>
      </nav>
      <button class="contact">Contáctanos</button>
    </header>

    <div class="content">
      <h1>Portal de Estudiantes</h1>
      <div class="courses">
        <div class="course-card" v-for="(course, index) in courses" :key="index">
          <h2>{{ course.title }}</h2>
          <p>{{ course.description }}</p>
          <button class="Details">Ver Detalles</button>
        </div>
      </div>
    </div>

    <footer class="footer">
      <p>Contacto: info@universidadautonoman.com | Teléfono: (123) 456-7890</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      courses: [
        { title: 'Curso de Desarrollo Web', description: 'Aprende a construir sitios web interactivos con HTML, CSS y JavaScript.' },
        { title: 'Curso de Python para Principiantes', description: 'Introduce a la programación con Python y desarrolla tus primeras aplicaciones.' },
        { title: 'Curso de Data Science', description: 'Explora el análisis de datos y aprende a utilizar herramientas como Pandas y NumPy.' },
        { title: 'Curso de Figma', description: 'Aprende a diseñar interfaces de usuario centradas en el usuario y accesibles.' },
        { title: 'Curso de Hacking', description: 'Domina el phishing y sniffing.' },
        { title: 'Curso de Inteligencia Artificial', description: 'Conoce los fundamentos de la IA y su aplicación en el mundo real.' },
      ],
    };
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: Arial, sans-serif;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100px;
  background-color: #fff;
  padding: 0 20px;
}

.logo {
  width: 100px;
  height: auto;
}

.nav {
  display: flex;
  flex: 1;
  justify-content: center;
}

.nav a {
  margin: 0 15px;
  text-decoration: none;
  color: #333;
  font-size: 20px;
}

.contact {
  background-color: #01045c;
  color: #fff;
  padding: 15px 30px;
  font-size: 18px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.contact:hover {
  background-color: #008ecc;
}

.content {
  flex-grow: 1;
  padding: 60px;
  background-color: rgba(245, 245, 245, 0.8);
  text-align: center;
  position: relative;
}

.content::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: url('@/assets/code.jpg');
  background-size: cover;
  background-position: center;
  opacity: 0.2;
  z-index: 0;
}

.content h1 {
  position: relative;
  z-index: 1;
}

.courses {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  justify-items: center;
}

.course-card {
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 20px;
  width: 300px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  text-align: center;
  position: relative;
  z-index: 1;
  transition: transform 0.3s, box-shadow 0.3s;
}

.course-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
}

.Details {
  background-color: #01045c;
  color: #fff;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.Details:hover {
  background-color: #008ecc;
}

.footer {
  background-color: #01045c;
  color: #fff;
  text-align: center;
  padding: 10px 0;
}

.footer p {
  margin: 0;
}

@media (max-width: 768px) {
  .header {
    flex-direction: column; 
    align-items: center; 
  }

  .nav {
    margin: 10px 0; 
  }

  .content {
    padding: 30px; 
  }

  .courses {
    grid-template-columns: repeat(1, 1fr); 
  }

  .course-card {
    width: 90%; 
  }
}
</style>
