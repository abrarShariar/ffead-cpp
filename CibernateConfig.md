# Cibernate ORM Configuration #
```
<cibernate>
	<config>
                <!--The DB user name-->
		<uid>DB user Name</uid>
                <!--The DB user password-->
		<pwd>DB user password</pwd>
                <!--The DB Data Source name-->
		<dsn>Data Source Name</dsn>
                <!--The DB connection pool size-->
		<pool-size>5</pool-size>
                <!--The database dialect-->                 
                <dialect>MySQLDialect</dialect>
	</config>
	<tables>
                <!--The Table to Objcet Mapping-->
		<table name="test4" class="Test4">
			<col dbf="dat" obf="date"></col>
			<col dbf="datt" obf="datt"></col>
			<col dbf="datm" obf="dattm"></col>
		</table>
		<table name="person" class="Person">
                        <hasMany fk="person_id" pk="id" field="interests" relClass="Person_Interests" relfk="interest_id" relpk="id">Interest</hasMany>
			<col dbf="id" obf="id"></col>
			<col dbf="name" obf="name"></col>
                        <col dbf="age" obf="age"></col>
                        <hasOne fk="life_id" pk="id" field="life" lazy="true">Life</hasOne>
		</table>
		<table name="interest" class="Interest">
                        <hasMany fk="interest_id" pk="id" field="persons" relClass="Person_Interests" relfk="person_id" relpk="id">Person</hasMany>
                        <col dbf="id" obf="id"></col>
			<col dbf="desc" obf="desc"></col>
                        <col dbf="type" obf="type"></col>
		</table>
                <table name="person_interests" class="Person_Interests">
                        <col dbf="person_id" obf="person_id"></col>
			<col dbf="interest_id" obf="interest_id"></col>
		</table>
		<table name="life clas="Life">
                        <col dbf="life_id" obf="life_id"></col>
                        <col dbf="desc" obf="desc"></col>
                        <col dbf="type" obf="type"></col>
		</table>
	</tables>
</cibernate>
```