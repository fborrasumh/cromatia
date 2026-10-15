# CromatIA

Simulador de HPLC con modelo físico y base de compuestos ampliable. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/cromatia/

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- **Muestra:** más de 200 compuestos de referencia en 15 categorías (fármacos, plaguicidas, micotoxinas, azúcares, ácidos orgánicos, vitaminas, cannabinoides, polifenoles, PFAS, proteínas, etc.) y 14 aplicaciones de ejemplo con método de partida.
- **Cromatógrafo:** 4 instrumentos (HPLC binaria y cuaternaria, 600 bar, UHPLC), 9 disolventes, 14 aditivos y tampones, programa isocrático o de gradiente, flujo, temperatura y disolvente de la muestra.
- **Columnas:** 35 químicas genéricas en 6 modos (fase inversa, normal, HILIC, intercambio de ligando/exclusión iónica, intercambio iónico y exclusión por tamaño), con dimensiones y partícula a elegir, estado de la columna y asesor de equivalencia (Fs de Snyder-Dolan).
- **Detectores:** UV, DAD (con pureza espectral), fluorescencia, índice de refracción, ELSD, masas (barrido y SIM; aductos, isótopos, carga múltiple), MS/MS (MRM) y electroquímico.
- **Modelo físico:** retención por Snyder (LSS) con logD (Henderson-Hasselbalch) y modelo de sustracción hidrofóbica; van 't Hoff; gradiente integrado numéricamente con volumen de retardo; van Deemter con Wilke-Chang/Young; presión por Darcy con viscosidad de la mezcla; picos con cola o adelanto (silanoles, sobrecarga, disolvente de inyección, columna degradada).
- **Resultados:** tR, k, N, Rs, α, factor de cola, área, altura, S/N y LOD medidos sobre la señal; aptitud del sistema orientativa; diagnóstico en tiempo real (sobrepresión, pH fuera de rango, tampones, compatibilidad detector–fase móvil, coeluciones…); espectros UV y de masas al pulsar un pico.
- **Mapa de resolución (QbD):** dos factores (%B, duración del gradiente, temperatura, pH, flujo) con Rs del par crítico por celda; se aplica al método con un clic.
- **Compuestos propios:** PubChem aporta fórmula, masa y XLogP; la IA propone el resto; el código comprueba fórmula, masa, rangos y coherencia. Importación y exportación en JSON y CSV.
- **Docencia:** 6 retos de serie (todos comprobados como resolubles), retos propios del profesorado compartibles como ficha JSON o como página web, y revisión de entregas con recálculo del método y huella SHA-256.
- **Exportaciones:** resultados y cromatograma en CSV, informe en Word, método en JSON; métodos guardados en el navegador.

## Cómo se usa la IA

La simulación no usa IA. La IA solo interviene, si se pide, para proponer propiedades de un compuesto nuevo (con la propia clave de OpenAI, Google Gemini o Anthropic Claude, guardada solo en el navegador). Lo que propone se marca como «IA · revisar» y no se guarda sin revisión de la persona. No hace falta servidor.

## Privacidad

La simulación, los métodos, los compuestos propios, los retos y las entregas se guardan solo en el navegador (IndexedDB). Sale únicamente el nombre (y la fórmula, si se escribe) de un compuesto: hacia el proveedor de IA al pulsar «Proponer con IA» (con aviso previo y muestra de lo que se envía) o hacia PubChem (NIH) al pulsar «Buscar en PubChem».

## Límites

- Los modelos son simplificaciones y los datos de la base son **aproximados** (literatura general y estimaciones). Sirven para docencia y desarrollo orientativo, no para validar métodos.
- Las columnas son genéricas, con valores representativos del modelo de sustracción hidrofóbica; **no** corresponden a productos comerciales.
- Las transiciones MRM sin datos propios son genéricas e ilustrativas (se marcan con *).
- El mapa de resolución usa anchuras calculadas (4σ): su Rs puede diferir ligeramente de la medida en el cromatograma.
- La huella SHA-256 de las entregas detecta ediciones, pero no es una prueba criptográfica.
- La consulta a PubChem se ha probado con respuestas simuladas, no contra el servicio real.

## Autoría

Fernando Borrás Rocher y Enrique Barrajón Catalán (Universidad Miguel Hernández de Elche).


ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Enrique Barrajón Catalán [0000-0001-8113-0795](https://orcid.org/0000-0001-8113-0795)

## Cómo citar

Borrás Rocher, F. y Barrajón Catalán, E. (2026). *CromatIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
