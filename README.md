<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Propuesta de Proyecto - Sistema de Gestión de Mantenimiento</title>
    <style>
        @page {
            size: A4;
            margin: 2.5cm;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Calibri', 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f5f5f5;
            padding: 20px;
        }
        
        .document {
            max-width: 21cm;
            margin: 0 auto;
            background: white;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
        }
        
        .page {
            padding: 2.5cm;
            min-height: 29.7cm;
            page-break-after: always;
            background: white;
        }
        
        /* PORTADA */
        .cover-page {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            min-height: 29.7cm;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 2.5cm;
        }
        
        .cover-page h1 {
            font-size: 42px;
            font-weight: bold;
            margin-bottom: 30px;
            text-transform: uppercase;
            letter-spacing: 2px;
            line-height: 1.3;
        }
        
        .cover-page .subtitle {
            font-size: 28px;
            margin-bottom: 60px;
            opacity: 0.95;
        }
        
        .cover-page .project-info {
            margin-top: 80px;
            font-size: 18px;
            line-height: 2;
        }
        
        .cover-page .project-info div {
            margin: 10px 0;
        }
        
        /* ÍNDICE */
        .toc {
            margin-top: 40px;
        }
        
        .toc h2 {
            font-size: 24px;
            color: #667eea;
            margin-bottom: 30px;
            border-bottom: 3px solid #667eea;
            padding-bottom: 10px;
        }
        
        .toc-item {
            display: flex;
            justify-content: space-between;
            padding: 12px 0;
            border-bottom: 1px dotted #ddd;
            cursor: pointer;
            transition: background 0.3s;
        }
        
        .toc-item:hover {
            background: #f7fafc;
            padding-left: 10px;
        }
        
        .toc-item.level-1 {
            font-weight: bold;
            font-size: 16px;
            color: #2d3748;
        }
        
        .toc-item.level-2 {
            padding-left: 30px;
            font-size: 14px;
            color: #4a5568;
        }
        
        /* ENCABEZADOS */
        h1 {
            font-size: 32px;
            color: #2d3748;
            margin-bottom: 20px;
            border-bottom: 3px solid #667eea;
            padding-bottom: 10px;
        }
        
        h2 {
            font-size: 24px;
            color: #667eea;
            margin-top: 30px;
            margin-bottom: 15px;
            border-left: 5px solid #667eea;
            padding-left: 15px;
        }
        
        h3 {
            font-size: 18px;
            color: #4a5568;
            margin-top: 20px;
            margin-bottom: 10px;
            font-weight: 600;
        }
        
        h4 {
            font-size: 16px;
            color: #718096;
            margin-top: 15px;
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        /* PÁRRAFOS */
        p {
            margin-bottom: 15px;
            text-align: justify;
        }
        
        /* LISTAS */
        ul, ol {
            margin-left: 25px;
            margin-bottom: 15px;
        }
        
        li {
            margin-bottom: 8px;
        }
        
        /* TABLAS */
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
            font-size: 14px;
        }
        
        thead {
            background: #667eea;
            color: white;
        }
        
        th {
            padding: 12px;
            text-align: left;
            font-weight: 600;
        }
        
        td {
            padding: 10px 12px;
            border: 1px solid #e2e8f0;
        }
        
        tbody tr:nth-child(even) {
            background: #f7fafc;
        }
        
        tbody tr:hover {
            background: #edf2f7;
        }
        
        /* CAJAS DESTACADAS */
        .info-box {
            background: #e6f3ff;
            border-left: 5px solid #4299e1;
            padding: 15px;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .warning-box {
            background: #fff5e6;
            border-left: 5px solid #f6ad55;
            padding: 15px;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .success-box {
            background: #e6ffe6;
            border-left: 5px solid #48bb78;
            padding: 15px;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .highlight {
            background: #fef5e7;
            padding: 2px 6px;
            border-radius: 3px;
            font-weight: 600;
        }
        
        /* RESUMEN EJECUTIVO */
        .executive-summary {
            background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
            padding: 25px;
            border-radius: 10px;
            margin: 20px 0;
        }
        
        /* COSTOS */
        .cost-summary {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin: 20px 0;
        }
        
        .cost-card {
            background: white;
            border: 2px solid #e2e8f0;
            border-radius: 10px;
            padding: 20px;
            text-align: center;
        }
        
        .cost-card h4 {
            color: #667eea;
            margin-bottom: 10px;
        }
        
        .cost-card .amount {
            font-size: 28px;
            font-weight: bold;
            color: #2d3748;
        }
        
        /* PIE DE PÁGINA */
        .footer {
            margin-top: 40px;
            padding-top: 20px;
            border-top: 2px solid #e2e8f0;
            text-align: center;
            font-size: 12px;
            color: #718096;
        }
        
        /* GANTT SIMPLIFICADO */
        .gantt-simple {
            margin: 20px 0;
        }
        
        .gantt-bar {
            background: #667eea;
            color: white;
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
            font-size: 14px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .gantt-bar.phase-1 { background: #667eea; }
        .gantt-bar.phase-2 { background: #f5576c; }
        .gantt-bar.phase-3 { background: #4facfe; }
        .gantt-bar.phase-4 { background: #43e97b; }
        .gantt-bar.phase-5 { background: #fa709a; }
        .gantt-bar.phase-6 { background: #330867; }
        .gantt-bar.phase-7 { background: #48bb78; }
        .gantt-bar.phase-8 { background: #ff9a9e; }
        
        /* BADGES */
        .badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
            margin-right: 10px;
        }
        
        .badge-critical { background: #fc8181; color: white; }
        .badge-high { background: #f6ad55; color: white; }
        .badge-medium { background: #4299e1; color: white; }
        .badge-low { background: #48bb78; color: white; }
        
        @media print {
            body {
                background: white;
                padding: 0;
            }
            .document {
                box-shadow: none;
            }
            .page {
                page-break-after: always;
            }
        }
    </style>
</head>
<body>
    <div class="document">
        <!-- PORTADA -->
        <div class="page cover-page">
            <h1>Propuesta de Proyecto</h1>
            <div class="subtitle">Sistema de Gestión de Mantenimiento de Flota Vehicular</div>
            
            <div style="margin: 60px 0; font-size: 72px;">🚛</div>
            
            <div class="project-info">
                <div><strong>Cliente:</strong> [Nombre de la Empresa]</div>
                <div><strong>Fecha:</strong> Octubre 2025</div>
                <div><strong>Versión:</strong> 1.0</div>
                <div><strong>Preparado por:</strong> Equipo de Análisis de Sistemas</div>
            </div>
        </div>

        <!-- ÍNDICE -->
        <div class="page">
            <div class="toc">
                <h2>📑 ÍNDICE</h2>
                
                <div class="toc-item level-1">
                    <span>1. RESUMEN EJECUTIVO</span>
                    <span>3</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>2. ANÁLISIS DE SITUACIÓN ACTUAL</span>
                    <span>4</span>
                </div>
                <div class="toc-item level-2">
                    <span>2.1 Problemática Identificada</span>
                    <span>4</span>
                </div>
                <div class="toc-item level-2">
                    <span>2.2 Hardware y Software Actual</span>
                    <span>4</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>3. OBJETIVOS DEL PROYECTO</span>
                    <span>5</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>4. ALCANCE FUNCIONAL</span>
                    <span>6</span>
                </div>
                <div class="toc-item level-2">
                    <span>4.1 Módulos del Sistema</span>
                    <span>6</span>
                </div>
                <div class="toc-item level-2">
                    <span>4.2 Usuarios del Sistema</span>
                    <span>7</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>5. REQUERIMIENTOS</span>
                    <span>8</span>
                </div>
                <div class="toc-item level-2">
                    <span>5.1 Requerimientos Funcionales</span>
                    <span>8</span>
                </div>
                <div class="toc-item level-2">
                    <span>5.2 Requerimientos No Funcionales</span>
                    <span>9</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>6. ANÁLISIS DE HARDWARE</span>
                    <span>10</span>
                </div>
                <div class="toc-item level-2">
                    <span>6.1 Hardware Actual</span>
                    <span>10</span>
                </div>
                <div class="toc-item level-2">
                    <span>6.2 Hardware Requerido</span>
                    <span>10</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>7. ANÁLISIS DE SOFTWARE</span>
                    <span>12</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>8. PRESUPUESTO DETALLADO</span>
                    <span>13</span>
                </div>
                <div class="toc-item level-2">
                    <span>8.1 Costos de Hardware</span>
                    <span>13</span>
                </div>
                <div class="toc-item level-2">
                    <span>8.2 Costos de Software</span>
                    <span>14</span>
                </div>
                <div class="toc-item level-2">
                    <span>8.3 Inversión Total</span>
                    <span>15</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>9. CRONOGRAMA DE IMPLEMENTACIÓN</span>
                    <span>16</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>10. ANÁLISIS DE RIESGOS</span>
                    <span>18</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>11. PLAN DE IMPLEMENTACIÓN</span>
                    <span>19</span>
                </div>
                
                <div class="toc-item level-1">
                    <span>12. CONCLUSIONES Y RECOMENDACIONES</span>
                    <span>20</span>
                </div>
            </div>
        </div>

        <!-- RESUMEN EJECUTIVO -->
        <div class="page">
            <h1>1. RESUMEN EJECUTIVO</h1>
            
            <div class="executive-summary">
                <p style="font-size: 16px; margin-bottom: 20px;">
                    El presente documento detalla la propuesta para el desarrollo e implementación de un <strong>Sistema de Gestión de Mantenimiento de Flota Vehicular</strong>, diseñado para automatizar y optimizar los procesos de seguimiento, programación y control de mantenimientos en su empresa.
                </p>
            </div>

            <h2>📊 Datos Clave del Proyecto</h2>
            
            <div class="cost-summary">
                <div class="cost-card">
                    <h4>Inversión Inicial</h4>
                    <div class="amount">$39,065</div>
                    <p style="font-size: 12px; margin-top: 10px;">Hardware + Software</p>
                </div>
                <div class="cost-card">
                    <h4>Inversión Total Año 1</h4>
                    <div class="amount">$46,905</div>
                    <p style="font-size: 12px; margin-top: 10px;">Incluye costos operativos</p>
                </div>
                <div class="cost-card">
                    <h4>Duración del Proyecto</h4>
                    <div class="amount">25 semanas</div>
                    <p style="font-size: 12px; margin-top: 10px;">Aproximadamente 6 meses</p>
                </div>
                <div class="cost-card">
                    <h4>Fecha Go-Live</h4>
                    <div class="amount">Mayo 2026</div>
                    <p style="font-size: 12px; margin-top: 10px;">Sistema en producción</p>
                </div>
            </div>

            <h2>🎯 Beneficios Esperados</h2>
            <ul>
                <li><strong>Optimización del tiempo de servicio:</strong> Reducción del 40% en tiempos de gestión de mantenimientos</li>
                <li><strong>Reducción de costos operativos:</strong> Mejor control de inventario y proveedores</li>
                <li><strong>Alertas automáticas:</strong> Sistema proactivo que notifica mantenimientos preventivos</li>
                <li><strong>Trazabilidad completa:</strong> Historial detallado de cada vehículo y servicio realizado</li>
                <li><strong>Mejora en la toma de decisiones:</strong> Reportes y dashboards con información en tiempo real</li>
                <li><strong>Acceso multi-usuario:</strong> Mecánicos, administrativos e inventario trabajando en la misma plataforma</li>
            </ul>

            <div class="success-box">
                <strong>Retorno de Inversión (ROI) Estimado:</strong> Se espera recuperar la inversión en 18-24 meses mediante la reducción de costos operativos, mejor gestión de inventario y optimización de tiempos.
            </div>
        </div>

        <!-- ANÁLISIS DE SITUACIÓN ACTUAL -->
        <div class="page">
            <h1>2. ANÁLISIS DE SITUACIÓN ACTUAL</h1>

            <h2>2.1 Problemática Identificada</h2>
            
            <p>
                Actualmente, la empresa gestiona el mantenimiento de su flota vehicular de manera completamente <span class="highlight">manual</span>, utilizando hojas de cálculo Excel y formularios en papel. Esta metodología presenta las siguientes limitaciones críticas:
            </p>

            <table>
                <thead>
                    <tr>
                        <th>Área Afectada</th>
                        <th>Problema</th>
                        <th>Impacto</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Seguimiento de Mantenimientos</strong></td>
                        <td>No hay alertas automáticas para mantenimientos preventivos</td>
                        <td>Pérdida de garantías, daños mayores</td>
                    </tr>
                    <tr>
                        <td><strong>Control de Inventario</strong></td>
                        <td>Formularios en papel, sin trazabilidad digital</td>
                        <td>Pérdidas, falta de stock crítico</td>
                    </tr>
                    <tr>
                        <td><strong>Gestión de Información</strong></td>
                        <td>Datos dispersos en múltiples archivos Excel</td>
                        <td>Duplicación de información, errores</td>
                    </tr>
                    <tr>
                        <td><strong>Reportes y Análisis</strong></td>
                        <td>Generación manual de reportes consume mucho tiempo</td>
                        <td>Decisiones sin información actualizada</td>
                    </tr>
                    <tr>
                        <td><strong>Acceso a Información</strong></td>
                        <td>Mecánicos no tienen acceso al sistema</td>
                        <td>Retrasos en actualizaciones, errores de transcripción</td>
                    </tr>
                    <tr>
                        <td><strong>Trazabilidad</strong></td>
                        <td>Historial incompleto de servicios</td>
                        <td>Imposible auditar o analizar tendencias</td>
                    </tr>
                </tbody>
            </table>

            <h2>2.2 Hardware y Software Actual</h2>

            <div class="warning-box">
                <strong>⚠️ ESTADO CRÍTICO:</strong> La empresa no cuenta con infraestructura tecnológica dedicada para gestión de mantenimientos.
            </div>

            <h3>Hardware Existente</h3>
            <ul>
                <li>Computadoras de escritorio básicas (uso administrativo general)</li>
                <li>No hay servidores dedicados</li>
                <li>No hay dispositivos móviles para el taller</li>
                <li>No hay equipos para control de inventario (lectores de código de barras, etc.)</li>
                <li>No hay infraestructura de red estructurada</li>
            </ul>

            <h3>Software Actual</h3>
            <ul>
                <li>Microsoft Excel para registro de vehículos y mantenimientos</li>
                <li>Formularios impresos para órdenes de trabajo</li>
                <li>Sin sistema de alertas o notificaciones</li>
                <li>Sin base de datos centralizada</li>
            </ul>

            <h3>Proceso Actual de Trabajo</h3>
            <ol>
                <li>Jefe de Mecánicos anota mantenimientos manualmente</li>
                <li>Se llena formulario en papel para solicitar repuestos</li>
                <li>Encargado de inventario despacha repuestos manualmente</li>
                <li>Mecánico realiza el servicio sin acceso a historial digital</li>
                <li>Se actualiza Excel después del servicio (con posibles errores u omisiones)</li>
                <li>No hay alertas cuando se acerca fecha de mantenimiento preventivo</li>
            </ol>
        </div>

        <!-- OBJETIVOS DEL PROYECTO -->
        <div class="page">
            <h1>3. OBJETIVOS DEL PROYECTO</h1>

            <h2>3.1 Objetivo General</h2>
            <div class="info-box">
                Desarrollar e implementar un sistema integral de gestión de mantenimiento de flota vehicular que automatice los procesos de seguimiento, programación y control, permitiendo optimizar tiempos, reducir costos operativos y mejorar la toma de decisiones mediante información centralizada y en tiempo real.
            </div>

            <h2>3.2 Objetivos Específicos</h2>

            <h3>Operacionales</h3>
            <ul>
                <li>Automatizar el registro y seguimiento de vehículos con su información técnica completa</li>
                <li>Implementar sistema de alertas automáticas para mantenimientos preventivos y correctivos</li>
                <li>Reducir el tiempo de gestión de mantenimientos en un 40%</li>
                <li>Eliminar errores de transcripción manual de información</li>
                <li>Centralizar toda la información de la flota en una base de datos única</li>
            </ul>

            <h3>Financieros</h3>
            <ul>
                <li>Reducir costos operativos mediante mejor planificación de mantenimientos</li>
                <li>Optimizar el control de inventario de repuestos</li>
                <li>Mejorar negociación con proveedores mediante análisis de costos históricos</li>
                <li>Evitar gastos mayores por falta de mantenimientos preventivos</li>
            </ul>

            <h3>Tecnológicos</h3>
            <ul>
                <li>Implementar infraestructura cloud para acceso remoto y escalabilidad</li>
                <li>Proporcionar aplicación móvil para mecánicos en taller</li>
                <li>Establecer sistema de respaldos automáticos de información</li>
                <li>Crear plataforma web responsive accesible desde cualquier dispositivo</li>
            </ul>

            <h3>Organizacionales</h3>
            <ul>
                <li>Democratizar acceso a información entre todos los roles (admin, mecánicos, inventario)</li>
                <li>Establecer flujos de trabajo digitales documentados</li>
                <li>Generar cultura de trabajo basada en datos y métricas</li>
                <li>Mejorar comunicación entre áreas (taller, inventario, administración)</li>
            </ul>

            <h2>3.3 Indicadores de Éxito (KPIs)</h2>

            <table>
                <thead>
                    <tr>
                        <th>KPI</th>
                        <th>Meta</th>
                        <th>Medición</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tiempo de gestión de mantenimiento</td>
                        <td>Reducción del 40%</td>
                        <td>Tiempo promedio desde solicitud hasta cierre</td>
                    </tr>
                    <tr>
                        <td>Cumplimiento de mantenimientos preventivos</td>
                        <td>95% en tiempo</td>
                        <td>% de mantenimientos realizados antes de fecha límite</td>
                    </tr>
                    <tr>
                        <td>Precisión de inventario</td>
                        <td>98% de exactitud</td>
                        <td>Coincidencia entre sistema y stock físico</td>
                    </tr>
                    <tr>
                        <td>Adopción del sistema</td>
                        <td>100% de usuarios</td>
                        <td>% de usuarios activos vs. usuarios totales</td>
                    </tr>
                    <tr>
                        <td>Tiempo promedio de respuesta a incidencias</td>
                        <td>< 24 horas</td>
                        <td>Tiempo desde reporte hasta asignación de mecánico</td>
                    </tr>
                    <tr>
                        <td>Reducción de costos operativos</td>
                        <td>15-20%</td>
                        <td>Comparación año anterior vs. año con sistema</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- ALCANCE FUNCIONAL -->
        <div class="page">
            <h1>4. ALCANCE FUNCIONAL</h1>

            <h2>4.1 Módulos del Sistema</h2>

            <h3>Módulo 1: Gestión de Vehículos</h3>
            <p><strong>Descripción:</strong> Registro completo de la flota vehicular con toda su información técnica y documentación.</p>
            <p><strong>Funcionalidades:</strong></p>
            <ul>
                <li>Registro de vehículos (placa, marca, modelo, año, VIN, etc.)</li>
                <li>Información técnica detallada (motor, transmisión, capacidades)</li>
                <li>Documentación digital (SOAT, revisión técnica, pólizas)</li>
                <li>Historial completo de cada vehículo</li>
                <li>Estado actual del vehículo (operativo, en mantenimiento, fuera de servicio)</li>
                <li>Asignación a unidades de negocio o conductores</li>
            </ul>

            <h3>Módulo 2: Programación de Mantenimientos</h3>
            <p><strong>Descripción:</strong> Sistema inteligente para programar y controlar mantenimientos preventivos y correctivos.</p>
            <p><strong>Funcionalidades:</strong></p>
            <ul>
                <li>Creación de planes de mantenimiento preventivo por tipo de vehículo</li>
                <li>Programación por fecha o kilometraje</li>
                <li>Registro de mantenimientos correctivos (reparaciones emergentes)</li>
                <li>Sistema de alertas automáticas (email, dashboard, notificaciones móviles)</li>
                <li>Priorización de mantenimientos (crítico, alto, medio, bajo)</li>
                <li>Calendario visual de mantenimientos programados</li>
            </ul>

            <h3>Módulo 3: Gestión de Recursos (Mecánicos y Talleres)</h3>
            <p><strong>Descripción:</strong> Asignación y control de recursos humanos y proveedores externos.</p>
            <p><strong>Funcionalidades:</strong></p>
            <ul>
                <li>Catálogo de mecánicos internos con especialidades</li>
                <li>Catálogo de talleres externos (proveedores)</li>
                <li>Asignación automática o manual de recursos</li>
                <li>Control de disponibilidad y carga de trabajo</li>
                <li>Evaluación de desempeño (tiempo, calidad, costos)</li>
                <li>Gestión de órdenes de trabajo</li>
            </ul>

            <h3>Módulo 4: Control de Inventario de Repuestos</h3>
            <p><strong>Descripción:</strong> Gestión completa del inventario de repuestos y consumibles.</p>
            <p><strong>Funcionalidades:</strong></p>
            <ul>
                <li>Catálogo de repuestos con códigos de barras</li>
                <li>Control de entradas y salidas de inventario</li>
                <li>Órdenes de requerimiento digitales (Jefe Mecánicos → Bodega)</li>
                <li>Alertas de stock mínimo</li>
                <li>Trazabilidad: qué repuesto se usó en qué vehículo</li>
                <li>Valorización de inventario</li>
                <li>Integración con sistema de compras (futuro)</li>
            </ul>

            <h3>Módulo 5: Reportes y Analítica</h3>
            <p><strong>Descripción:</strong> Generación de reportes y dashboards para análisis y toma de decisiones.</p>
            <p><strong>Funcionalidades:</strong></p>
            <ul>
                <li>Reporte de historial por vehículo (servicios, costos, repuestos)</li>
                <li>Reporte consolidado de flota</li>
                <li>Análisis de costos (por vehículo, por tipo de mantenimiento, por período)</li>
                <li>Dashboard con KPIs principales</li>
                <li>Gráficos de tendencias y comparativos</li>
                <li>Exportación a Excel y PDF</li>
                <li>Reportes programados automáticos</li>
            </ul>

            <h3>Módulo 6: Administración y Seguridad</h3>
            <p><strong>Descripción:</strong> Gestión de usuarios, permisos y configuración del sistema.</p>
            <p><strong>Funcionalidades:</strong></p>
            <ul>
                <li>Gestión de usuarios y contraseñas</li>
                <li>Control de roles y permisos</li>
                <li>Auditoría de acciones (quién hizo qué y cuándo)</li>
                <li>Configuración de parámetros del sistema</li>
                <li>Gestión de respaldos</li>
            </ul>

            <h2>4.2 Usuarios del Sistema</h2>

            <table>
                <thead>
                    <tr>
                        <th>Rol</th>
                        <th>Cantidad Est.</th>
                        <th>Acceso Principal</th>
                        <th>Dispositivos</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Administrador del Sistema</strong></td>
                        <td>1-2</td>
                        <td>Acceso completo, configuración, reportes ejecutivos</td>
                        <td>PC de escritorio</td>
                    </tr>
                    <tr>
                        <td><strong>Jefe de Mecánicos</strong></td>
                        <td>1-2</td>
                        <td>Programación, asignación, órdenes de repuestos</td>
                        <td>PC/Laptop/Tablet</td>
                    </tr>
                    <tr>
                        <td><strong>Mecánicos</strong></td>
                        <td>5-10</td>
                        <td>Consulta órdenes, registro de servicios, fotos</td>
                        <td>Tablet/Smartphone</td>
                    </tr>
                    <tr>
                        <td><strong>Encargado de Inventario</strong></td>
                        <td>1-2</td>
                        <td>Control stock, despachos, órdenes de compra</td>
                        <td>PC + Lector barras</td>
                    </tr>
                    <tr>
                        <td><strong>Personal Administrativo</strong></td>
                        <td>2-5</td>
                        <td>Consulta reportes, análisis de costos</td>
                        <td>PC de escritorio</td>
                    </tr>
                </tbody>
            </table>

            <div class="info-box">
                <strong>Total de usuarios estimados:</strong> 10-22 usuarios concurrentes. El sistema está diseñado para escalar hasta 50+ usuarios sin problemas de rendimiento.
            </div>
        </div>

        <!-- REQUERIMIENTOS -->
        <div class="page">
            <h1>5. REQUERIMIENTOS</h1>

            <h2>5.1 Requerimientos Funcionales</h2>

            <table>
                <thead>
                    <tr>
                        <th style="width: 15%;">ID</th>
                        <th style="width: 15%;">Prioridad</th>
                        <th>Descripción</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>RF-001</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe permitir registrar vehículos con información técnica completa (placa, marca, modelo, año, VIN, motor, etc.)</td>
                    </tr>
                    <tr>
                        <td><strong>RF-002</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe permitir programar mantenimientos preventivos basados en fecha o kilometraje</td>
                    </tr>
                    <tr>
                        <td><strong>RF-003</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe generar alertas automáticas cuando se acerque fecha de mantenimiento programado</td>
                    </tr>
                    <tr>
                        <td><strong>RF-004</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe permitir registrar mantenimientos correctivos (emergencias y reparaciones)</td>
                    </tr>
                    <tr>
                        <td><strong>RF-005</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe permitir asignar mecánicos internos o talleres externos a cada orden de trabajo</td>
                    </tr>
                    <tr>
                        <td><strong>RF-006</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe gestionar un catálogo de talleres externos (proveedores) con su información de contacto</td>
                    </tr>
                    <tr>
                        <td><strong>RF-007</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe permitir crear órdenes de requerimiento de repuestos desde el módulo de mantenimientos</td>
                    </tr>
                    <tr>
                        <td><strong>RF-008</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe registrar salidas de inventario con aprobación del encargado de bodega</td>
                    </tr>
                    <tr>
                        <td><strong>RF-009</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe controlar stock de repuestos y generar alertas cuando llegue a stock mínimo</td>
                    </tr>
                    <tr>
                        <td><strong>RF-010</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe generar reporte histórico por vehículo con todos los mantenimientos, costos y repuestos utilizados</td>
                    </tr>
                    <tr>
                        <td><strong>RF-011</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe generar reportes consolidados de costos (por vehículo, por tipo de servicio, por período)</td>
                    </tr>
                    <tr>
                        <td><strong>RF-012</strong></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>El sistema debe permitir gestionar usuarios con diferentes roles y permisos (Admin, Jefe, Mecánico, Inventario, Consulta)</td>
                    </tr>
                    <tr>
                        <td><strong>RF-013</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe permitir que mecánicos registren servicios realizados desde dispositivos móviles (tablets/smartphones)</td>
                    </tr>
                    <tr>
                        <td><strong>RF-014</strong></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>El sistema debe permitir adjuntar fotografías y documentos a cada orden de trabajo</td>
                    </tr>
                    <tr>
                        <td><strong>RF-015</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe mantener un historial completo de cambios (auditoría): quién hizo qué y cuándo</td>
                    </tr>
                    <tr>
                        <td><strong>RF-016</strong></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>El sistema debe permitir exportar reportes a formato Excel y PDF</td>
                    </tr>
                    <tr>
                        <td><strong>RF-017</strong></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>El sistema debe enviar notificaciones por correo electrónico para eventos importantes (alertas, asignaciones, etc.)</td>
                    </tr>
                    <tr>
                        <td><strong>RF-018</strong></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>El sistema debe mostrar un dashboard visual con KPIs principales (vehículos en servicio, mantenimientos pendientes, costos del mes, etc.)</td>
                    </tr>
                </tbody>
            </table>

            <h2>5.2 Requerimientos No Funcionales</h2>

            <table>
                <thead>
                    <tr>
                        <th style="width: 25%;">Categoría</th>
                        <th>Requerimiento</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>RNF-001: Usabilidad</strong></td>
                        <td>La interfaz debe ser intuitiva y fácil de usar para usuarios con nivel técnico básico. Máximo 2 horas de capacitación para usuarios finales.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-002: Disponibilidad</strong></td>
                        <td>El sistema debe estar disponible 24/7 con un uptime del 99.5% (máximo 3.65 horas de caída al mes).</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-003: Rendimiento</strong></td>
                        <td>Tiempo de respuesta máximo de 3 segundos para consultas normales y 10 segundos para reportes complejos.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-004: Seguridad</strong></td>
                        <td>Todos los accesos deben requerir autenticación. Conexiones HTTPS encriptadas. Respaldos automáticos diarios.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-005: Escalabilidad</strong></td>
                        <td>El sistema debe soportar el crecimiento de la flota hasta 500 vehículos y 50 usuarios concurrentes sin degradación de rendimiento.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-006: Compatibilidad</strong></td>
                        <td>Acceso desde navegadores modernos (Chrome, Firefox, Safari, Edge). App móvil compatible con Android 8+ e iOS 12+.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-007: Respaldo</strong></td>
                        <td>Respaldo automático diario con retención de 30 días. Respaldo incremental cada 6 horas.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-008: Mantenibilidad</strong></td>
                        <td>Código documentado y modular para facilitar mantenimiento futuro. Uso de frameworks y tecnologías estándar del mercado.</td>
                    </tr>
                    <tr>
                        <td><strong>RNF-009: Soporte</strong></td>
                        <td>Soporte técnico durante horario laboral (8am-6pm) con respuesta máxima de 4 horas para incidencias críticas.</td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- ANÁLISIS DE HARDWARE -->
        <div class="page">
            <h1>6. ANÁLISIS DE HARDWARE</h1>

            <h2>6.1 Hardware Actual</h2>

            <div class="warning-box">
                <strong>⚠️ SITUACIÓN ACTUAL:</strong> La empresa NO cuenta con hardware dedicado para el sistema de gestión de mantenimientos. Todo el proceso es manual utilizando Excel en computadoras de oficina estándar.
            </div>

            <p><strong>Equipamiento existente (estimado):</strong></p>
            <ul>
                <li>❌ Sin servidores dedicados</li>
                <li>❌ Sin infraestructura de red estructurada</li>
                <li>❌ Sin dispositivos móviles para taller</li>
                <li>❌ Sin equipos para control de inventario</li>
                <li>⚠️ Posiblemente 3-5 PCs de escritorio para tareas administrativas generales</li>
            </ul>

            <h2>6.2 Hardware Requerido</h2>

            <h3>6.2.1 Infraestructura de Servidor (Opción Recomendada: Cloud)</h3>

            <table>
                <thead>
                    <tr>
                        <th>Componente</th>
                        <th>Especificación</th>
                        <th>Cantidad</th>
                        <th>Costo Mensual</th>
                        <th>Costo Anual</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Cloud Server</td>
                        <td>4 vCPU, 16GB RAM, 200GB SSD</td>
                        <td>1</td>
                        <td>$80-150</td>
                        <td>$960-1,800</td>
                    </tr>
                    <tr>
                        <td>Almacenamiento Cloud</td>
                        <td>500GB para respaldos</td>
                        <td>1</td>
                        <td>$20-40</td>
                        <td>$240-480</td>
                    </tr>
                    <tr>
                        <td>Backup Cloud</td>
                        <td>Respaldo automático diario</td>
                        <td>1</td>
                        <td>$30-60</td>
                        <td>$360-720</td>
                    </tr>
                    <tr>
                        <td>Firewall/Seguridad</td>
                        <td>SSL, DDoS protection</td>
                        <td>1</td>
                        <td>$20-50</td>
                        <td>$240-600</td>
                    </tr>
                    <tr>
                        <td colspan="4"><strong>TOTAL SERVIDOR CLOUD (Año 1)</strong></td>
                        <td><strong>$1,800-3,600</strong></td>
                    </tr>
                </tbody>
            </table>

            <div class="success-box">
                <strong>✅ Ventajas de la opción Cloud:</strong>
                <ul style="margin-top: 10px;">
                    <li>Sin inversión inicial en hardware</li>
                    <li>Acceso desde cualquier ubicación</li>
                    <li>Escalabilidad inmediata</li>
                    <li>Mantenimiento incluido</li>
                    <li>Alta disponibilidad (99.9% uptime)</li>
                </ul>
            </div>

            <h3>6.2.2 Estaciones de Trabajo</h3>

            <table>
                <thead>
                    <tr>
                        <th>Usuario</th>
                        <th>Especificación</th>
                        <th>Cant.</th>
                        <th>Precio Unit.</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Administrador</td>
                        <td>PC i5, 8GB RAM, SSD 256GB, Monitor 24"</td>
                        <td>1</td>
                        <td>$800</td>
                        <td>$800</td>
                    </tr>
                    <tr>
                        <td>Jefe de Mecánicos</td>
                        <td>PC i5, 8GB RAM, SSD 256GB, Monitor 24"</td>
                        <td>1</td>
                        <td>$800</td>
                        <td>$800</td>
                    </tr>
                    <tr>
                        <td>Encargado Inventario</td>
                        <td>PC i5, 8GB RAM, SSD 256GB, Monitor 24"</td>
                        <td>1</td>
                        <td>$800</td>
                        <td>$800</td>
                    </tr>
                    <tr>
                        <td>Personal Administrativo</td>
                        <td>PC i3, 8GB RAM, SSD 256GB, Monitor 22"</td>
                        <td>2</td>
                        <td>$650</td>
                        <td>$1,300</td>
                    </tr>
                    <tr>
                        <td colspan="4"><strong>SUBTOTAL ESTACIONES</strong></td>
                        <td><strong>$3,700</strong></td>
                    </tr>
                </tbody>
            </table>

            <h3>6.2.3 Dispositivos Móviles (Taller)</h3>

            <table>
                <thead>
                    <tr>
                        <th>Dispositivo</th>
                        <th>Especificación</th>
                        <th>Cant.</th>
                        <th>Precio Unit.</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tablets Mecánicos</td>
                        <td>Samsung Tab A8, 10", 64GB, funda protectora</td>
                        <td>6</td>
                        <td>$250</td>
                        <td>$1,500</td>
                    </tr>
                    <tr>
                        <td>Smartphone Jefe Taller</td>
                        <td>Gama media, 128GB, cámara</td>
                        <td>1</td>
                        <td>$300</td>
                        <td>$300</td>
                    </tr>
                    <tr>
                        <td colspan="4"><strong>SUBTOTAL MÓVILES</strong></td>
                        <td><strong>$1,800</strong></td>
                    </tr>
                </tbody>
            </table>

            <h3>6.2.4 Equipos para Inventario</h3>

            <table>
                <thead>
                    <tr>
                        <th>Equipo</th>
                        <th>Especificación</th>
                        <th>Cant.</th>
                        <th>Precio Unit.</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Lector Código Barras</td>
                        <td>2D Bluetooth, compatible QR</td>
                        <td>2</td>
                        <td>$120</td>
                        <td>$240</td>
                    </tr>
                    <tr>
                        <td>Impresora Etiquetas</td>
                        <td>Térmica Zebra ZD420</td>
                        <td>1</td>
                        <td>$400</td>
                        <td>$400</td>
                    </tr>
                    <tr>
                        <td>Etiquetas (kit inicial)</td>
                        <td>5,000 unidades adhesivas</td>
                        <td>1</td>
                        <td>$75</td>
                        <td>$75</td>
                    </tr>
                    <tr>
                        <td colspan="4"><strong>SUBTOTAL INVENTARIO</strong></td>
                        <td><strong>$715</strong></td>
                    </tr>
                </tbody>
            </table>

            <h3>6.2.5 Infraestructura de Red</h3>

            <table>
                <thead>
                    <tr>
                        <th>Componente</th>
                        <th>Especificación</th>
                        <th>Cant.</th>
                        <th>Precio Unit.</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Router Empresarial</td>
                        <td>TP-Link ER605 VPN</td>
                        <td>1</td>
                        <td>$120</td>
                        <td>$120</td>
                    </tr>
                    <tr>
                        <td>Access Point WiFi</td>
                        <td>Ubiquiti UniFi AP</td>
                        <td>3</td>
                        <td>$150</td>
                        <td>$450</td>
                    </tr>
                    <tr>
                        <td>Switch PoE</td>
                        <td>8 puertos Gigabit PoE</td>
                        <td>1</td>
                        <td>$140</td>
                        <td>$140</td>
                    </tr>
                    <tr>
                        <td>Cableado Estructurado</td>
                        <td>Cat6, instalación completa</td>
                        <td>1</td>
                        <td>$600</td>
                        <td>$600</td>
                    </tr>
                    <tr>
                        <td colspan="4"><strong>SUBTOTAL RED</strong></td>
                        <td><strong>$1,310</strong></td>
                    </tr>
                </tbody>
            </table>

            <h3>6.2.6 Periféricos y Otros</h3>

            <table>
                <thead>
                    <tr>
                        <th>Item</th>
                        <th>Cant.</th>
                        <th>Precio Unit.</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Impresora Multifuncional Láser</td>
                        <td>1</td>
                        <td>$320</td>
                        <td>$320</td>
                    </tr>
                    <tr>
                        <td>UPS/Reguladores</td>
                        <td>5</td>
                        <td>$80</td>
                        <td>$400</td>
                    </tr>
                    <tr>
                        <td>Webcam 1080p</td>
                        <td>2</td>
                        <td>$60</td>
                        <td>$120</td>
                    </tr>
                    <tr>
                        <td>Teclado + Mouse (sets)</td>
                        <td>5</td>
                        <td>$30</td>
                        <td>$150</td>
                    </tr>
                    <tr>
                        <td>Docking Station tablets</td>
                        <td>2</td>
                        <td>$45</td>
                        <td>$90</td>
                    </tr>
                    <tr>
                        <td>Disco Duro Externo 4TB backup</td>
                        <td>2</td>
                        <td>$110</td>
                        <td>$220</td>
                    </tr>
                    <tr>
                        <td>Cámara IP Seguridad</td>
                        <td>2</td>
                        <td>$120</td>
                        <td>$240</td>
                    </tr>
                    <tr>
                        <td colspan="3"><strong>SUBTOTAL PERIFÉRICOS</strong></td>
                        <td><strong>$1,540</strong></td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- ANÁLISIS DE SOFTWARE -->
        <div class="page">
            <h1>7. ANÁLISIS DE SOFTWARE</h1>

            <h2>7.1 Desarrollo del Sistema</h2>

            <p>Se propone el desarrollo de un sistema web a medida con aplicación móvil complementaria, utilizando tecnologías modernas y escalables.</p>

            <h3>7.1.1 Arquitectura Tecnológica Propuesta</h3>

            <table>
                <thead>
                    <tr>
                        <th>Componente</th>
                        <th>Tecnología Propuesta</th>
                        <th>Justificación</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Backend</strong></td>
                        <td>Node.js + Express o Python + Django</td>
                        <td>Alta escalabilidad, amplia comunidad, fácil mantenimiento</td>
                    </tr>
                    <tr>
                        <td><strong>Frontend Web</strong></td>
                        <td>React.js o Vue.js</td>
                        <td>Interfaz moderna, responsive, experiencia fluida</td>
                    </tr>
                    <tr>
                        <td><strong>Base de Datos</strong></td>
                        <td>PostgreSQL</td>
                        <td>Open source, robusta, alta confiabilidad</td>
                    </tr>
                    <tr>
                        <td><strong>App Móvil</strong></td>
                        <td>React Native o Flutter</td>
                        <td>Un solo código para Android e iOS</td>
                    </tr>
                    <tr>
                        <td><strong>Servidor</strong></td>
                        <td>Cloud (AWS, Google Cloud, Azure)</td>
                        <td>Escalable, confiable, sin inversión inicial</td>
                    </tr>
                    <tr>
                        <td><strong>Almacenamiento</strong></td>
                        <td>AWS S3 o similar</td>
                        <td>Para documentos, fotos, archivos</td>
                    </tr>
                </tbody>
            </table>

            <h3>7.1.2 Desglose de Desarrollo por Módulo</h3>

            <table>
                <thead>
                    <tr>
                        <th>Módulo/Actividad</th>
                        <th>Horas Est.</th>
                        <th>Tarifa/Hora</th>
                        <th>Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Análisis y Diseño</strong></td>
                        <td>80</td>
                        <td>$40</td>
                        <td>$3,200</td>
                    </tr>
                    <tr>
                        <td>• Levantamiento detallado de requisitos</td>
                        <td>30</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Diagramas UML (casos de uso, clases, secuencia)</td>
                        <td>25</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Diseño de base de datos</td>
                        <td>25</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td><strong>Módulo Vehículos</strong></td>
                        <td>60</td>
                        <td>$40</td>
                        <td>$2,400</td>
                    </tr>
                    <tr>
                        <td><strong>Módulo Mantenimientos</strong></td>
                        <td>120</td>
                        <td>$40</td>
                        <td>$4,800</td>
                    </tr>
                    <tr>
                        <td>• Sistema de alertas</td>
                        <td>40</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Programación preventivos/correctivos</td>
                        <td>50</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Calendario y notificaciones</td>
                        <td>30</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td><strong>Módulo Mecánicos/Talleres</strong></td>
                        <td>60</td>
                        <td>$40</td>
                        <td>$2,400</td>
                    </tr>
                    <tr>
                        <td><strong>Módulo Inventario</strong></td>
                        <td>80</td>
                        <td>$40</td>
                        <td>$3,200</td>
                    </tr>
                    <tr>
                        <td>• Control de stock</td>
                        <td>35</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Órdenes de requerimiento</td>
                        <td>25</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Integración con lectores código barras</td>
                        <td>20</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td><strong>Módulo Reportes</strong></td>
                        <td>80</td>
                        <td>$40</td>
                        <td>$3,200</td>
                    </tr>
                    <tr>
                        <td>• Reportes históricos</td>
                        <td>30</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Dashboard con KPIs</td>
                        <td>35</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Exportación Excel/PDF</td>
                        <td>15</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td><strong>Módulo Usuarios/Seguridad</strong></td>
                        <td>40</td>
                        <td>$40</td>
                        <td>$1,600</td>
                    </tr>
                    <tr>
                        <td><strong>Aplicación Móvil</strong></td>
                        <td>100</td>
                        <td>$40</td>
                        <td>$4,000</td>
                    </tr>
                    <tr>
                        <td>• Interfaz para tablets</td>
                        <td>50</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Funcionalidad offline</td>
                        <td>30</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td>• Captura de fotos</td>
                        <td>20</td>
                        <td></td>
                        <td></td>
                    </tr>
                    <tr>
                        <td><strong>Pruebas y QA</strong></td>
                        <td>60</td>
                        <td>$40</td>
                        <td>$2,400</td>
                    </tr>
                    <tr>
                        <td><strong>Capacitación</strong></td>
                        <td>40</td>
                        <td>$40</td>
                        <td>$1,600</td>
                    </tr>
                    <tr>
                        <td><strong>Migración de Datos</strong></td>
                        <td>30</td>
                        <td>$40</td>
                        <td>$1,200</td>
                    </tr>
                    <tr>
                        <td colspan="3"><strong>TOTAL DESARROLLO</strong></td>
                        <td><strong>$30,000</strong></td>
                    </tr>
                </tbody>
            </table>

            <h2>7.2 Licencias y Servicios Software</h2>

            <table>
                <thead>
                    <tr>
                        <th>Servicio</th>
                        <th>Descripción</th>
                        <th>Costo Anual</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Base de Datos</td>
                        <td>PostgreSQL (Open Source)</td>
                        <td>$0</td>
                    </tr>
                    <tr>
                        <td>Sistema Operativo</td>
                        <td>Linux Ubuntu Server (Open Source)</td>
                        <td>$0</td>
                    </tr>
                    <tr>
                        <td>Certificado SSL</td>
                        <td>Let's Encrypt (Gratis)</td>
                        <td>$0</td>
                    </tr>
                    <tr>
                        <td>Panel Control Servidor</td>
                        <td>cPanel/Plesk (Opcional)</td>
                        <td>$200</td>
                    </tr>
                    <tr>
                        <td>Email Transaccional</td>
                        <td>SendGrid/Mailgun para alertas</td>
                        <td>$240</td>
                    </tr>
                    <tr>
                        <td>Almacenamiento Docs</td>
                        <td>AWS S3 o similar</td>
                        <td>$180</td>
                    </tr>
                    <tr>
                        <td>Monitoreo</td>
                        <td>Herramienta de monitoreo básica</td>
                        <td>$120</td>
                    </tr>
                    <tr>
                        <td colspan="2"><strong>TOTAL LICENCIAS AÑO 1</strong></td>
                        <td><strong>$740</strong></td>
                    </tr>
                </tbody>
            </table>

            <h2>7.3 Soporte y Mantenimiento Software</h2>

            <table>
                <thead>
                    <tr>
                        <th>Servicio</th>
                        <th>Descripción</th>
                        <th>Costo Anual</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Soporte Técnico</td>
                        <td>Correctivos, consultas, incidencias (horario laboral)</td>
                        <td>$2,400</td>
                    </tr>
                    <tr>
                        <td>Actualizaciones</td>
                        <td>Mejoras menores, parches de seguridad (trimestral)</td>
                        <td>$1,200</td>
                    </tr>
                    <tr>
                        <td>Backup y Monitoreo</td>
                        <td>Supervisión 24/7, respaldos automáticos</td>
                        <td>$600</td>
                    </tr>
                    <tr>
                        <td colspan="2"><strong>TOTAL SOPORTE ANUAL</strong></td>
                        <td><strong>$4,200</strong></td>
                    </tr>
                </tbody>
            </table>

            <div class="info-box">
                <strong>Nota sobre Soporte:</strong> El primer año incluye soporte prioritario durante el período de estabilización. A partir del segundo año, el costo de soporte se mantiene pero puede ajustarse según el nivel de servicio requerido.
            </div>
        </div>

        <!-- PRESUPUESTO DETALLADO -->
        <div class="page">
            <h1>8. PRESUPUESTO DETALLADO</h1>

            <h2>8.1 Resumen de Costos de Hardware</h2>

            <table>
                <thead>
                    <tr>
                        <th>Categoría</th>
                        <th>Inversión Inicial</th>
                        <th>Recurrente Anual</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Servidor Cloud (Año 1)</td>
                        <td>-</td>
                        <td>$1,800 - 3,600</td>
                    </tr>
                    <tr>
                        <td>Estaciones de Trabajo</td>
                        <td>$3,700</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>Dispositivos Móviles</td>
                        <td>$1,800</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>Equipos de Inventario</td>
                        <td>$715</td>
                        <td>$200 (consumibles)</td>
                    </tr>
                    <tr>
                        <td>Infraestructura de Red</td>
                        <td>$1,310</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>Periféricos y Otros</td>
                        <td>$1,540</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>Internet Empresarial (50Mbps)</td>
                        <td>-</td>
                        <td>$900</td>
                    </tr>
                    <tr>
                        <td><strong>SUBTOTAL HARDWARE</strong></td>
                        <td><strong>$9,065</strong></td>
                        <td><strong>$2,900 - 4,700</strong></td>
                    </tr>
                    <tr style="background: #edf2f7;">
                        <td><strong>TOTAL HARDWARE AÑO 1</strong></td>
                        <td colspan="2" style="text-align: center;"><strong>$11,965 - 13,765</strong></td>
                    </tr>
                </tbody>
            </table>

            <h2>8.2 Resumen de Costos de Software</h2>

            <table>
                <thead>
                    <tr>
                        <th>Concepto</th>
                        <th>Año 1</th>
                        <th>Recurrente Anual</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Desarrollo Inicial del Sistema</td>
                        <td>$30,000</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td>Licencias Software</td>
                        <td>$740</td>
                        <td>$740</td>
                    </tr>
                    <tr>
                        <td>Soporte y Mantenimiento</td>
                        <td>$4,200</td>
                        <td>$4,200</td>
                    </tr>
                    <tr style="background: #edf2f7;">
                        <td><strong>TOTAL SOFTWARE AÑO 1</strong></td>
                        <td><strong>$34,940</strong></td>
                        <td><strong>$4,940</strong></td>
                    </tr>
                </tbody>
            </table>

            <h2>8.3 Inversión Total del Proyecto</h2>

            <div class="cost-summary" style="margin: 30px 0;">
                <div class="cost-card" style="grid-column: span 2;">
                    <h4>Inversión Inicial (Una vez)</h4>
                    <div class="amount" style="color: #667eea;">$39,065</div>
                    <p style="font-size: 13px; margin-top: 10px;">Hardware físico + Desarrollo software</p>
                </div>
            </div>

            <div class="cost-summary">
                <div class="cost-card">
                    <h4>Costos Recurrentes Año 1</h4>
                    <div class="amount" style="color: #f5576c; font-size: 24px;">$7,840 - 9,640</div>
                    <p style="font-size: 12px; margin-top: 8px;">Cloud + Soporte + Licencias</p>
                </div>
                <div class="cost-card">
                    <h4>TOTAL AÑO 1</h4>
                    <div class="amount" style="color: #48bb78; font-size: 24px;">$46,905 - 48,705</div>
                    <p style="font-size: 12px; margin-top: 8px;">Inversión completa primer año</p>
                </div>
            </div>

            <h3>8.3.1 Desglose de Inversión Año 1</h3>

            <table>
                <thead>
                    <tr>
                        <th>Concepto</th>
                        <th>Monto</th>
                        <th>% del Total</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Desarrollo de Software</td>
                        <td>$30,000</td>
                        <td>63.7%</td>
                    </tr>
                    <tr>
                        <td>Hardware (equipos físicos)</td>
                        <td>$9,065</td>
                        <td>19.2%</td>
                    </tr>
                    <tr>
                        <td>Hosting Cloud (año 1)</td>
                        <td>$1,800 - 3,600</td>
                        <td>3.8 - 7.6%</td>
                    </tr>
                    <tr>
                        <td>Soporte Software</td>
                        <td>$4,200</td>
                        <td>8.9%</td>
                    </tr>
                    <tr>
                        <td>Internet + Consumibles</td>
                        <td>$1,100</td>
                        <td>2.3%</td>
                    </tr>
                    <tr>
                        <td>Licencias Software</td>
                        <td>$740</td>
                        <td>1.6%</td>
                    </tr>
                    <tr style="background: #667eea; color: white;">
                        <td><strong>TOTAL</strong></td>
                        <td><strong>$46,905 - 48,705</strong></td>
                        <td><strong>100%</strong></td>
                    </tr>
                </tbody>
            </table>

            <h3>8.3.2 Proyección de Costos Años Siguientes</h3>

            <table>
                <thead>
                    <tr>
                        <th>Concepto</th>
                        <th>Año 2</th>
                        <th>Año 3</th>
                        <th>Año 4</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Hosting Cloud</td>
                        <td>$2,400</td>
                        <td>$2,400</td>
                        <td>$2,400</td>
                    </tr>
                    <tr>
                        <td>Internet</td>
                        <td>$900</td>
                        <td>$900</td>
                        <td>$900</td>
                    </tr>
                    <tr>
                        <td>Consumibles</td>
                        <td>$200</td>
                        <td>$200</td>
                        <td>$200</td>
                    </tr>
                    <tr>
                        <td>Soporte Software</td>
                        <td>$4,200</td>
                        <td>$4,200</td>
                        <td>$4,200</td>
                    </tr>
                    <tr>
                        <td>Licencias Software</td>
                        <td>$740</td>
                        <td>$740</td>
                        <td>$740</td>
                    </tr>
                    <tr>
                        <td>Mantenimiento Hardware</td>
                        <td>$400</td>
                        <td>$400</td>
                        <td>$800</td>
                    </tr>
                    <tr style="background: #edf2f7; font-weight: bold;">
                        <td>TOTAL ANUAL</td>
                        <td>$8,840</td>
                        <td>$8,840</td>
                        <td>$9,240</td>
                    </tr>
                </tbody>
            </table>

            <div class="success-box">
                <strong>💰 Análisis Financiero:</strong>
                <ul style="margin-top: 10px;">
                    <li><strong>Inversión inicial:</strong> $39,065 (una sola vez)</li>
                    <li><strong>Costo operativo anual:</strong> $8,840 promedio (años 2-4)</li>
                    <li><strong>ROI estimado:</strong> 18-24 meses mediante ahorro en costos operativos</li>
                    <li><strong>Vida útil del sistema:</strong> 5-7 años con mantenimiento adecuado</li>
                </ul>
            </div>

            <h3>8.3.3 Plan de Pagos Sugerido</h3>

            <table>
                <thead>
                    <tr>
                        <th>Hito</th>
                        <th>% Avance</th>
                        <th>Monto</th>
                        <th>Fecha Estimada</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Pago 1:</strong> Inicio del Proyecto</td>
                        <td>0%</td>
                        <td>$3,000</td>
                        <td>Semana 1</td>
                    </tr>
                    <tr>
                        <td><strong>Pago 2:</strong> Diseño Aprobado</td>
                        <td>10%</td>
                        <td>$3,000</td>
                        <td>Semana 3</td>
                    </tr>
                    <tr>
                        <td><strong>Pago 3:</strong> Sistema Base Funcional</td>
                        <td>50%</td>
                        <td>$15,000</td>
                        <td>Semana 14</td>
                    </tr>
                    <tr>
                        <td><strong>Pago 4:</strong> Pruebas Completadas</td>
                        <td>70%</td>
                        <td>$6,000</td>
                        <td>Semana 17</td>
                    </tr>
                    <tr>
                        <td><strong>Pago 5:</strong> Go-Live Exitoso</td>
                        <td>90%</td>
                        <td>$3,000</td>
                        <td>Semana 21</td>
                    </tr>
                    <tr>
                        <td><strong>Pago 6:</strong> Cierre Proyecto (30 días)</td>
                        <td>100%</td>
                        <td>$9,065</td>
                        <td>Semana 25</td>
                    </tr>
                    <tr style="background: #667eea; color: white;">
                        <td colspan="2"><strong>TOTAL</strong></td>
                        <td><strong>$39,065</strong></td>
                        <td></td>
                    </tr>
                </tbody>
            </table>
        </div>

        <!-- CRONOGRAMA -->
        <div class="page">
            <h1>9. CRONOGRAMA DE IMPLEMENTACIÓN</h1>

            <div class="info-box">
                <strong>Duración Total:</strong> 25 semanas (aproximadamente 6 meses)<br>
                <strong>Fecha de Inicio Estimada:</strong> Enero 2026<br>
                <strong>Fecha Go-Live Estimada:</strong> Mayo 2026<br>
                <strong>Fecha Cierre Proyecto:</strong> Junio 2026
            </div>

            <h2>9.1 Fases del Proyecto</h2>

            <div class="gantt-simple">
                <div class="gantt-bar phase-1">
                    <span><strong>FASE 1: Planificación y Análisis</strong></span>
                    <span>Sem 1-3 (3 semanas)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Levantamiento de requisitos detallado</li>
                    <li>Diseño de arquitectura y base de datos</li>
                    <li>Creación de mockups y prototipos</li>
                    <li>Validación y aprobación del diseño</li>
                </ul>

                <div class="gantt-bar phase-2">
                    <span><strong>FASE 2: Adquisición de Hardware</strong></span>
                    <span>Sem 1-3 (Paralelo a Fase 1)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Cotización y compra de equipos</li>
                    <li>Contratación de servicios cloud</li>
                    <li>Instalación de infraestructura de red</li>
                    <li>Configuración de estaciones de trabajo</li>
                </ul>

                <div class="gantt-bar phase-3">
                    <span><strong>FASE 3: Desarrollo del Sistema</strong></span>
                    <span>Sem 4-14 (10 semanas)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Infraestructura base y base de datos (2 sem)</li>
                    <li>Módulo de Vehículos (2 sem)</li>
                    <li>Módulo de Mantenimientos (3 sem)</li>
                    <li>Módulo de Inventario (2 sem)</li>
                    <li>Módulo de Reportes (1 sem)</li>
                    <li>Aplicación móvil (1 sem)</li>
                </ul>

                <div class="gantt-bar phase-4">
                    <span><strong>FASE 4: Pruebas y Ajustes</strong></span>
                    <span>Sem 15-17 (3 semanas)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Pruebas internas (QA)</li>
                    <li>Pruebas con usuarios piloto</li>
                    <li>Corrección de bugs y ajustes</li>
                    <li>Pruebas finales de aceptación</li>
                </ul>

                <div class="gantt-bar phase-5">
                    <span><strong>FASE 5: Migración de Datos</strong></span>
                    <span>Sem 18 (1 semana)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Exportación de datos desde Excel</li>
                    <li>Limpieza y validación de datos</li>
                    <li>Importación al nuevo sistema</li>
                    <li>Verificación de integridad</li>
                </ul>

                <div class="gantt-bar phase-6">
                    <span><strong>FASE 6: Capacitación</strong></span>
                    <span>Sem 19-20 (2 semanas)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Capacitación a administrativos (8 horas)</li>
                    <li>Capacitación a jefe de mecánicos (6 horas)</li>
                    <li>Capacitación a mecánicos - App móvil (4 horas)</li>
                    <li>Capacitación a encargado de inventario (4 horas)</li>
                </ul>

                <div class="gantt-bar phase-7">
                    <span><strong>FASE 7: Go-Live y Puesta en Marcha</strong></span>
                    <span>Sem 21 (1 semana)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Despliegue a producción</li>
                    <li>Configuración final y pruebas smoke</li>
                    <li>Acompañamiento in-situ a usuarios</li>
                    <li>Ajustes menores en tiempo real</li>
                </ul>

                <div class="gantt-bar phase-8">
                    <span><strong>FASE 8: Soporte Post-Lanzamiento</strong></span>
                    <span>Sem 22-25 (4 semanas)</span>
                </div>
                <ul style="margin: 10px 0 20px 40px; font-size: 14px;">
                    <li>Soporte prioritario 24/7</li>
                    <li>Corrección de incidencias</li>
                    <li>Monitoreo de rendimiento</li>
                    <li>Ajustes basados en uso real</li>
                    <li>Cierre formal del proyecto</li>
                </ul>
            </div>

            <h2>9.2 Hitos Principales</h2>

            <table>
                <thead>
                    <tr>
                        <th>Hito</th>
                        <th>Fecha</th>
                        <th>Entregables</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>🚀 <strong>Inicio del Proyecto</strong></td>
                        <td>01/Ene/2026</td>
                        <td>Contrato firmado, equipo asignado</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Diseño Aprobado</strong></td>
                        <td>22/Ene/2026</td>
                        <td>Documentación completa, mockups validados</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Hardware Instalado</strong></td>
                        <td>22/Ene/2026</td>
                        <td>Infraestructura operativa, red configurada</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Sistema Beta</strong></td>
                        <td>02/Abr/2026</td>
                        <td>Sistema funcional con todos los módulos</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Pruebas Completadas</strong></td>
                        <td>23/Abr/2026</td>
                        <td>Sistema aprobado para producción</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Migración Completa</strong></td>
                        <td>30/Abr/2026</td>
                        <td>Datos históricos migrados y verificados</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Capacitación Finalizada</strong></td>
                        <td>14/May/2026</td>
                        <td>Todos los usuarios capacitados</td>
                    </tr>
                    <tr style="background: #48bb78; color: white;">
                        <td>🎉 <strong>GO-LIVE</strong></td>
                        <td>21/May/2026</td>
                        <td>Sistema en producción operando</td>
                    </tr>
                    <tr>
                        <td>✅ <strong>Cierre del Proyecto</strong></td>
                        <td>18/Jun/2026</td>
                        <td>Proyecto estabilizado y cerrado</td>
                    </tr>
                </tbody>
            </table>

            <div class="footer">
                <p>Este cronograma es una estimación basada en la información disponible y puede ajustarse según las necesidades del proyecto.</p>
            </div>
        </div>

        <!-- ANÁLISIS DE RIESGOS -->
        <div class="page">
            <h1>10. ANÁLISIS DE RIESGOS</h1>

            <h2>10.1 Riesgos Identificados y Plan de Mitigación</h2>

            <table>
                <thead>
                    <tr>
                        <th>Riesgo</th>
                        <th>Prob.</th>
                        <th>Impacto</th>
                        <th>Mitigación</th>
                        <th>Contingencia</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>R-01: Retraso en compra de hardware</strong></td>
                        <td><span class="badge badge-medium">Media</span></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>Iniciar proceso de compra desde semana 1. Tener proveedores alternativos.</td>
                        <td>+1 semana buffer. Usar equipos temporales si es necesario.</td>
                    </tr>
                    <tr>
                        <td><strong>R-02: Cambios frecuentes en requisitos</strong></td>
                        <td><span class="badge badge-high">Alta</span></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>Validación exhaustiva en fase de diseño. Proceso formal de control de cambios.</td>
                        <td>+2 semanas buffer. Priorización de cambios críticos vs. deseables.</td>
                    </tr>
                    <tr>
                        <td><strong>R-03: Problemas en migración de datos</strong></td>
                        <td><span class="badge badge-medium">Media</span></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>Backup completo antes de migración. Pruebas con datos de muestra primero.</td>
                        <td>Plan B: migración manual por lotes. Rollback disponible.</td>
                    </tr>
                    <tr>
                        <td><strong>R-04: Resistencia al cambio del personal</strong></td>
                        <td><span class="badge badge-high">Alta</span></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>Comunicación temprana de beneficios. Involucrar usuarios clave desde inicio. Capacitación extendida.</td>
                        <td>Sesiones de coaching adicionales. Champions por área.</td>
                    </tr>
                    <tr>
                        <td><strong>R-05: Bugs críticos post-lanzamiento</strong></td>
                        <td><span class="badge badge-medium">Media</span></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>Pruebas exhaustivas. QA independiente. Beta con usuarios reales.</td>
                        <td>Soporte 24/7 primer mes. Hotfix rápido. Rollback si es crítico.</td>
                    </tr>
                    <tr>
                        <td><strong>R-06: Problemas de conectividad</strong></td>
                        <td><span class="badge badge-low">Baja</span></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>Internet empresarial con SLA. Backup de conexión 4G.</td>
                        <td>Modo offline en app móvil. Sincronización posterior.</td>
                    </tr>
                    <tr>
                        <td><strong>R-07: Pérdida de datos</strong></td>
                        <td><span class="badge badge-low">Baja</span></td>
                        <td><span class="badge badge-critical">Crítico</span></td>
                        <td>Backups automáticos diarios. Respaldos en múltiples ubicaciones.</td>
                        <td>Recuperación desde backup más reciente. RPO: 24 horas.</td>
                    </tr>
                    <tr>
                        <td><strong>R-08: Rotación de personal clave</strong></td>
                        <td><span class="badge badge-medium">Media</span></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>Documentación completa. Transferencia de conocimiento a múltiples personas.</td>
                        <td>Capacitación rápida a reemplazos. Manuales detallados.</td>
                    </tr>
                    <tr>
                        <td><strong>R-09: Sobrecarga del equipo de desarrollo</strong></td>
                        <td><span class="badge badge-medium">Media</span></td>
                        <td><span class="badge badge-medium">Medio</span></td>
                        <td>Planificación realista. Revisión semanal de avances.</td>
                        <td>Recursos adicionales si es necesario. Repriorización de tareas.</td>
                    </tr>
                    <tr>
                        <td><strong>R-10: Incompatibilidad tecnológica</strong></td>
                        <td><span class="badge badge-low">Baja</span></td>
                        <td><span class="badge badge-high">Alto</span></td>
                        <td>Pruebas de compatibilidad tempranas. Tecnologías probadas y estables.</td>
                        <td>Cambio de stack tecnológico si se detecta a tiempo.</td>
                    </tr>
                </tbody>
            </table>

            <h2>10.2 Matriz de Riesgos</h2>

            <div style="margin: 30px 0; padding: 20px; background: #f7fafc; border-radius: 10px;">
                <table style="width: 100%; text-align: center;">
                    <thead>
                        <tr>
                            <th style="width: 20%;"></th>
                            <th style="background: #48bb78; color: white;">Bajo</th>
                            <th style="background: #4299e1; color: white;">Medio</th>
                            <th style="background: #f6ad55; color: white;">Alto</th>
                            <th style="background: #fc8181; color: white;">Crítico</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td style="background: #fc8181; color: white; font-weight: bold;">Alta</td>
                            <td>-</td>
                            <td>R-02, R-04</td>
                            <td>-</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td style="background: #f6ad55; color: white; font-weight: bold;">Media</td>
                            <td>-</td>
                            <td>R-06, R-08, R-09</td>
                            <td>R-01, R-03, R-05</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td style="background: #4299e1; color: white; font-weight: bold;">Baja</td>
                            <td>-</td>
                            <td>R-06</td>
                            <td>R-10</td>
                            <td>R-07</td>
                        </tr>
                    </tbody>
                </table>
                <p style="text-align: center; margin-top: 20px; font-size: 14px;">
                    <strong>Probabilidad vs. Impacto</strong>
                </p>
            </div>

            <h2>10.3 Buffer de Tiempo Recomendado</h2>

            <div class="warning-box">
                <strong>⏱️ Buffer Total Recomendado:</strong> +4 semanas adicionales (total: 29 semanas)<br><br>
                <strong>Distribución del buffer:</strong>
                <ul style="margin-top: 10px;">
                    <li>+1 semana para adquisición de hardware</li>
                    <li>+2 semanas para cambios en requisitos</li>
                    <li>+1 semana para estabilización post-lanzamiento</li>
                </ul>
            </div>
        </div>

        <!-- PLAN DE IMPLEMENTACIÓN -->
        <div class="page">
            <h1>11. PLAN DE IMPLEMENTACIÓN</h1>

            <h2>11.1 Estrategia de Implementación</h2>

            <p>Se propone una estrategia de implementación por fases (Big Bang Controlado) con los siguientes componentes:</p>

            <h3>11.1.1 Preparación Pre-Lanzamiento</h3>

            <table>
                <thead>
                    <tr>
                        <th>Actividad</th>
                        <th>Responsable</th>
                        <th>Duración</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Limpieza y validación de datos existentes en Excel</td>
                        <td>Cliente + Analista</td>
                        <td>2 semanas</td>
                    </tr>
                    <tr>
                        <td>Instalación y configuración de hardware</td>
                        <td>Técnico IT</td>
                        <td>2 semanas</td>
                    </tr>
                    <tr>
                        <td>Creación de usuarios y permisos</td>
                        <td>Administrador Sistema</td>
                        <td>3 días</td>
                    </tr>
                    <tr>
                        <td>Carga de catálogos maestros (mecánicos, talleres, repuestos)</td>
                        <td>Cliente</td>
                        <td>1 semana</td>
                    </tr>
                    <tr>
                        <td>Capacitación a usuarios</td>
                        <td>Capacitador</td>
                        <td>2 semanas</td>
                    </tr>
                </tbody>
            </table>

            <h3>11.1.2 Estrategia de Go-Live</h3>

            <div class="info-box">
                <strong>Enfoque Recomendado: Big Bang Controlado</strong><br><br>
                Se activará el sistema completo en una fecha definida, pero con las siguientes medidas de control:
                <ul style="margin-top: 10px;">
                    <li>Go-Live en día viernes (menor actividad, fin de semana para ajustes)</li>
                    <li>Equipo técnico en sitio durante 3-5 días</li>
                    <li>Sistema antiguo (Excel) disponible por 1 mes como respaldo</li>
                    <li>Monitoreo intensivo primera semana</li>
                    <li>Hotline de soporte 24/7 durante el primer mes</li>
                </ul>
            </div>

            <h3>11.1.3 Cronograma de Go-Live (Semana 21)</h3>

            <table>
                <thead>
                    <tr>
                        <th>Día</th>
                        <th>Actividades</th>
                        <th>Horario</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Jueves</strong></td>
                        <td>
                            • Backup completo de datos<br>
                            • Verificación final de configuraciones<br>
                            • Preparación de equipos
                        </td>
                        <td>Todo el día</td>
                    </tr>
                    <tr>
                        <td><strong>Viernes 6am</strong></td>
                        <td>
                            • Activación del sistema en producción<br>
                            • Pruebas smoke finales<br>
                            • Verificación de conectividad
                        </td>
                        <td>6:00am - 8:00am</td>
                    </tr>
                    <tr>
                        <td><strong>Viernes 8am</strong></td>
                        <td>
                            • 🎉 <strong>GO-LIVE OFICIAL</strong><br>
                            • Inicio de operaciones con sistema nuevo<br>
                            • Equipo técnico en sitio
                        </td>
                        <td>8:00am</td>
                    </tr>
                    <tr>
                        <td><strong>Viernes-Domingo</strong></td>
                        <td>
                            • Monitoreo continuo<br>
                            • Corrección de incidencias menores<br>
                            • Soporte on-call 24/7
                        </td>
                        <td>24/7</td>
                    </tr>
                    <tr>
                        <td><strong>Lunes-Viernes (Sem 21)</strong></td>
                        <td>
                            • Acompañamiento presencial<br>
                            • Resolución de dudas<br>
                            • Ajustes basados en feedback
                        </td>
                        <td>Horario laboral</td>
                    </tr>
                </tbody>
            </table>

            <h2>11.2 Plan de Capacitación</h2>

            <h3>11.2.1 Grupos de Capacitación</h3>

            <table>
                <thead>
                    <tr>
                        <th>Grupo</th>
                        <th>Participantes</th>
                        <th>Duración</th>
                        <th>Contenido</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Administrativos</strong></td>
                        <td>Admin, personal oficina</td>
                        <td>8 horas (2 sesiones)</td>
                        <td>
                            • Navegación general<br>
                            • Gestión de vehículos<br>
                            • Programación mantenimientos<br>
                            • Generación de reportes<br>
                            • Dashboard y KPIs
                        </td>
                    </tr>
                    <tr>
                        <td><strong>Jefe de Mecánicos</strong></td>
                        <td>1-2 supervisores</td>
                        <td>6 horas (1.5 sesiones)</td>
                        <td>
                            • Asignación de trabajos<br>
                            • Órdenes de requerimiento<br>
                            • Seguimiento de servicios<br>
                            • Gestión de recursos<br>
                            • Reportes operativos
                        </td>
                    </tr>
                    <tr>
                        <td><strong>Mecánicos</strong></td>
                        <td>5-10 técnicos</td>
                        <td>4 horas</td>
                        <td>
                            • App móvil: login y navegación<br>
                            • Consulta de órdenes de trabajo<br>
                            • Registro de servicios realizados<br>
                            • Captura de fotos<br>
                            • Cierre de órdenes
                        </td>
                    </tr>
                    <tr>
                        <td><strong>Inventario</strong></td>
                        <td>1-2 encargados bodega</td>
                        <td>4 horas</td>
                        <td>
                            • Gestión de catálogo de repuestos<br>
                            • Uso de lector de códigos<br>
                            • Procesamiento de órdenes<br>
                            • Control de entradas/salidas<br>
                            • Alertas de stock mínimo
                        </td>
                    </tr>
                </tbody>
            </table>

            <h3>11.2.2 Material de Capacitación</h3>

            <ul>
                <li>✅ Manual de Usuario completo (PDF descargable)</li>
                <li>✅ Videos tutoriales por módulo (5-10 minutos cada uno)</li>
                <li>✅ Guías rápidas (cheat sheets) imprimibles</li>
                <li>✅ Presentaciones PowerPoint para sesiones presenciales</li>
                <li>✅ FAQ (Preguntas Frecuentes)</li>
                <li>✅ Base de conocimientos online</li>
            </ul>

            <h2>11.3 Plan de Soporte Post-Lanzamiento</h2>

            <h3>Niveles de Soporte</h3>

            <table>
                <thead>
                    <tr>
                        <th>Período</th>
                        <th>Tipo de Soporte</th>
                        <th>Tiempo de Respuesta</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Semana 1-4 (Mes 1)</strong></td>
                        <td>Soporte prioritario 24/7<br>Equipo en sitio disponible</td>
                        <td>
                            • Crítico: 1 hora<br>
                            • Alto: 4 horas<br>
                            • Medio: 8 horas
                        </td>
                    </tr>
                    <tr>
                        <td><strong>Mes 2-3</strong></td>
                        <td>Soporte horario laboral<br>On-call para emergencias</td>
                        <td>
                            • Crítico: 4 horas<br>
                            • Alto: 1 día<br>
                            • Medio: 2 días
                        </td>
                    </tr>
                    <tr>
                        <td><strong>Mes 4+</strong></td>
                        <td>Soporte estándar<br>Horario oficina (8am-6pm)</td>
                        <td>
                            • Crítico: 8 horas<br>
                            • Alto: 2 días<br>
                            • Medio: 5 días
                        </td>
                    </tr>
                </tbody>
            </table>

            <h3>Canales de Soporte</h3>
            <ul>
                <li>📧 <strong>Email:</strong> soporte@proyecto.com</li>
                <li>📱 <strong>WhatsApp/Teléfono:</strong> Línea directa de soporte</li>
                <li>💻 <strong>Sistema de Tickets:</strong> Dentro de la plataforma</li>
                <li>👥 <strong>Sesiones remotas:</strong> TeamViewer/AnyDesk para casos complejos</li>
            </ul>
        </div>

        <!-- CONCLUSIONES -->
        <div class="page">
            <h1>12. CONCLUSIONES Y RECOMENDACIONES</h1>

            <h2>12.1 Conclusiones</h2>

            <p style="text-align: justify;">
                La implementación del Sistema de Gestión de Mantenimiento de Flota Vehicular representa una transformación digital fundamental para la empresa, que permitirá evolucionar de procesos manuales y desorganizados hacia una gestión moderna, automatizada y basada en datos.
            </p>

            <h3>Conclusiones Principales:</h3>

            <div class="success-box">
                <strong>1. Necesidad Crítica Identificada</strong><br>
                La empresa actualmente opera sin herramientas tecnológicas adecuadas para gestionar su flota, lo cual representa riesgos operativos, pérdidas económicas y oportunidades de mejora significativas.
            </div>

            <div class="success-box">
                <strong>2. Solución Integral Propuesta</strong><br>
                El sistema propuesto cubre todos los aspectos críticos: gestión de vehículos, mantenimientos preventivos y correctivos, control de inventario, asignación de recursos y análisis mediante reportes y dashboards.
            </div>

            <div class="success-box">
                <strong>3. Inversión Justificada</strong><br>
                Con una inversión inicial de $39,065 y costos operativos de ~$8,800/año, el ROI esperado es de 18-24 meses mediante la reducción de costos operativos y optimización de procesos.
            </div>

            <div class="success-box">
                <strong>4. Enfoque Tecnológico Adecuado</strong><br>
                La arquitectura cloud propuesta ofrece escalabilidad, accesibilidad remota y costos predecibles, sin requerir grandes inversiones en infraestructura local.
            </div>

            <div class="success-box">
                <strong>5. Riesgos Controlables</strong><br>
                Los riesgos identificados son manejables mediante las estrategias de mitigación propuestas y el plan de implementación gradual con soporte intensivo inicial.
            </div>

            <h2>12.2 Beneficios Esperados</h2>

            <h3>Beneficios Cuantitativos:</h3>
            <ul>
                <li>✅ <strong>Reducción del 40%</strong> en tiempo de gestión de mantenimientos</li>
                <li>✅ <strong>Reducción del 15-20%</strong> en costos operativos de mantenimiento</li>
                <li>✅ <strong>Reducción del 60%</strong> en errores de transcripción manual</li>
                <li>✅ <strong>Mejora del 95%</strong> en cumplimiento de mantenimientos preventivos</li>
                <li>✅ <strong>Reducción del 30%</strong> en tiempos muertos de vehículos</li>
                <li>✅ <strong>Ahorro del 25%</strong> en costos de inventario por mejor control</li>
            </ul>

            <h3>Beneficios Cualitativos:</h3>
            <ul>
                <li>📊 <strong>Visibilidad total:</strong> Información centralizada y accesible en tiempo real</li>
                <li>🔔 <strong>Gestión proactiva:</strong> Alertas automáticas previenen problemas mayores</li>
                <li>📱 <strong>Movilidad:</strong> Mecánicos pueden registrar servicios desde el taller</li>
                <li>📈 <strong>Toma de decisiones:</strong> Reportes y KPIs para decisiones basadas en datos</li>
                <li>🔒 <strong>Seguridad:</strong> Información respaldada y protegida</li>
                <li>👥 <strong>Colaboración:</strong> Mejor comunicación entre áreas</li>
                <li>✨ <strong>Profesionalización:</strong> Imagen mejorada ante clientes y auditorías</li>
            </ul>

            <h2>12.3 Recomendaciones</h2>

            <h3>Recomendaciones Estratégicas:</h3>

            <div class="info-box">
                <strong>✅ RECOMENDACIÓN 1: Aprobar el proyecto</strong><br>
                Dada la criticidad de la necesidad y el análisis costo-beneficio favorable, se recomienda aprobar la implementación del sistema en el plazo propuesto.
            </div>

            <div class="info-box">
                <strong>✅ RECOMENDACIÓN 2: Implementación por fases</strong><br>
                Seguir el plan de implementación propuesto con fases claramente definidas, permitiendo validación progresiva y ajustes tempranos.
            </div>

            <div class="info-box">
                <strong>✅ RECOMENDACIÓN 3: Priorizar capacitación</strong><br>
                Invertir tiempo y recursos en capacitación exhaustiva de todos los usuarios. El éxito del sistema depende en gran medida de la adopción por parte del personal.
            </div>

            <div class="info-box">
                <strong>✅ RECOMENDACIÓN 4: Designar un líder interno</strong><br>
                Nombrar un "champion" o líder del proyecto dentro de la organización que coordine con el equipo de desarrollo y facilite la adopción del sistema.
            </div>

            <div class="info-box">
                <strong>✅ RECOMENDACIÓN 5: Iniciar con datos limpios</strong><br>
                Dedicar tiempo previo al go-live para limpiar y validar los datos existentes en Excel. La calidad del sistema depende de la calidad de los datos.
            </div>

            <h3>Recomendaciones Técnicas:</h3>

            <ul>
                <li>🌐 <strong>Optar por solución cloud:</strong> Mayor flexibilidad y menor inversión inicial</li>
                <li>📱 <strong>Priorizar app móvil:</strong> Fundamental para adopción por parte de mecánicos</li>
                <li>🏷️ <strong>Implementar códigos de barras:</strong> Mejora significativa en control de inventario</li>
                <li>📡 <strong>Garantizar conectividad robusta:</strong> WiFi de calidad en taller es crítico</li>
                <li>💾 <strong>Mantener respaldos frecuentes:</strong> Protección de información crítica del negocio</li>
            </ul>

            <h2>12.4 Próximos Pasos</h2>

            <div class="warning-box">
                <strong>Si se aprueba el proyecto, los pasos inmediatos son:</strong>
                <ol style="margin-top: 15px; margin-left: 20px;">
                    <li><strong>Firma del contrato</strong> y asignación de presupuesto</li>
                    <li><strong>Kick-off meeting</strong> con todos los stakeholders</li>
                    <li><strong>Inicio de adquisición</strong> de hardware y contratación de servicios cloud</li>
                    <li><strong>Formación del equipo</strong> de proyecto (interno + desarrollo)</li>
                    <li><strong>Inicio de Fase 1:</strong> Planificación y Análisis Detallado</li>
                </ol>
            </div>

            <div style="margin-top: 50px; padding: 30px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; border-radius: 10px; text-align: center;">
                <h2 style="color: white; border: none; margin-bottom: 15px;">🚀 Estamos listos para comenzar</h2>
                <p style="font-size: 18px; margin-bottom: 0;">
                    Este proyecto transformará la forma en que gestionan su flota vehicular,<br>
                    llevando a su empresa hacia la excelencia operativa y la transformación digital.
                </p>
            </div>

            <div class="footer" style="margin-top: 60px;">
                <hr style="margin-bottom: 20px;">
                <p><strong>Documento preparado por:</strong> Equipo de Análisis de Sistemas</p>
                <p><strong>Fecha:</strong> Octubre 2025 | <strong>Versión:</strong> 1.0</p>
                <p><strong>Confidencial:</strong> Este documento contiene información confidencial y es propiedad exclusiva del cliente.</p>
            </div>
        </div>

        <!-- ANEXOS -->
        <div class="page">
            <h1>ANEXOS</h1>

            <h2>ANEXO A: Glosario de Términos</h2>

            <table>
                <thead>
                    <tr>
                        <th style="width: 30%;">Término</th>
                        <th>Definición</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>API</strong></td>
                        <td>Application Programming Interface. Conjunto de reglas que permite la comunicación entre diferentes sistemas de software.</td>
                    </tr>
                    <tr>
                        <td><strong>Backup</strong></td>
                        <td>Copia de seguridad de datos que permite su recuperación en caso de pérdida.</td>
                    </tr>
                    <tr>
                        <td><strong>Cloud / Nube</strong></td>
                        <td>Infraestructura de servidores remotos accesibles por internet, que elimina la necesidad de servidores físicos locales.</td>
                    </tr>
                    <tr>
                        <td><strong>Dashboard</strong></td>
                        <td>Tablero visual que muestra indicadores clave de rendimiento (KPIs) de forma gráfica e intuitiva.</td>
                    </tr>
                    <tr>
                        <td><strong>Go-Live</strong></td>
                        <td>Momento en que el sistema entra en operación productiva real.</td>
                    </tr>
                    <tr>
                        <td><strong>KPI</strong></td>
                        <td>Key Performance Indicator. Indicador clave de rendimiento que mide el desempeño de un proceso.</td>
                    </tr>
                    <tr>
                        <td><strong>Mantenimiento Correctivo</strong></td>
                        <td>Reparación realizada después de que ocurre una falla o problema.</td>
                    </tr>
                    <tr>
                        <td><strong>Mantenimiento Preventivo</strong></td>
                        <td>Servicio programado de forma regular para prevenir fallas futuras.</td>
                    </tr>
                    <tr>
                        <td><strong>QA</strong></td>
                        <td>Quality Assurance. Proceso de pruebas para asegurar la calidad del software.</td>
                    </tr>
                    <tr>
                        <td><strong>Responsive</strong></td>
                        <td>Diseño que se adapta automáticamente a diferentes tamaños de pantalla (PC, tablet, móvil).</td>
                    </tr>
                    <tr>
                        <td><strong>ROI</strong></td>
                        <td>Return on Investment. Retorno de la inversión, mide la rentabilidad de un proyecto.</td>
                    </tr>
                    <tr>
                        <td><strong>SLA</strong></td>
                        <td>Service Level Agreement. Acuerdo de nivel de servicio que garantiza ciertos estándares de rendimiento.</td>
                    </tr>
                    <tr>
                        <td><strong>SSL</strong></td>
                        <td>Secure Sockets Layer. Protocolo de seguridad que encripta las comunicaciones web (https://).</td>
                    </tr>
                    <tr>
                        <td><strong>UML</strong></td>
                        <td>Unified Modeling Language. Lenguaje estándar para crear diagramas de sistemas de software.</td>
                    </tr>
                    <tr>
                        <td><strong>Uptime</strong></td>
                        <td>Porcentaje de tiempo que un sistema está operativo y disponible.</td>
                    </tr>
                </tbody>
            </table>

            <h2 style="margin-top: 40px;">ANEXO B: Especificaciones Técnicas Detalladas</h2>

            <h3>Stack Tecnológico Propuesto</h3>

            <table>
                <thead>
                    <tr>
                        <th>Capa</th>
                        <th>Tecnología</th>
                        <th>Versión</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Backend Framework</strong></td>
                        <td>Node.js + Express / Python + Django</td>
                        <td>LTS</td>
                    </tr>
                    <tr>
                        <td><strong>Frontend Framework</strong></td>
                        <td>React.js / Vue.js</td>
                        <td>Latest stable</td>
                    </tr>
                    <tr>
                        <td><strong>Base de Datos</strong></td>
                        <td>PostgreSQL</td>
                        <td>15.x</td>
                    </tr>
                    <tr>
                        <td><strong>App Móvil</strong></td>
                        <td>React Native / Flutter</td>
                        <td>Latest stable</td>
                    </tr>
                    <tr>
                        <td><strong>Servidor Web</strong></td>
                        <td>Nginx</td>
                        <td>Latest</td>
                    </tr>
                    <tr>
                        <td><strong>Cloud Provider</strong></td>
                        <td>AWS / Google Cloud / Azure</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td><strong>Almacenamiento</strong></td>
                        <td>AWS S3 / Cloud Storage</td>
                        <td>-</td>
                    </tr>
                    <tr>
                        <td><strong>Email Service</strong></td>
                        <td>SendGrid / Mailgun</td>
                        <td>-</td>
                    </tr>
                </tbody>
            </table>

            <h2 style="margin-top: 40px;">ANEXO C: Contactos del Proyecto</h2>

            <table>
                <thead>
                    <tr>
                        <th>Rol</th>
                        <th>Nombre</th>
                        <th>Email</th>
                        <th>Teléfono</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><strong>Jefe de Proyecto</strong></td>
                        <td>[Nombre]</td>
                        <td>[email]</td>
                        <td>[teléfono]</td>
                    </tr>
                    <tr>
                        <td><strong>Analista de Sistemas</strong></td>
                        <td>[Nombre]</td>
                        <td>[email]</td>
                        <td>[teléfono]</td>
                    </tr>
                    <tr>
                        <td><strong>Líder Técnico</strong></td>
                        <td>[Nombre]</td>
                        <td>[email]</td>
                        <td>[teléfono]</td>
                    </tr>
                    <tr>
                        <td><strong>Soporte Técnico</strong></td>
                        <td>[Nombre]</td>
                        <td>soporte@proyecto.com</td>
                        <td>[teléfono]</td>
                    </tr>
                </tbody>
            </table>

            <div style="margin-top: 60px; text-align: center; padding: 40px; background: #f7fafc; border-radius: 10px;">
                <h2 style="color: #667eea;">📄 FIN DEL DOCUMENTO</h2>
                <p style="margin-top: 20px; font-size: 14px; color: #718096;">
                    Para consultas o aclaraciones sobre este documento, por favor contacte al equipo del proyecto.
                </p>
            </div>
        </div>
    </div>
</body>
</html>
