# 지시자 

directives(지시자)는 일반적인 프로그램 언어와는 달리 태그 형식을 이용하여 JSP 페이지에 대한 속성 또는 특별한 지시 사항을 지정하는 태그이다.

|종류|형태|용도
|---|---|---|
|page|<%@ page property="property_value" %>|JSP 페이지에 대한 속성지정|
|include|<@ include file="file_name" %>|태그 부분에 지정한 페이지를 정적으로 삽입|
|taglib|<%@ taglib uri="uri-value" prifix="pfx-value" %>|새로운 태그를 정의하여 사용|