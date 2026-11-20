# Validador y Blindaje de Seguridad para Pipelines RAG - TAVARDT España

> Auditoría de Aislamiento de Contexto, Prevención de Inyección Indirecta y Protección Defensiva de IA

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Active-brightgreen)](https://tavardt-espana.github.io/rag-security-hardener-es/)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Security: OWASP LLM](https://img.shields.io/badge/Security-OWASP%20LLM01%20%7C%20LLM02-red.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

## Visión General de la Arquitectura y Seguridad RAG

El ecosistema de Recuperación Aumentada por Generación (RAG) introduce vectores críticos de vulnerabilidad en aplicaciones corporativas de inteligencia artificial. Al ingerir documentos externos y bases de conocimiento para alimentar el contexto de los modelos de lenguaje (LLMs), la aplicación queda expuesta a Inyección Indirecta de Prompt (OWASP LLM01) y Fuga de Datos Multi-inquilino (OWASP LLM02).

Este repositorio proporciona tanto una aplicación web interactiva que se ejecuta 100% en el navegador como una herramienta CLI en Python para auditar arquitecturas RAG y generar plantillas de blindaje defensivo.

## Aplicación Web Interactiva (GitHub Pages)

Acceda a la herramienta online y audite su pipeline en tiempo real:

- [https://tavardt-espana.github.io/rag-security-hardener-es/](https://tavardt-espana.github.io/rag-security-hardener-es/)

## Uso del Scanner CLI (Python)

La herramienta `rag_security_hardener.py` funciona exclusivamente con la biblioteca estándar de Python (sin dependencias externas) y permite automatizar la auditoría en pipelines de CI/CD o entornos locales.

```bash
# Executar avaliacao interativa com parametros padrao
python rag_security_hardener.py

# Exportar middleware defensivo para uso imediato em seu pipeline
python rag_security_hardener.py --export-blueprint secure_rag_middleware.py

# Executar auditoria em modo JSON para integracao em CI/CD
python rag_security_hardener.py --ingestion 3 --vector-db 3 --context-boundary 3 --indirect-filter 3 --json
```

## Controles Arquitectónicos y Mitigaciones Defensivas

1. **Aislamiento de Contexto**: Encapsulación estricta del contexto recuperado utilizando etiquetas XML delimitadoras (`<untrusted_context>`) e instrucciones de sistema seguras.
2. **Prevención de Inyección Indirecta**: Sanitización heurística de instrucciones incrustadas y anomalías semánticas en documentos ingeridos.
3. **Aislamiento Multi-inquilino (Multi-Tenant RBAC)**: Segregación estricta de vectores por namespaces y validación de permisos en tiempo de consulta.
4. **Puerta de Salida y Supervisión de Citas**: Verificación de atribución de respuestas y enmascaramiento activo de datos confidenciales.

## Portales Oficiales

- **Portal Oficial TAVARDT**: [https://tavardt.es](https://tavardt.es)
- **Centro de Herramientas**: [https://tools.tavardt.es](https://tools.tavardt.es)
- **Contacto**: [https://tavardt.es/contacto](https://tavardt.es/contacto)

---
&copy; 2026 TAVARDT España. Todos los derechos reservados.
