<p align="center"><img src="header.svg" alt="" width="100%"/></p>

<pre align="center">
<span style="color:#8b949e">// Patricio Antonio García Pérez Vela</span>
<span style="color:#8b949e">// Software Engineer — Learning AI Development</span>
<span style="color:#8b949e">// Guanajuato, México 🇲🇽</span>
</pre>

<br>

<pre>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>
<span style="color:#8b949e">// ~/about.ts</span>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>

<span style="color:#ff7b72">const</span> <span style="color:#79c0ff">profile</span> <span style="color:#ff7b72">=</span> {
  <span style="color:#79c0ff">name</span>        : <span style="color:#a5d6ff">"Patricio Antonio García Pérez Vela"</span>,
  <span style="color:#79c0ff">role</span>        : <span style="color:#a5d6ff">"Software Engineer & Learning AI Development"</span>,
  <span style="color:#79c0ff">location</span>    : <span style="color:#a5d6ff">"Guanajuato, México 🇲🇽"</span>,
  <span style="color:#79c0ff">education</span>   : <span style="color:#a5d6ff">"B.Sc. Computer Systems Engineering — UGTO"</span>,
  <span style="color:#79c0ff">gpa</span>         : <span style="color:#a5d6ff">"9.4 / 10.0"</span>,
  <span style="color:#79c0ff">status</span>      : <span style="color:#a5d6ff">"Graduated — Dec 2025"</span>,
  <span style="color:#79c0ff">focus</span>       : [<span style="color:#a5d6ff">"Sovereign AI"</span>, <span style="color:#a5d6ff">"Full-Stack"</span>, <span style="color:#a5d6ff">"NLP"</span>],
  <span style="color:#79c0ff">building</span>    : [<span style="color:#a5d6ff">"WisprLocal"</span>, <span style="color:#a5d6ff">"Nue.ai"</span>, <span style="color:#a5d6ff">"DEMOX"</span>],
  <span style="color:#79c0ff">philosophy</span>  : <span style="color:#a5d6ff">"Hay que dar un paso a la vez. Solo uno a la vez."</span>,
}

<span style="color:#ff7b72">export default</span> <span style="color:#79c0ff">profile</span>
</pre>

<br>

<pre>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>
<span style="color:#8b949e">// ~/stack.ts</span>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>

<span style="color:#ff7b72">const</span> <span style="color:#79c0ff">stack</span> <span style="color:#ff7b72">=</span> {
  <span style="color:#79c0ff">languages</span>   : [<span style="color:#a5d6ff">"Python"</span>, <span style="color:#a5d6ff">"TypeScript"</span>, <span style="color:#a5d6ff">"JavaScript"</span>, <span style="color:#a5d6ff">"Go"</span>, <span style="color:#a5d6ff">"C#"</span>, <span style="color:#a5d6ff">"C++"</span>],
  <span style="color:#79c0ff">frontend</span>    : [<span style="color:#a5d6ff">"React"</span>, <span style="color:#a5d6ff">"Next.js"</span>, <span style="color:#a5d6ff">"Vue"</span>, <span style="color:#a5d6ff">"NuxtJS"</span>, <span style="color:#a5d6ff">"Flutter"</span>],
  <span style="color:#79c0ff">backend</span>     : [<span style="color:#a5d6ff">"FastAPI"</span>, <span style="color:#a5d6ff">"Node.js"</span>, <span style="color:#a5d6ff">"Express"</span>, <span style="color:#a5d6ff">".NET"</span>],
  <span style="color:#79c0ff">ai</span>          : [<span style="color:#a5d6ff">"TensorFlow"</span>, <span style="color:#a5d6ff">"PyTorch"</span>, <span style="color:#a5d6ff">"spaCy"</span>, <span style="color:#a5d6ff">"Whisper"</span>, <span style="color:#a5d6ff">"Ollama"</span>],
  <span style="color:#79c0ff">databases</span>   : [<span style="color:#a5d6ff">"PostgreSQL"</span>, <span style="color:#a5d6ff">"MongoDB"</span>, <span style="color:#a5d6ff">"Redis"</span>, <span style="color:#a5d6ff">"SQL Server"</span>],
  <span style="color:#79c0ff">devops</span>      : [<span style="color:#a5d6ff">"Docker"</span>, <span style="color:#a5d6ff">"Git"</span>, <span style="color:#a5d6ff">"Linux"</span>, <span style="color:#a5d6ff">"WSL2"</span>, <span style="color:#a5d6ff">"Fly.io"</span>, <span style="color:#a5d6ff">"Render"</span>],
}
</pre>

<br>

<pre>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>
<span style="color:#8b949e">// ~/projects.ts</span>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>

