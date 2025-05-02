# Repo-elevador.

Integrantes :
Flores Jaime Andrea Margarita 
GUZMAN RODRIGUEZ INGRID JULIETA

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
