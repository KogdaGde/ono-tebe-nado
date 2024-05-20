# ono-tebe-nado
Проект "Оно тебе надо"
https://github.com/KogdaGde/ono-tebe-nado.git


CREATE TABLE public.brigades (
 brigade_id character varying NOT NULL,
 brigade_name character varying
);

--
— TOC entry 228 (class 1259 OID 17749)
— Name: events; Type: TABLE; Schema: public; Owner: -
--

CREATE TABLE public.events (
 id character varying NOT NULL,
 datestart_plan timestamp without time zone,
 dateend_plan timestamp without time zone,
 well_id character varying,
 plan_fact integer,
 datestart_fact timestamp without time zone,
 dateend_fact timestamp without time zone
);

--
— TOC entry 229 (class 1259 OID 17755)
— Name: wells; Type: TABLE; Schema: public; Owner: -
--

CREATE TABLE public.wells (
 well_id integer NOT NULL,
 cluster character varying,
 well_name character varying,
 brigade_id integer
);

--
— TOC entry 3100 (class 0 OID 17765)
— Dependencies: 230
— Data for Name: brigades; Type: TABLE DATA; Schema: public; Owner: -
--

INSERT INTO public.brigades VALUES ('2', 'B 2');
INSERT INTO public.brigades VALUES ('3', 'B 3');

--
— TOC entry 3098 (class 0 OID 17749)
— Dependencies: 228
— Data for Name: events; Type: TABLE DATA; Schema: public; Owner: -
--

INSERT INTO public.events VALUES ('2', '2023-01-03 00:00:00', '2023-01-16 00:00:00', '101', 0, '2023-01-06 00:00:00', '2023-01-20 00:00:00');
INSERT INTO public.events VALUES ('1', '2023-01-01 00:00:00', '2023-01-20 00:00:00', '100', 0, '2023-02-01 00:00:00', '2023-02-12 00:00:00');
INSERT INTO public.events VALUES ('3', '2023-02-01 00:00:00', '2023-02-13 00:00:00', '102', 1, '2023-03-05 00:00:00', '2023-06-01 00:00:00');
INSERT INTO public.events VALUES ('4', '2023-02-05 00:00:00', '2023-02-07 00:00:00', '103', 1, '2023-03-07 00:00:00', '2023-05-01 00:00:00');
INSERT INTO public.events VALUES ('5', '2023-03-01 00:00:00', '2023-03-04 00:00:00', '104', 1, '2023-01-02 00:00:00', '2023-02-03 00:00:00');

--
— TOC entry 3099 (class 0 OID 17755)
— Dependencies: 229
— Data for Name: wells; Type: TABLE DATA; Schema: public; Owner: -
--

INSERT INTO public.wells VALUES (100, '2', 'W 1', 2);
INSERT INTO public.wells VALUES (101, '5', 'W 2', 3);
INSERT INTO public.wells VALUES (102, '12', 'W 3', 2);
INSERT INTO public.wells VALUES (103, '41', 'W 4', 2);
INSERT INTO public.wells VALUES (104, '13', 'W 5', 2);

--
— TOC entry 2967 (class 2606 OID 17772)
— Name: brigades brigades_pk; Type: CONSTRAINT; Schema: public; Owner: -
--

ALTER TABLE ONLY public.brigades
 ADD CONSTRAINT brigades_pk PRIMARY KEY (brigade_id);

--
— TOC entry 2963 (class 2606 OID 17762)
— Name: events events_pk; Type: CONSTRAINT; Schema: public; Owner: -
--

ALTER TABLE ONLY public.events
 ADD CONSTRAINT events_pk PRIMARY KEY (id);

--
— TOC entry 2965 (class 2606 OID 17764)
— Name: wells wells_pk; Type: CONSTRAINT; Schema: public; Owner: -
--

ALTER TABLE ONLY public.wells
 ADD CONSTRAINT wells_pk PRIMARY KEY (well_id);

— Completed on 2023-06-15 17:43:55 MSK

--
— PostgreSQL database dump complete
--