<span style="color:#ff7b72">const</span> <span style="color:#79c0ff">projects</span> <span style="color:#ff7b72">=</span> [
  {
    <span style="color:#79c0ff">name</span>  : <span style="color:#a5d6ff">"WisprLocal"</span>,
    <span style="color:#79c0ff">desc</span>  : <span style="color:#a5d6ff">"Sovereign voice AI — local STT + TTS + LLM on RTX 4060 / WSL2"</span>,
    <span style="color:#79c0ff">tech</span>  : [<span style="color:#a5d6ff">"Python"</span>, <span style="color:#a5d6ff">"Whisper"</span>, <span style="color:#a5d6ff">"Ollama"</span>, <span style="color:#a5d6ff">"CUDA"</span>],
  },
  {
    <span style="color:#79c0ff">name</span>  : <span style="color:#a5d6ff">"Nue.ai"</span>,
    <span style="color:#79c0ff">desc</span>  : <span style="color:#a5d6ff">"AI-powered style assistant — GPT-4o + Gemini Vision"</span>,
    <span style="color:#79c0ff">tech</span>  : [<span style="color:#a5d6ff">"Python"</span>, <span style="color:#a5d6ff">"FastAPI"</span>, <span style="color:#a5d6ff">"Next.js"</span>],
  },
  {
    <span style="color:#79c0ff">name</span>  : <span style="color:#a5d6ff">"DEMOX"</span>,
    <span style="color:#79c0ff">desc</span>  : <span style="color:#a5d6ff">"Political intelligence platform — NLP + pgvector"</span>,
    <span style="color:#79c0ff">tech</span>  : [<span style="color:#a5d6ff">"FastAPI"</span>, <span style="color:#a5d6ff">"Next.js"</span>, <span style="color:#a5d6ff">"spaCy"</span>, <span style="color:#a5d6ff">"Supabase"</span>, <span style="color:#a5d6ff">"Docker"</span>],
  },
  {
    <span style="color:#79c0ff">name</span>  : <span style="color:#a5d6ff">"infinite-tic-tac-toe"</span>,
    <span style="color:#79c0ff">desc</span>  : <span style="color:#a5d6ff">"Recursive strategy game engine"</span>,
    <span style="color:#79c0ff">tech</span>  : [<span style="color:#a5d6ff">"TypeScript"</span>, <span style="color:#a5d6ff">"React"</span>],
  },
]
</pre>

<br>

<pre>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>
<span style="color:#8b949e">// ~/experience.ts</span>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>

<span style="color:#ff7b72">const</span> <span style="color:#79c0ff">experience</span> <span style="color:#ff7b72">=</span> [
  {
    <span style="color:#79c0ff">company</span>   : <span style="color:#a5d6ff">"Mazda Motor Mexico"</span>,
    <span style="color:#79c0ff">role</span>      : <span style="color:#a5d6ff">"Software Engineer (Intern)"</span>,
    <span style="color:#79c0ff">period</span>    : <span style="color:#a5d6ff">"Aug 2025 → Feb 2026"</span>,
    <span style="color:#79c0ff">highlights</span>: [
      <span style="color:#a5d6ff">"Built end-to-end DMS in C# / .NET + SQL Server"</span>,
      <span style="color:#a5d6ff">"Cut document-search time & eliminated manual errors"</span>,
    ],
  },
]
</pre>

<br>

<pre>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>
<span style="color:#8b949e">// ~/contact.ts</span>
<span style="color:#8b949e">// ─────────────────────────────────────────────────────────────────────</span>

<span style="color:#ff7b72">const</span> <span style="color:#79c0ff">contact</span> <span style="color:#ff7b72">=</span> {
  <span style="color:#79c0ff">email</span>     : <span style="color:#a5d6ff">"<a href="mailto:pa.garciaperezvela@ugto.mx" style="color:#58a6ff;text-decoration:none">pa.garciaperezvela@ugto.mx</a>"</span>,
  <span style="color:#79c0ff">linkedin</span>  : <span style="color:#a5d6ff">"<a href="https://www.linkedin.com/in/patricioagpv/" style="color:#58a6ff;text-decoration:none">linkedin.com/in/patricioagpv</a>"</span>,
  <span style="color:#79c0ff">github</span>    : <span style="color:#a5d6ff">"<a href="https://github.com/p5Patricio" style="color:#58a6ff;text-decoration:none">github.com/p5Patricio</a>"</span>,
}
</pre>

<br>

<pre align="center">
  <img src="now-playing.svg" alt="Now Playing" width="400"/>
</pre>

<br>

<pre align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/p5Patricio/p5Patricio/output/github-snake-dark.svg"/>
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/p5Patricio/p5Patricio/output/github-snake.svg"/>
    <img alt="github-snake" src="https://raw.githubusercontent.com/p5Patricio/p5Patricio/output/github-snake.svg"/>
  </picture>
</pre>

<br>

<pre align="center">
  <span style="color:#8b949e"><i>// Hay que dar un paso a la vez. Solo uno a la vez.</i></span>
</pre>

<p align="center"><img src="footer.svg" alt="" width="100%"/></p>
