
CREATE TABLE public.alumno (
	id serial4 NOT NULL,
	nombre varchar(100) NULL,
	carnet varchar(100) NULL,
	CONSTRAINT alumno_pkey PRIMARY KEY (id)
);

CREATE TABLE public.materia (
	id serial4 NOT NULL,
	nombre varchar(255) NOT NULL,
	descripcion varchar(255) NULL,
	codigomateria varchar(50) NULL,
	CONSTRAINT materia_pkey PRIMARY KEY (id)
);


CREATE TABLE public.inscripciones (
	id serial4 NOT NULL,
	idalumno int4 NULL,
	idmateria int4 NULL,
	ciclo varchar(50) NULL,
	año int4 NULL,
	fechainscripcion date NULL
 ,
	CONSTRAINT inscripciones_pkey PRIMARY KEY (id),
	CONSTRAINT inscripciones_alumno_id_fkey FOREIGN KEY (idalumno) REFERENCES public.alumno(id),
	CONSTRAINT inscripciones_materia_id_fkey FOREIGN KEY (idmateria) REFERENCES public.materia(id)
);
docker-compose down --rmi all && docker system prune -af --volumes && docker-compose up --build
