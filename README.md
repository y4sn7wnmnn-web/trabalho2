# trabalho2
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Poison Estética Automotiva</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="app">

  <aside class="sidebar">
    <div class="brand">
      <div class="brand-mark">P</div>
      <div>
        <strong>POISON</strong>
        <span>ESTÉTICA AUTOMOTIVA</span>
      </div>
    </div>

    <nav>
      <button class="nav-item active" data-page="inicio">
        ⌂ <span>Início</span>
      </button>

      <button class="nav-item" data-page="servicos">
        ▣ <span>Serviços</span>
      </button>

      <button class="nav-item" data-page="cadastrar">
        ＋ <span>Cadastrar</span>
      </button>
    </nav>
  </aside>

  <main class="content">

    <header class="topbar">
      <div>
        <h1 id="pageTitle">Painel Operacional</h1>
        <p>Bom dia, equipe Poison.</p>
      </div>

      <div class="date">01 OUT 2026</div>
    </header>

    <!-- INÍCIO -->
    <section id="inicio" class="page active-page">

      <div class="cards">

        <div class="card stat">
          <span>Serviços pendentes</span>
          <strong id="pendingCount">2</strong>
        </div>

        <div class="card stat">
          <span>Serviços concluídos</span>
          <strong id="completedCount">0</strong>
        </div>

        <div class="card stat">
          <span>Faturamento concluído</span>
          <strong id="revenue">R$ 0,00</strong>
        </div>

      </div>

      <div class="section-head">
        <h2>Agenda de hoje</h2>
        <span class="badge" id="todayCount">2 AGENDADOS</span>
      </div>

      <div id="todayList" class="appointments"></div>

      <button class="primary" data-page="servicos">
        VER TODOS OS SERVIÇOS
      </button>

    </section>

    <!-- SERVIÇOS -->
    <section id="servicos" class="page">

      <div class="section-head">

        <div>
          <h2>Agenda completa</h2>
          <p class="muted">
            Serviços cadastrados no sistema
          </p>
        </div>

        <span class="badge">PENDENTES</span>

      </div>

      <div id="serviceList" class="service-list"></div>

    </section>

    <!-- CADASTRAR -->
    <section id="cadastrar" class="page">

      <div class="form-card">

        <div class="section-head">
          <div>
            <h2>Ordem de Serviço</h2>

            <p class="muted">
              Preencha os dados para reservar um horário na agenda.
            </p>
          </div>
        </div>

        <form id="serviceForm">

          <label>
            CLIENTE
            <input
              id="client"
              type="text"
              placeholder="Nome completo"
              required
            >
          </label>

          <div class="grid-2">

            <label>
              VEÍCULO
              <input
                id="vehicle"
                type="text"
                placeholder="Modelo do veículo"
                required
              >
            </label>

            <label>
              PLACA
              <input
                id="plate"
                type="text"
                placeholder="ABC-1D23"
                required
              >
            </label>

          </div>

          <label>
            TIPO DE SERVIÇO

            <select id="type" required>

              <option value="">
                Selecione o serviço
              </option>

              <option>
                Polimento técnico
              </option>

              <option>
                Higienização interna
              </option>

              <option>
                Lavagem detalhada
              </option>

              <option>
                Vitrificação
              </option>

              <option>
                Restauração de farol
              </option>

            </select>

          </label>

          <div class="grid-2">

            <label>
              DATA
              <input id="date" type="date" required>
            </label>

            <label>
              HORÁRIO
              <input id="time" type="time" required>
            </label>

          </div>

          <label>
            VALOR (R$)

            <input
              id="value"
              type="number"
              min="0"
              step="0.01"
              value="0"
              required
            >
          </label>

          <p class="review">
            Revise os dados antes de confirmar o agendamento.
          </p>

          <div class="actions">

            <button class="primary" type="submit">
              SALVAR SERVIÇO
            </button>

            <button class="secondary" type="reset">
              NOVO SERVIÇO
            </button>

          </div>

        </form>

      </div>

    </section>

  </main>

</div>

<script src="script.js"></script>

</body>
</html>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f5f6f8;
  color: #17191c;
}

.app {
  min-height: 100vh;
  display: flex;
}

.sidebar {
  width: 245px;
  background: #101214;
  color: white;
  padding: 28px 18px;
  position: fixed;
  inset: 0 auto 0 0;
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 8px 10px 35px;
}

.brand-mark {
  width: 42px;
  height: 42px;
  border-radius: 12px;
  background: #d9ff3f;
  color: #101214;
  display: grid;
  place-items: center;
  font-size: 23px;
  font-weight: 900;
}

