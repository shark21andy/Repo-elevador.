# Repo-elevador.

Integrantes :
Flores Jaime Andrea Margarita 
GUZMAN RODRIGUEZ INGRID JULIETA
Hernández Herrera Ulises Gadiel
Hernández Cruz Mariel

SISTEMA MECÁNICO 
componentes: 
 - cabina del elevador 
 - contrapeso 
 - guias verticales 
 - Motor (generalmente de tracción) 
 - Poleas y cables de acero 
 - Amortiguadores 
Función 
 - Permite el movimiento vertical de la cabina entre pisos 
 - El contrapeso equilibra el peso de la cabina para reducir la carga del motor
 - Las guias aseguran que la cabina se desplace de forma estable y recta.

SISTEMA ELÉCTICO 
Componentes :
 - Motor eléctrico (AC o DC).
 - Fuente de alimentación.
 - Sistema de iluminación (cabina y paneles).
 - Cableado y conectores.
Función:
 - Suministra energia al motor y a todos los dispositivos electrónicos del elevador.
 - Asegura el funcionamiento de luces, indicadores y sensores.
 - Puede incluir baterias o UPS para respaldo en caso de apagón.

SISTEMA DE CONTROL 
Componentes :
 - Unidad logics programable (PLC o microcontrolador).
 - Panel de control (interior y exterior).
 - Sensores de piso y posición.
 - Variador de velocidad.
Función:
 - Recibe las solicitudes de piso (internas y externas).
 - Controla el motor para mover la cabina al piso solicitado. 
 - Regula la velocidad y aceleración para visjes suaves. 
 - Sincroniza la apertura y cierre de puertas. 

SISTEMA DE SEGURIDAD : 
Componentes: 
 - Freno electromecánico. 
 - Limitadores de velocidad. 
 - Sensores de puertas ( antipinzamiento) 
 - Sistema de comunicación de emergencia. 
 - Amortiguadores en el fondo del eje. 
Función : 
 - Detiene el elevador si supera la velocidad máxima.
 - Asegura que las puertas no se cierren con personas u objetos en el paso.
 - Permite llamadas de emergencia en caso de fallo.
 - Protege a los pasajeros en caso de caida o choque. 










pseudocodigo
INICIO

Definir piso_actual ← 1
Definir solicitudes ← lista vacía
Definir dirección ← "ninguna" // puede ser "subiendo", "bajando" o "ninguna"

MIENTRAS el sistema esté encendido HACER

    Revisar_solicitudes_externas()
    Revisar_solicitudes_internas()

    SI hay solicitudes ENTONCES
        Seleccionar_próximo_piso()
        Mover_elevador_al_piso(próximo_piso)
        Abrir_puertas()
        Esperar(5 segundos)
        Cerrar_puertas()
        Eliminar_solicitud(piso_actual)
    SINO
        Esperar(1 segundo)
    FIN SI

FIN MIENTRAS

FIN


PROCEDIMIENTO Revisar_solicitudes_externas()
    // Simula la lectura de botones presionados en cada piso
    SI se presiona un botón en un piso
        Agregar piso a solicitudes
    FIN SI
FIN PROCEDIMIENTO


PROCEDIMIENTO Revisar_solicitudes_internas()
    // Simula la lectura de botones dentro del elevador
    SI se presiona un botón dentro del elevador
        Agregar piso a solicitudes
    FIN SI
FIN PROCEDIMIENTO


PROCEDIMIENTO Seleccionar_próximo_piso()
    // Lógica simple para determinar el siguiente piso más cercano
    Ordenar solicitudes según dirección y cercanía al piso_actual
    próximo_piso ← primer elemento de solicitudes
FIN PROCEDIMIENTO


PROCEDIMIENTO Mover_elevador_al_piso(piso_destino)
    MIENTRAS piso_actual ≠ piso_destino HACER
        SI piso_actual < piso_destino ENTONCES
            piso_actual ← piso_actual + 1
            dirección ← "subiendo"
        SINO
            piso_actual ← piso_actual - 1
            dirección ← "bajando"
        FIN SI
        Esperar(1 segundo) // tiempo de viaje entre pisos
    FIN MIENTRAS
    dirección ← "ninguna"
FIN PROCEDIMIENTO


PROCEDIMIENTO Abrir_puertas()
    Mostrar("Puertas abiertas en piso " + piso_actual)
FIN PROCEDIMIENTO


PROCEDIMIENTO Cerrar_puertas()
    Mostrar("Puertas cerradas")
FIN PROCEDIMIENTO


PROCEDIMIENTO Eliminar_solicitud(piso)
    Eliminar piso de la lista de solicitudes
FIN PROCEDIMIENTO
