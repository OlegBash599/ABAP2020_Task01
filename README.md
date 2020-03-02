# ABAP2020_Task01
Получение описания к значению домена

<h2>Описание решаемой задачи </h2>
По заданному ID-домена и значению функционал возвращает описание к этому домену.
Функционал работает как по доменам с указанными значениями, с диапазонами, а также с привязанными таблицами.

<h2>Алгоритм решения задачи</h2>
Система проверяет наличие у домена привязанной таблица и текстовой таблице к этой таблице. Если таковые имеются, то выбор производится из текстовой таблицы.
Если у домена нет привязанной таблицы, но есть "твердные значения", то нужно вернуть описание этого значения. Если значение входит в диапазон, то вернуть описание диапазона.
Если нет привязанной таблице с текстовой таблицей, и нет твердных значений, то системы пытается найти "специальную обработку" для домена.
Если нет и таковой - то генерится исключение или возвращается пустое значение (в зависимости от строгости режима).

<h3>Цель функционала</h3>
<ol>
 <li>Минимизировать количество кода в клиентской программе </li>
 <li>Снизить количество обращений к базе данных </li> 
  <ol>
    <li>Не читать значение, которое уже было прочитано ранее</li> 
    <li>Для полностью прочитанных таблиц - не обращаться в базу повторно, даже при отсутствии значения </li> 
  </ol>
</ol>

<h4>Справка</h4>
Для загрузки-выгрузки использовать ABAPGIT https://docs.abapgit.org/
Namespace и пакет для разработки: ZLSP020 Чтение значений домена

<h4>Версия системы</h4>
ABAP 731 и выше
