# AgentSM 🇸🇻

Prototipo de asistente de actividades para San Miguel, El Salvador. Toda la aplicación está en `index.html`: Vue 3 Composition API y Tailwind CSS por CDN, sin claves ni backend.

## Visualizar

Abrí `index.html` directamente en un navegador con acceso a Internet, o usá el entorno existente:

```bash
npm run dev
```

`npm run build` genera `dist/index.html`; `npm run preview` permite servirlo. Los CDN, las fuentes, el clima y Google Maps necesitan conexión. Los archivos anteriores de `src/` ya no son utilizados por esta página.

## Funciones

- Chat por reglas locales: reconoce presupuestos como «Tengo $8» y preferencias como café, playa, cine o cultura. También ofrece controles explícitos de presupuesto y actividad.
- Seis lugares con costos orientativos por persona. Las recomendaciones respetan el costo mínimo y aclaran si el presupuesto no cubre todo el rango.
- Clima de Open-Meteo para 13.4833, -88.1833; temperatura, humedad, precipitación y códigos WMO. Consulta inicial, actualización cada diez minutos, botón manual y tiempo límite de doce segundos.
- Pronóstico horario adicional: muestra el máximo de probabilidad de precipitación de las tres horas siguientes; desde 60% indica posible lluvia. No interpreta nubes como predicción de lluvia.
- Si llueve o hay riesgo de lluvia, prioriza interiores. Si falla la API, lo informa y recomienda únicamente por presupuesto y gustos.
- Tarjetas y enlaces de búsqueda en Maps. Los filtros agrupan por costo mínimo: menos de $10, desde $10 hasta menos de $20 y desde $20. $20 pertenece al último grupo para evitar huecos.

## Validación

Compilación Vite y comprobación de la plantilla Vue realizadas. Lógica comprobada con respuestas meteorológicas simuladas: sol, lluvia, posible lluvia, error de conexión, presupuesto insuficiente, alternativa interior, reconocimiento de texto y filtros. Falta validación visual en navegador y comprobación de la API desde la conexión del usuario.

Fuente meteorológica y códigos: [documentación de Open-Meteo](https://open-meteo.com/en/docs). Lugares y estimaciones proporcionados en los requisitos; no son tarifas verificadas ni disponibilidad en tiempo real. El clima consultado corresponde a San Miguel y no garantiza las condiciones en Playa El Cuco.
