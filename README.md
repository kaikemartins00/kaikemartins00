import React from "react";
import {
  Coffee,
  Leaf,
  ShieldCheck,
  KeyRound,
  Database,
  Link2,
  Package,
  GitBranch,
  FileJson,
  Send,
  Wrench,
  Brain,
  Github,
  Linkedin,
  Mail,
  Terminal,
  GitCommit,
  Braces,
  Atom,
  FileCode,
  Palette,
} from "lucide-react";

const stack = [
  { icon: Coffee, label: "Java" },
  { icon: Leaf, label: "Spring Boot" },
  { icon: ShieldCheck, label: "Spring Security" },
  { icon: KeyRound, label: "JWT" },
  { icon: Database, label: "PostgreSQL" },
  { icon: Leaf, label: "MongoDB" },
  { icon: Link2, label: "APIs REST" },
  { icon: Package, label: "Docker" },
  { icon: Package, label: "Maven" },
  { icon: GitBranch, label: "Git & GitHub" },
  { icon: FileJson, label: "JSON / XML" },
  { icon: Wrench, label: "JPA / Hibernate" },
  { icon: Send, label: "Postman" },
  { icon: Brain, label: "POO" },
  { icon: Braces, label: "JavaScript" },
  { icon: Atom, label: "React" },
  { icon: FileCode, label: "HTML5" },
  { icon: Palette, label: "CSS3" },
];

const projects = [
  {
    method: "GET",
    path: "/projects/helpdesk-api",
    name: "HelpDeskAPI",
    status: 200,
    desc: "Sistema de gerenciamento de chamados.",
    tech: ["Java", "Spring Boot", "PostgreSQL", "JPA/Hibernate", "Docker"],
  },
  {
    method: "GET",
    path: "/projects/stockmanager-api",
    name: "StockManagerAPI",
    status: 200,
    desc: "API para gerenciamento de estoque.",
    tech: ["Java", "Spring Boot", "Spring Security + JWT", "PostgreSQL", "Docker"],
  },
];

const education = [
  {
    tag: "v1.0.0",
    state: "IN_PROGRESS",
    title: "Tecnólogo em Análise e Desenvolvimento de Sistemas",
    org: "Faculdade Maurício de Nassau",
  },
  {
    tag: "v2.0.0",
    state: "PLANNED",
    title: "Bacharelado em Engenharia de Software",
    org: "Uniasselvi",
  },
];

