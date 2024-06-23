import React, { useState } from 'react';

const App = () => {
  const [activeTab, setActiveTab] = useState('inicio');

  const renderContent = () => {
    switch(activeTab) {
      case 'inicio':
        return (
          <div>
            <h2>Bienvenido al Wilde Sporting Club</h2>
            <p>Explora nuestras instalaciones y actividades. ¡Únete a nuestra comunidad deportiva!</p>
          </div>
        );
      case 'actividades':
        return (
          <div>
            <h2>Nuestras Actividades</h2>
            <ul>
              <li>Básquet masculino</li>
              <li>Básquet femenino</li>
              <li>Natación</li>
              <li>Taekwondo</li>
              <li>Pelota paleta</li>
              <li>Yoga</li>
              <li>Colonia de invierno</li>
              <li>Colonia de verano</li>
            </ul>
          </div>
        );
      case 'eventos':
        return (
          <div>
            <h2>Próximos Eventos</h2>
            <ul>
              <li>Torneo de Básquet - 15 de Julio</li>
              <li>Clases de Natación - Todos los Sábados</li>
              <li>Exhibición de Taekwondo - 30 de Agosto</li>
            </ul>
          </div>
        );
      case 'perfil':
        return (
          <div>
            <h2>Mi Perfil</h2>
            <p>Nombre: [Nombre del Usuario]</p>
            <p>Membresía: Activa</p>
            <p>Actividades: Básquet masculino, Natación</p>
          </div>
        );
      default:
        return null;
    }
  };

  return (
    <div style={{ fontFamily: 'Arial, sans-serif', maxWidth: '800px', margin: '0 auto', padding: '20px' }}>
      <header style={{ textAlign: 'center', marginBottom: '20px' }}>
        <h1 style={{ color: '#0000FF' }}>Wilde Sporting Club</h1>
      </header>
      <nav style={{ display: 'flex', justifyContent: 'center', marginBottom: '20px' }}>
        <button onClick={() => setActiveTab('inicio')} style={{ margin: '0 10px', padding: '10px 20px' }}>Inicio</button>
        <button onClick={() => setActiveTab('actividades')} style={{ margin: '0 10px', padding: '10px 20px' }}>Actividades</button>
        <button onClick={() => setActiveTab('eventos')} style={{ margin: '0 10px', padding: '10px 20px' }}>Eventos</button>
        <button onClick={() => setActiveTab('perfil')} style={{ margin: '0 10px', padding: '10px 20px' }}>Perfil</button>
      </nav>
      <main style={{ backgroundColor: '#f0f0f0', padding: '20px', borderRadius: '5px' }}>
        {renderContent()}
      </main>
    </div>
  );
};

export default App;