.brand strong {
  display: block;
  letter-spacing: 4px;
  font-size: 15px;
}

.brand span {
  display: block;
  color: #8f949a;
  font-size: 8px;
  letter-spacing: 1.5px;
  margin-top: 4px;
}

.nav-item {
  width: 100%;
  border: 0;
  background: transparent;
  color: #9da2a8;
  text-align: left;
  padding: 14px 15px;
  border-radius: 10px;
  margin: 4px 0;
  font-size: 15px;
  cursor: pointer;
}

.nav-item span {
  margin-left: 9px;
}

.nav-item:hover,
.nav-item.active {
  background: #202327;
  color: #d9ff3f;
}

.content {
  margin-left: 245px;
  width: calc(100% - 245px);
  padding: 35px 6%;
  max-width: 1300px;
}

.topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
}

.topbar h1 {
  margin: 0 0 6px;
  font-size: 29px;
}

.topbar p {
  margin: 0;
  color: #777;
}

.date {
  font-weight: bold;
  color: #777;
  font-size: 13px;
}

.cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
}

.card,
.appointment,
.service,
.form-card {
  background: white;
  border: 1px solid #e7e8eb;
  border-radius: 15px;
  padding: 23px;
  box-shadow: 0 5px 20px #00000008;
}

.stat span {
  display: block;
  color: #777;
  font-size: 13px;
  margin-bottom: 15px;
}

.stat strong {
  font-size: 27px;
}

.section-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 34px 0 17px;
}

.section-head h2 {
  margin: 0;
  font-size: 20px;
}

.muted {
  color: #7a7d82;
  margin: 6px 0 0;
  font-size: 13px;
}

.badge {
  background: #eef1f3;
  padding: 7px 11px;
  border-radius: 20px;
  font-size: 10px;
  font-weight: 800;
}

.appointments {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 18px;
  margin-bottom: 20px;
}

.appointment,
.service {
  padding: 20px;
  box-shadow: none;
}

.appointment-time {
  font-size: 12px;
  color: #777;
  margin-bottom: 8px;
}

.appointment h3 {
  margin: 0 0 7px;
  font-size: 17px;
}

.appointment p,
.service p {
  margin: 4px 0;
  color: #666;
  font-size: 13px;
}

.primary {
  border: 0;
  background: #151719;
  color: white;
  border-radius: 10px;
  padding: 13px 18px;
  font-weight: 800;
  cursor: pointer;
}

.primary:hover {
  background: #d9ff3f;
  color: #101214;
}

.secondary {
  border: 1px solid #ddd;
  background: white;
  border-radius: 10px;
  padding: 13px 18px;
  font-weight: 800;
  cursor: pointer;
}

.page {
  display: none;
}

.active-page {
  display: block;
}

.service-list {
  display: grid;
  gap: 15px;
}

.service {
  position: relative;
}

.service h3 {
  margin: 0 0 8px;
}

.status {
  position: absolute;
  right: 20px;
  top: 20px;
  color: #7e9200;
  font-weight: 800;
  font-size: 11px;
}

.form-card {
  max-width: 760px;
}

form {
  display: grid;
  gap: 17px;
}

label {
  font-size: 10px;
  font-weight: 800;
  letter-spacing: .7px;
  color: #555;
  display: grid;
  gap: 7px;
}

input,
select {
  width: 100%;
  border: 1px solid #dddfe3;
  border-radius: 9px;
  padding: 13px;
  font: inherit;
  outline: none;
  background: white;
}

input:focus,
select:focus {
  border-color: #111;
}

.grid-2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
}

.review {
  color: #777;
  font-size: 12px;
  margin: 0;
}

.actions {
  display: flex;
  gap: 10px;
}

.complete {
  margin-top: 15px;
}

@media (max-width: 800px) {

  .sidebar {
    width: 75px;
    padding: 20px 10px;
  }

  .brand {
    justify-content: center;
  }

  .brand div:not(.brand-mark) {
    display: none;
  }

  .nav-item {
    font-size: 0;
    text-align: center;
  }

  .nav-item span {
    display: none;
  }

  .content {
    margin-left: 75px;
    width: calc(100% - 75px);
    padding: 25px 4%;
  }

  .cards,
  .appointments {
    grid-template-columns: 1fr;
  }

  .grid-2 {
    grid-template-columns: 1fr;
  }

  .topbar {
    align-items: flex-start;
  }
}
const initialServices = [
  {
    id: 1,
    client: "Carlos Silva",
    vehicle: "Honda Civic",
    plate: "ABC-1D23",
    type: "Polimento técnico",
    date: "2026-10-01",
    time: "09:00",
    value: 350,
    done: false
  },

  {
    id: 2,
    client: "Mariana Costa",
    vehicle: "Jeep Compass",
    plate: "XYZ-9K87",
    type: "Higienização interna",
    date: "2026-10-01",
    time: "14:30",
    value: 280,
    done: false
  }
];

