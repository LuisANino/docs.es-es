# [LINQ to SQL](index.md)
## [Introducción](getting-started.md)
### [Qué puede hacer con LINQ to SQL](what-you-can-do-with-linq-to-sql.md)
### [Pasos habituales para usar LINQ to SQL](typical-steps-for-using-linq-to-sql.md)
### [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
### [Aprendizaje con tutoriales](learning-by-walkthroughs.md)
#### [Tutorial: Modelo de objetos simple y consultas (Visual Basic)](walkthrough-simple-object-model-and-query-visual-basic.md)
#### [Tutorial: Realizar consultas en varias relaciones (Visual Basic)](walkthrough-querying-across-relationships-visual-basic.md)
#### [Tutorial: Manipular datos (Visual Basic)](walkthrough-manipulating-data-visual-basic.md)
#### [Tutorial: Usar solo procedimientos almacenados (Visual Basic)](walkthrough-using-only-stored-procedures-visual-basic.md)
#### [Tutorial: Modelo de objetos simple y consultas (C#)](walkthrough-simple-object-model-and-query-csharp.md)
#### [Tutorial: Realizar consultas en varias relaciones (C#)](walkthrough-querying-across-relationships-csharp.md)
#### [Tutorial: Manipular datos (C#)](walkthrough-manipulating-data-csharp.md)
#### [Tutorial: Usar solo procedimientos almacenados (C#)](walkthrough-using-only-stored-procedures-csharp.md)
## [Guía de programación](programming-guide.md)
### [Creación del modelo de objetos](creating-the-object-model.md)
#### [Generación del modelo de objetos en Visual Basic o C#](how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
#### [Generación del modelo de objetos como un archivo externo](how-to-generate-the-object-model-as-an-external-file.md)
#### [Generación de código personalizado modificando un archivo DBML](how-to-generate-customized-code-by-modifying-a-dbml-file.md)
#### [Validación de archivos DBML y de asignación externa](how-to-validate-dbml-and-external-mapping-files.md)
#### [Serialización de entidades](how-to-make-entities-serializable.md)
#### [Personalización de clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
##### [Especificación de nombres de base de datos](how-to-specify-database-names.md)
##### [Representación de tablas como clases](how-to-represent-tables-as-classes.md)
##### [Representación de columnas como miembros de clase](how-to-represent-columns-as-class-members.md)
##### [Representación de claves principales](how-to-represent-primary-keys.md)
##### [Asignación de relaciones de base de datos](how-to-map-database-relationships.md)
##### [Representación de columnas como columnas generadas por la base de datos](how-to-represent-columns-as-database-generated.md)
##### [Representación de columnas como marcas de tiempo o columnas de versión](how-to-represent-columns-as-timestamp-or-version-columns.md)
##### [Definición de tipos de datos de base de datos](how-to-specify-database-data-types.md)
##### [Representación de columnas calculadas](how-to-represent-computed-columns.md)
##### [Definición de campos de almacenamiento privado](how-to-specify-private-storage-fields.md)
##### [Representación de columnas como columnas que permiten valores null](how-to-represent-columns-as-allowing-null-values.md)
##### [Asignación de jerarquías de herencia](how-to-map-inheritance-hierarchies.md)
##### [Definición de comprobaciones con conflictos de simultaneidad](how-to-specify-concurrency-conflict-checking.md)
### [Comunicación con la base de datos](communicating-with-the-database.md)
#### [Conexión a una base de datos](how-to-connect-to-a-database.md)
#### [Ejecución directa de comandos SQL](how-to-directly-execute-sql-commands.md)
#### [Reutilización de una conexión entre un comando de ADO.NET y un objeto DataContext](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
### [Consulta de la base de datos](querying-the-database.md)
#### [Consulta de información](how-to-query-for-information.md)
#### [Recuperación de información con formato de solo lectura](how-to-retrieve-information-as-read-only.md)
#### [Control de la cantidad de datos relacionados que se recuperan](how-to-control-how-much-related-data-is-retrieved.md)
#### [Filtrado de datos relacionados](how-to-filter-related-data.md)
#### [Desactivación de la carga diferida](how-to-turn-off-deferred-loading.md)
#### [Ejecución directa de consultas SQL](how-to-directly-execute-sql-queries.md)
#### [Almacenamiento y reutilización de consultas](how-to-store-and-reuse-queries.md)
#### [Control de claves compuestas en consultas](how-to-handle-composite-keys-in-queries.md)
#### [Recuperación de muchos objetos a la vez](how-to-retrieve-many-objects-at-once.md)
#### [Filtrado en el nivel de DataContext](how-to-filter-at-the-datacontext-level.md)
#### [Ejemplos de consultas](query-examples.md)
##### [Consultas de agregado](aggregate-queries.md)
###### [Devolución del valor medio de una secuencia numérica](return-the-average-value-from-a-numeric-sequence.md)
###### [Conteo del número de elementos de una secuencia](count-the-number-of-elements-in-a-sequence.md)
###### [Búsqueda del valor máximo de una secuencia numérica](find-the-maximum-value-in-a-numeric-sequence.md)
###### [Búsqueda del valor mínimo de una secuencia numérica](find-the-minimum-value-in-a-numeric-sequence.md)
###### [Cálculo de la suma de valores de una secuencia numérica](compute-the-sum-of-values-in-a-numeric-sequence.md)
##### [Devolución del primer elemento de una secuencia](return-the-first-element-in-a-sequence.md)
##### [Devolución u omisión de elementos de una secuencia](return-or-skip-elements-in-a-sequence.md)
##### [Ordenación de los elementos de una secuencia](sort-elements-in-a-sequence.md)
##### [Agrupación de elementos de una secuencia](group-elements-in-a-sequence.md)
##### [Eliminación de elementos duplicados de una secuencia](eliminate-duplicate-elements-from-a-sequence.md)
##### [Determinación de si alguno o todos los elementos de una secuencia satisfacen una condición](determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)
##### [Concatenación de dos secuencias](concatenate-two-sequences.md)
##### [Devolución de la diferencia de conjuntos entre dos secuencias](return-the-set-difference-between-two-sequences.md)
##### [Devolución de la intersección de conjuntos de dos secuencias](return-the-set-intersection-of-two-sequences.md)
##### [Devolución de la unión de conjuntos de dos secuencias](return-the-set-union-of-two-sequences.md)
##### [Conversión de una secuencia en una matriz](convert-a-sequence-to-an-array.md)
##### [Conversión de una secuencia en una lista genérica](convert-a-sequence-to-a-generic-list.md)
##### [Conversión de un tipo en una interfaz IEnumerable genérica](convert-a-type-to-a-generic-ienumerable.md)
##### [Formulación de combinaciones y consultas entre productos](formulate-joins-and-cross-product-queries.md)
##### [Formulación de proyecciones](formulate-projections.md)
### [Realización y envío de cambios de datos](making-and-submitting-data-changes.md)
#### [Inserción de filas en la base de datos](how-to-insert-rows-into-the-database.md)
#### [Actualización de filas en la base de datos](how-to-update-rows-in-the-database.md)
#### [Eliminación de filas de la base de datos](how-to-delete-rows-from-the-database.md)
#### [Envío de cambios a la base de datos](how-to-submit-changes-to-the-database.md)
#### [Colocación entre corchetes de envíos de datos utilizando transacciones](how-to-bracket-data-submissions-by-using-transactions.md)
#### [Creación dinámica de una base de datos](how-to-dynamically-create-a-database.md)
#### [Administración de conflictos de cambios](how-to-manage-change-conflicts.md)
##### [Detección y resolución de envíos con conflictos](how-to-detect-and-resolve-conflicting-submissions.md)
##### [Determinación de cuándo se inician las excepciones de simultaneidad](how-to-specify-when-concurrency-exceptions-are-thrown.md)
##### [Determinación de en qué miembros se comprueban los conflictos de simultaneidad](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
##### [Recuperación de información de conflictos de entidades](how-to-retrieve-entity-conflict-information.md)
##### [Recuperación de información de conflictos de miembros](how-to-retrieve-member-conflict-information.md)
##### [Resolución de conflictos de simultaneidad conservando valores de base de datos](how-to-resolve-conflicts-by-retaining-database-values.md)
##### [Resolución de conflictos de simultaneidad sobrescribiendo valores de base de datos](how-to-resolve-conflicts-by-overwriting-database-values.md)
##### [Resolución de conflictos de simultaneidad mediante combinaciones con valores de base de datos](how-to-resolve-conflicts-by-merging-with-database-values.md)
### [Capacidad de depuración](debugging-support.md)
#### [Visualización del código SQL generado](how-to-display-generated-sql.md)
#### [Visualización de un conjunto de cambios](how-to-display-a-changeset.md)
#### [Visualización de comandos de LINQ to SQL](how-to-display-linq-to-sql-commands.md)
#### [Solución de problemas](troubleshooting.md)
### [Información general](background-information.md)
#### [ADO.NET y LINQ to SQL](ado-net-and-linq-to-sql.md)
#### [Análisis del código fuente de LINQ to SQL](analyzing-linq-to-sql-source-code.md)
#### [Personalización de operaciones de actualización, inserción y eliminación](customizing-insert-update-and-delete-operations.md)
##### [Personalización de operaciones: información general](customizing-operations-overview.md)
##### [Operaciones de inserción, actualización y eliminación](insert-update-and-delete-operations.md)
##### [Responsabilidades del desarrollador al invalidar un comportamiento predeterminado](responsibilities-of-the-developer-in-overriding-default-behavior.md)
##### [Adición de lógica de negocios utilizando métodos parciales](adding-business-logic-by-using-partial-methods.md)
#### [Enlace de datos](data-binding.md)
#### [Compatibilidad de herencia](inheritance-support.md)
#### [Llamadas a métodos locales](local-method-calls.md)
#### [Aplicaciones de n niveles y remotas con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
##### [N niveles de LINQ to SQL con ASP.NET](linq-to-sql-n-tier-with-aspnet.md)
##### [N niveles de LINQ to SQL con servicios web](linq-to-sql-n-tier-with-web-services.md)
##### [LINQ to SQL con aplicaciones cliente/servidor estrechamente asociadas](linq-to-sql-with-tightly-coupled-client-server-applications.md)
##### [Implementación de una lógica de negocios de n niveles](implementing-business-logic-linq-to-sql.md)
##### [Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)](data-retrieval-and-cud-operations-in-n-tier-applications.md)
#### [Identidad de objetos](object-identity.md)
#### [Modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
#### [Estados de objetos y seguimiento de cambios](object-states-and-change-tracking.md)
#### [Simultaneidad optimista: información general](optimistic-concurrency-overview.md)
#### [Conceptos sobre consultas](query-concepts.md)
##### [Consultas de LINQ to SQL](linq-to-sql-queries.md)
##### [Realización de consultas en varias relaciones](querying-across-relationships.md)
##### [Ejecución remota o ejecución local](remote-vs-local-execution.md)
##### [Carga inmediata y carga diferida](deferred-versus-immediate-loading.md)
#### [Recuperar objetos de la memoria caché de identidades](retrieving-objects-from-the-identity-cache.md)
#### [Seguridad de LINQ to SQL](security-in-linq-to-sql.md)
#### [Serialización](serialization.md)
#### [Procedimientos almacenados](stored-procedures.md)
##### [Devolución de conjuntos de filas](how-to-return-rowsets.md)
##### [Uso de procedimientos almacenados que toman parámetros](how-to-use-stored-procedures-that-take-parameters.md)
##### [Uso de procedimientos almacenados asignados en varias formas de resultados](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)
##### [Uso de procedimientos almacenados asignados en formas de resultados secuenciales](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)
##### [Personalización de operaciones utilizando procedimientos almacenados](customizing-operations-by-using-stored-procedures.md)
##### [Personalización de operaciones utilizando exclusivamente procedimientos almacenados](customizing-operations-by-using-stored-procedures-exclusively.md)
#### [Compatibilidad con transacciones](transaction-support.md)
#### [Desajustes de tipos entre SQL y CLR](sql-clr-type-mismatches.md)
#### [Asignaciones de tipos personalizadas entre SQL y CLR](sql-clr-custom-type-mappings.md)
#### [Funciones definidas por el usuario](user-defined-functions.md)
##### [Uso de funciones escalares definidas por el usuario](how-to-use-scalar-valued-user-defined-functions.md)
##### [Uso de funciones con valores de tabla definidas por el usuario](how-to-use-table-valued-user-defined-functions.md)
##### [Llamada a funciones alineadas definidas por el usuario](how-to-call-user-defined-functions-inline.md)
## [Referencia](reference.md)
### [Tipos de datos y funciones](data-types-and-functions.md)
#### [Asignación de tipos entre CLR y SQL](sql-clr-type-mapping.md)
#### [Tipos de datos básicos](basic-data-types.md)
#### [Tipos de datos booleanos](boolean-data-types.md)
#### [Semántica de null](null-semantics.md)
#### [Operadores numéricos y de comparación](numeric-and-comparison-operators.md)
#### [Operadores de secuencia](sequence-operators.md)
#### [System.Convert (Métodos)](system-convert-methods.md)
#### [System.DateTime (Métodos)](system-datetime-methods.md)
#### [System.Math (Métodos)](system-math-methods.md)
#### [System.Object (Métodos)](system-object-methods.md)
#### [System.String (Métodos)](system-string-methods.md)
#### [System.TimeSpan (Métodos)](system-timespan-methods.md)
#### [Funcionalidad no admitida](unsupported-functionality.md)
#### [System.DateTimeOffset (Métodos)](system-datetimeoffset-methods.md)
### [Asignación basada en atributos](attribute-based-mapping.md)
### [Generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md)
### [Asignación externa](external-mapping.md)
### [Preguntas más frecuentes](frequently-asked-questions.md)
### [SQL Server Compact y LINQ to SQL](sql-server-compact-and-linq-to-sql.md)
### [Traslación del operador de consulta estándar](standard-query-operator-translation.md)
## [Ejemplos](samples.md)
