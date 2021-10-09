# formulario-trabajo

<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
<meta charset="UTF-8">
<title>Sistema de Gestão de Pessoas</title>

<link rel="stylesheet"
	href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
	integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z"
	crossorigin="anonymous">
</head>
<body>
	<div class="container my-2">
		<h1>Sistema de Gestão de Pessoas</h1>
		<hr>
		<h2>Editar Pessoa</h2>
		<form action="#" th:action="@{/rh/pessoas/salvar}" th:object="${pessoa}" method="POST">
			<input type="hidden" id="id" th:field="*{id}">
			<input type="text" th:field="*{nome}" placeholder="Nome" class="form-control mb-4 col-4">
      <input type="date" th:field="*{dataNascimento}" placeholder="Data Nascimento" class="form-control mb-4 col-4">
      <input type="text" th:field="*{cpf}" placeholder="CPF" class="form-control mb-4 col-4">
			<input type="text" th:field="*{email}" placeholder="Email" class="form-control mb-4 col-4">
      <input type="text" th:field="*{telefone}" placeholder="Telefone" class="form-control mb-4 col-4">
			
			<button type="submit" class="btn btn-info col-2">Salvar</button>
		</form>
		<hr>
		<a th:href="@{/rh/pessoas}">Retornar para a lista de pessoas</a>
	</div>
</body>
</html>
index.html
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
<meta charset="UTF-8">
<title>Sistema de Gestão de Pessoas</title>

<link rel="stylesheet"
	href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
	integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z"
	crossorigin="anonymous">

</head>
<body>
	<div class="container my-2">
		<a th:href="@{/rh/pessoas/nova}" class="btn btn-primary btn-sm mb-3">Incluir Pessoa</a>
		<h1>Pessoas</h1>
		<table border="1" class="table table-striped table-responsive-md">
			<thead>
				<tr>
					<th>Nome</th>
					<th>Telefone</th>
					<th>Email</th>
					<th>Ações</th>
				</tr>
			</thead>
			<tbody>
				<tr th:each="pessoa : ${listaPessoas}">
					<td th:text="${pessoa.nome}"></td>
					<td th:text="${pessoa.telefone}"></td>
					<td th:text="${pessoa.email}"></td>
					<td>			
					</td>
				</tr>
			</tbody>
		</table>
	</div>
</body>
</html>