let services =
  JSON.parse(localStorage.getItem("poisonServices")) ||
  initialServices;

function money(value) {
  return Number(value).toLocaleString("pt-BR", {
    style: "currency",
    currency: "BRL"
  });
}

function save() {
  localStorage.setItem(
    "poisonServices",
    JSON.stringify(services)
  );
}

function escapeHtml(value) {
  return String(value).replace(/[&<>"']/g, function (char) {
    const entities = {
      "&": "&amp;",
      "<": "&lt;",
      ">": "&gt;",
      '"': "&quot;",
      "'": "&#039;"
    };

    return entities[char];
  });
}

function render() {

  const pending =
    services.filter(service => !service.done);

  const completed =
    services.filter(service => service.done);

  document.getElementById("pendingCount").textContent =
    pending.length;

  document.getElementById("completedCount").textContent =
    completed.length;

  const totalRevenue =
    completed.reduce(
      (total, service) =>
        total + Number(service.value),
      0
    );

  document.getElementById("revenue").textContent =
    money(totalRevenue);

  document.getElementById("todayCount").textContent =
    `${services.length} AGENDADOS`;

  document.getElementById("todayList").innerHTML =
    services.map(service => `
      <article class="appointment">

        <div class="appointment-time">
          ${service.time}
        </div>

        <h3>
          ${escapeHtml(service.client)}
        </h3>

        <p>
          ${escapeHtml(service.type)}
        </p>

        <p>
          ${escapeHtml(service.vehicle)}
          · ${escapeHtml(service.plate)}
        </p>

        <p>
          ${money(service.value)}
        </p>

      </article>
    `).join("");

  document.getElementById("serviceList").innerHTML =
    services.map(service => `
      <article class="service">

        <span class="status">
          ${service.done ? "CONCLUÍDO" : "PENDENTE"}
        </span>

        <h3>
          ${escapeHtml(service.client)}
        </h3>

        <p>
          <b>${escapeHtml(service.vehicle)}</b>
          · ${escapeHtml(service.plate)}
        </p>

        <p>
          ${escapeHtml(service.type)}
        </p>

        <p>
          ${service.date}
          às ${service.time}
          · ${money(service.value)}
        </p>

        ${
          service.done
          ? ""
          : `
            <button
              class="primary complete"
              onclick="completeService(${service.id})"
            >
              CONCLUIR
            </button>
          `
        }

      </article>
    `).join("");
}

function completeService(id) {

  const service =
    services.find(item => item.id === id);

  if (service) {
    service.done = true;

    save();
    render();
  }
}

function openPage(page) {

  document
    .querySelectorAll(".page")
    .forEach(element =>
      element.classList.remove("active-page")
    );

  document
    .getElementById(page)
    .classList.add("active-page");

  document
    .querySelectorAll(".nav-item")
    .forEach(button =>
      button.classList.toggle(
        "active",
        button.dataset.page === page
      )
    );

  if (page === "inicio") {
    document.getElementById("pageTitle").textContent =
      "Painel Operacional";
  }

  if (page === "servicos") {
    document.getElementById("pageTitle").textContent =
      "Serviços";
  }

  if (page === "cadastrar") {
    document.getElementById("pageTitle").textContent =
      "Cadastrar Atendimento";
  }
}

document.addEventListener("click", function (event) {

  const button =
    event.target.closest("[data-page]");

  if (button) {
    openPage(button.dataset.page);
  }

});

document
  .getElementById("serviceForm")
  .addEventListener("submit", function (event) {

    event.preventDefault();

    const newService = {

      id: Date.now(),

      client:
        document.getElementById("client").value,

      vehicle:
        document.getElementById("vehicle").value,

      plate:
        document
          .getElementById("plate")
          .value
          .toUpperCase(),

      type:
        document.getElementById("type").value,

      date:
        document.getElementById("date").value,

      time:
        document.getElementById("time").value,

      value:
        Number(
          document.getElementById("value").value
        ),

      done: false
    };

    services.push(newService);

    save();
    render();

    this.reset();

    openPage("servicos");
  });

render();