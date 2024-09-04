Carry System - Sistema de Carga para FiveM

Este script proporciona un sistema interactivo de carga de personajes, ideal para servidores de rol en FiveM. El sistema utiliza qb-menu para crear un menú accesible por comandos.

Funcionalidades del Sistema

	1.	Comando de Apertura:
	•	Usa el comando /carry para abrir el menú interactivo de opciones de carga.
	2.	Opciones de Carga Disponibles:
	•	Carry Normal: Carga a otro jugador en brazos.
	•	Piggyback: Lleva a otro jugador en la espalda.
	•	Caballito: Lleva a otro jugador sobre los hombros.
	3.	Liberación de la Carga:
	•	Jugador Cargador: Presiona E para soltar al jugador que estás cargando.
	•	Jugador Cargado: También puede presionar E para liberarse de la carga.

Compatibilidad

	•	Este script es totalmente compatible con cualquier sistema que utilice qb-menu.
	•	Se requieren adaptaciones mínimas para integrarlo con las configuraciones específicas de tu servidor.

Configuración y Requisitos

	1.	Integración con QBCore:
	•	Este script está diseñado para funcionar con la estructura de QBCore.
	•	Modifica los permisos y roles necesarios en el archivo de configuración config.lua para permitir el acceso adecuado a diferentes trabajos o grupos.
	2.	Adaptaciones Recomendadas:
	•	Personalización del Menú: Modifica el menú para reflejar el estilo de tu servidor o incluir más opciones de carga.
	•	Mapeo de Teclas: Asegúrate de que el mapeo de la tecla E no interfiera con otras funcionalidades críticas de tu servidor.
	3.	Optimización del Código:
	•	Utiliza prácticas recomendadas de optimización de scripts en Lua, asegurándote de minimizar el uso de bucles intensivos y eventos frecuentes para mantener un rendimiento fluido.

Ejemplo de Uso en el Servidor

	1.	Abre el menú de carga:

RegisterCommand('carry', function()
    TriggerEvent('qb-menu:client:openCarryMenu')
end)


	2.	Definición de Opciones del Menú:

local carryMenu = {
    {
        header = "Opciones de Carga",
        isMenuHeader = true
    },
    {
        header = "Carry Normal",
        txt = "Carga a otro jugador en brazos",
        params = {
            event = "carry:client:startNormalCarry"
        }
    },
    {
        header = "Piggyback",
        txt = "Lleva a otro jugador en la espalda",
        params = {
            event = "carry:client:startPiggyback"
        }
    },
    {
        header = "Caballito",
        txt = "Lleva a otro jugador sobre los hombros",
        params = {
            event = "carry:client:startCaballito"
        }
    },
    {
        header = "Cerrar Menú",
        txt = "",
        params = {
            event = "qb-menu:client:closeMenu"
        }
    }
}



Consideraciones Finales

	•	Revisa las funciones de liberación (E) y asegúrate de que estén correctamente vinculadas en los archivos de eventos de cliente para que ambas partes puedan liberar o ser liberadas.
	•	Este script se puede extender fácilmente para incluir animaciones adicionales o variaciones de carga, según las preferencias del servidor.