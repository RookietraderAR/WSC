# WSC
import React, { useState } from 'react';
import { Calendar, User, Info, Activity } from 'lucide-react';
import { Card, CardContent, CardHeader, CardTitle } from '@/components/ui/card';

const App = () => {
  const [activeTab, setActiveTab] = useState('inicio');

  const renderContent = () => {
    switch(activeTab) {
      case 'inicio':
        return (
          <Card className="mt-4">
            <CardHeader>
              <CardTitle>Bienvenido al Wilde Sporting Club</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Explora nuestras instalaciones y actividades. ¡Únete a nuestra comunidad deportiva!</p>
            </CardContent>
          </Card>
        );
      case 'actividades':
        return (
          <Card className="mt-4">
            <CardHeader>
              <CardTitle>Actividades</CardTitle>
            </CardHeader>
            <CardContent>
              <ul>
                <li>Fútbol</li>
                <li>Básquet</li>
                <li>Natación</li>
                <li>Tenis</li>
                <li>Gimnasio</li>
              </ul>
            </CardContent>
          </Card>
        );
      case 'eventos':
        return (
          <Card className="mt-4">
            <CardHeader>
              <CardTitle>Próximos Eventos</CardTitle>
            </CardHeader>
            <CardContent>
              <ul>
                <li>Torneo de Fútbol - 15 de Julio</li>
                <li>Clases de Natación - Todos los Sábados</li>
                <li>Cena Anual del Club - 30 de Agosto</li>
              </ul>
            </CardContent>
          </Card>
        );
      case 'perfil':
        return (
          <Card className="mt-4">
            <CardHeader>
              <CardTitle>Mi Perfil</CardTitle>
            </CardHeader>
            <CardContent>
              <p>Nombre: [Nombre del Usuario]</p>
              <p>Membresía: Activa</p>
              <p>Actividades: Fútbol, Gimnasio</p>
            </CardContent>
          </Card>
        );
      default:
        return null;
    }
  };

  return (
    <div className="max-w-md mx-auto mt-8 p-4 bg-white">
      <div className="flex items-center justify-center mb-4">
        {/* En una aplicación real, usaríamos la ruta real de la imagen del escudo */}
        <img src="/api/placeholder/100/100" alt="Escudo Wilde Sporting Club" className="w-16 h-16 mr-4" />
        <h1 className="text-2xl font-bold text-blue-600">Wilde Sporting Club</h1>
      </div>
      <div className="flex justify-around mb-4 bg-blue-600 rounded-lg p-2">
        <button 
          onClick={() => setActiveTab('inicio')}
          className={`p-2 rounded ${activeTab === 'inicio' ? 'bg-white text-blue-600' : 'text-white'}`}
        >
          <Info size={24} />
        </button>
        <button 
          onClick={() => setActiveTab('actividades')}
          className={`p-2 rounded ${activeTab === 'actividades' ? 'bg-white text-blue-600' : 'text-white'}`}
        >
          <Activity size={24} />
        </button>
        <button 
          onClick={() => setActiveTab('eventos')}
          className={`p-2 rounded ${activeTab === 'eventos' ? 'bg-white text-blue-600' : 'text-white'}`}
        >
          <Calendar size={24} />
        </button>
        <button 
          onClick={() => setActiveTab('perfil')}
          className={`p-2 rounded ${activeTab === 'perfil' ? 'bg-white text-blue-600' : 'text-white'}`}
        >
          <User size={24} />
        </button>
      </div>
      {renderContent()}
    </div>
  );
};

export default App;