export default function Portfolio() {
  return (
    <div className="kmport">
      <style>{`
        .kmport {
          --bg: #0a0e14;
          --surface: #10161f;
          --surface-alt: #131a24;
          --border: #212938;
          --text: #dbe2ea;
          --text-dim: #7c8798;
          --java: #e8720c;
          --java-dim: #4a3220;
          --spring: #6db33f;
          --spring-dim: #253a1c;
          --gold: #e8b93d;
          --mono: 'JetBrains Mono', 'Fira Code', ui-monospace, SFMono-Regular, Menlo, monospace;
          --sans: 'Inter', system-ui, -apple-system, sans-serif;

          background: var(--bg);
          color: var(--text);
          font-family: var(--sans);
          min-height: 100vh;
          padding: 40px 16px;
          box-sizing: border-box;
          display: flex;
          justify-content: center;
        }
        .kmport * { box-sizing: border-box; }
        .kmport .frame {
          width: 100%;
          max-width: 760px;
        }

        /* file tab */
        .kmport .tab {
          display: flex;
          align-items: center;
          gap: 10px;
          background: var(--surface);
          border: 1px solid var(--border);
          border-bottom: none;
          border-radius: 10px 10px 0 0;
          padding: 12px 16px;
          font-family: var(--mono);
          font-size: 13px;
          color: var(--text-dim);
        }
        .kmport .dots { display: flex; gap: 6px; margin-right: 4px; }
        .kmport .dot { width: 10px; height: 10px; border-radius: 50%; }
        .kmport .dot.r { background: #ff5f56; }
        .kmport .dot.y { background: #ffbd2e; }
        .kmport .dot.g { background: #27c93f; }
        .kmport .tab span.file { color: var(--text); }

        .kmport .body {
          border: 1px solid var(--border);
          border-radius: 0 0 10px 10px;
          background: var(--surface);
          padding: 32px;
        }

        /* header */
        .kmport .head {
          display: flex;
          gap: 20px;
          align-items: center;
          margin-bottom: 22px;
        }
        .kmport .avatar {
          width: 68px;
          height: 68px;
          border-radius: 14px;
          background: linear-gradient(135deg, var(--java), var(--spring));
          display: flex;
          align-items: center;
          justify-content: center;
          font-family: var(--mono);
          font-weight: 700;
          font-size: 22px;
          color: #0a0e14;
          flex-shrink: 0;
        }
        .kmport h1 {
          margin: 0 0 6px 0;
          font-family: var(--mono);
          font-size: 26px;
          letter-spacing: -0.5px;
          color: var(--text);
        }
        .kmport .role {
          display: inline-flex;
          align-items: center;
          gap: 6px;
          font-family: var(--mono);
          font-size: 12px;
          color: var(--java);
          background: var(--java-dim);
          border: 1px solid #6b4420;
          padding: 4px 10px;
          border-radius: 6px;
        }

        .kmport .bio {
          font-size: 14.5px;
          line-height: 1.7;
          color: var(--text-dim);
          margin: 0 0 20px 0;
        }
        .kmport .bio b { color: var(--text); font-weight: 600; }

        .kmport .badges { display: flex; flex-wrap: wrap; gap: 10px; margin-bottom: 30px; }
        .kmport .badge {
          display: inline-flex;
          align-items: center;
          gap: 6px;
          padding: 7px 12px;
          border-radius: 6px;
          font-family: var(--mono);
          font-size: 12px;
          text-decoration: none;
          border: 1px solid var(--border);
          color: var(--text);
          background: var(--surface-alt);
          transition: border-color 0.15s ease;
        }
        .kmport .badge:hover { border-color: var(--java); }
        .kmport .badge svg { width: 14px; height: 14px; }

        .kmport .section-title {
          display: flex;
          align-items: center;
          gap: 8px;
          font-family: var(--mono);
          font-size: 13px;
          color: var(--text-dim);
          text-transform: uppercase;
          letter-spacing: 1px;
          margin: 0 0 14px 0;
          padding-bottom: 10px;
          border-bottom: 1px solid var(--border);
        }
        .kmport .section-title svg { width: 15px; height: 15px; color: var(--spring); }

        .kmport section { margin-bottom: 32px; }

        /* stack */
        .kmport .stack-grid {
          display: grid;
          grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
          gap: 10px;
        }
        .kmport .stack-item {
          display: flex;
          align-items: center;
          gap: 8px;
          background: var(--surface-alt);
          border: 1px solid var(--border);
          border-radius: 7px;
          padding: 9px 11px;
          font-size: 12.5px;
          font-family: var(--mono);
          color: var(--text);
        }
        .kmport .stack-item svg { width: 15px; height: 15px; color: var(--spring); flex-shrink: 0; }

        /* projects as api responses */
        .kmport .proj-card {
          background: var(--surface-alt);
          border: 1px solid var(--border);
          border-radius: 8px;
          overflow: hidden;
          margin-bottom: 14px;
        }
        .kmport .proj-req {
          display: flex;
          align-items: center;
          gap: 10px;
          padding: 12px 14px;
          font-family: var(--mono);
          font-size: 12.5px;
          border-bottom: 1px solid var(--border);
        }
        .kmport .method {
          background: var(--spring-dim);
          color: var(--spring);
          padding: 2px 8px;
          border-radius: 4px;
          font-weight: 700;
          font-size: 11px;
        }
        .kmport .path { color: var(--text-dim); flex: 1; }
        .kmport .status {
          font-size: 11px;
          color: var(--spring);
          font-weight: 700;
        }
        .kmport .proj-body { padding: 14px; }
        .kmport .proj-name {
          font-family: var(--mono);
          font-size: 15px;
          color: var(--text);
          margin: 0 0 6px 0;
          font-weight: 600;
        }
        .kmport .proj-desc { font-size: 13.5px; color: var(--text-dim); margin: 0 0 12px 0; }
        .kmport .tech-row { display: flex; flex-wrap: wrap; gap: 6px; }
        .kmport .tech-chip {
          font-family: var(--mono);
          font-size: 11px;
          color: var(--gold);
          background: rgba(232, 185, 61, 0.08);
          border: 1px solid rgba(232, 185, 61, 0.25);
          padding: 3px 8px;
          border-radius: 4px;
        }

        /* education as version log */
        .kmport .edu-item {
          display: flex;
          gap: 14px;
          padding: 12px 0;
          border-bottom: 1px solid var(--border);
        }
        .kmport .edu-item:last-child { border-bottom: none; }
        .kmport .edu-tag {
          font-family: var(--mono);
          font-size: 12px;
          color: var(--java);
          flex-shrink: 0;
          width: 62px;
        }
        .kmport .edu-state {
          font-family: var(--mono);
          font-size: 10px;
          padding: 2px 6px;
          border-radius: 4px;
          height: fit-content;
          margin-top: 1px;
        }
        .kmport .edu-state.progress { background: var(--java-dim); color: var(--java); }
        .kmport .edu-state.planned { background: var(--surface); color: var(--text-dim); border: 1px solid var(--border); }
        .kmport .edu-title { font-size: 13.5px; color: var(--text); margin: 0 0 3px 0; }
        .kmport .edu-org { font-size: 12px; color: var(--text-dim); margin: 0; }

        /* footer */
        .kmport .footer {
          display: flex;
          gap: 10px;
          padding-top: 22px;
          border-top: 1px solid var(--border);
        }
        .kmport .footer a {
          flex: 1;
          display: flex;
          align-items: center;
          justify-content: center;
          gap: 8px;
          padding: 11px;
          border-radius: 7px;
          font-family: var(--mono);
          font-size: 12.5px;
          text-decoration: none;
          color: #0a0e14;
          font-weight: 700;
        }
        .kmport .footer a.li { background: #0a66c2; color: #fff; }
        .kmport .footer a.mail { background: var(--java); color: #0a0e14; }
        .kmport .footer a svg { width: 15px; height: 15px; }

        @media (max-width: 480px) {
          .kmport .body { padding: 20px; }
          .kmport h1 { font-size: 21px; }
          .kmport .head { gap: 14px; }
          .kmport .avatar { width: 56px; height: 56px; font-size: 18px; }
          .kmport .stack-grid { grid-template-columns: repeat(auto-fill, minmax(105px, 1fr)); }
          .kmport .footer { flex-direction: column; }
        }
      `}</style>

      <div className="frame">
        <div className="tab">
          <div className="dots">
            <span className="dot r" />
            <span className="dot y" />
            <span className="dot g" />
          </div>
          <Terminal size={14} />
          kaikemartins / <span className="file">README.md</span>
        </div>

        <div className="body">
          <div className="head">
            <div className="avatar">KM</div>
            <div>
              <h1>Kaike Martins</h1>
              <span className="role">
                <Coffee size={13} /> Desenvolvedor Backend Java
              </span>
            </div>
          </div>

          <p className="bio">
            <b>☕ Java</b> · <b>Spring Boot</b> · APIs REST e banco de dados. Atualmente
            cursando Análise e Desenvolvimento de Sistemas e iniciando Engenharia de
            Software, desenvolvendo projetos com Java, Spring Boot, PostgreSQL, Docker,
            JPA/Hibernate e arquitetura backend — compartilhando minha evolução e
            projetos práticos na área de desenvolvimento de software. Também tenho
            base em <b>JavaScript, React, HTML e CSS</b>, o que me ajuda a entender o
            fluxo completo de uma aplicação, do front ao back.
          </p>

          <div className="badges">
            <a
              className="badge"
              href="https://linkedin.com/in/kaikemartins00"
              target="_blank"
              rel="noreferrer"
            >
              <Linkedin /> linkedin.com/in/kaikemartins00
            </a>
            <a className="badge" href="mailto:kaikesantos739@gmail.com">
              <Mail /> kaikesantos739@gmail.com
            </a>
            <a className="badge" href="#" onClick={(e) => e.preventDefault()}>
              <Github /> github.com/kaikemartins
            </a>
          </div>

          <section>
            <p className="section-title">
              <GitCommit /> Stack &amp; Ferramentas
            </p>
            <div className="stack-grid">
              {stack.map(({ icon: Icon, label }) => (
                <div className="stack-item" key={label}>
                  <Icon />
                  {label}
                </div>
              ))}
            </div>
          </section>

          <section>
            <p className="section-title">
              <FileJson /> Projetos em Destaque
            </p>
            {projects.map((p) => (
              <div className="proj-card" key={p.name}>
                <div className="proj-req">
                  <span className="method">{p.method}</span>
                  <span className="path">{p.path}</span>
                  <span className="status">{p.status} OK</span>
                </div>
                <div className="proj-body">
                  <p className="proj-name">{p.name}</p>
                  <p className="proj-desc">{p.desc}</p>
                  <div className="tech-row">
                    {p.tech.map((t) => (
                      <span className="tech-chip" key={t}>
                        {t}
                      </span>
                    ))}
                  </div>
                </div>
              </div>
            ))}
          </section>

          <section style={{ marginBottom: 8 }}>
            <p className="section-title">
              <GitBranch /> Formação Acadêmica
            </p>
            {education.map((e) => (
              <div className="edu-item" key={e.title}>
                <span className="edu-tag">{e.tag}</span>
                <span className={`edu-state ${e.state === "IN_PROGRESS" ? "progress" : "planned"}`}>
                  {e.state === "IN_PROGRESS" ? "cursando" : "a iniciar"}
                </span>
                <div>
                  <p className="edu-title">{e.title}</p>
                  <p className="edu-org">{e.org}</p>
                </div>
              </div>
            ))}
          </section>

          <div className="footer">
            <a className="li" href="https://linkedin.com/in/kaikemartins00" target="_blank" rel="noreferrer">
              <Linkedin /> LinkedIn
            </a>
            <a className="mail" href="mailto:kaikesantos739@gmail.com">
              <Mail /> Gmail
            </a>
          </div>
        </div>
      </div>
    </div>
  );
}
