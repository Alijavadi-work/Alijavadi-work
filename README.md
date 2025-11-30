<!-- FILE: index.html -->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>GitHub Skill Banner</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Small responsive banner you can embed as a GitHub repository asset or link from your README -->
  <div class="banner">
    <div class="badge">HTML</div>
    <div class="divider"></div>
    <div class="badge css">CSS</div>
  </div>
</body>
</html>


/* ------------------------------------------------------------------ */
/* FILE: styles.css                                                    */
/* Save this as "styles.css" next to index.html in your repo.         */
/* ------------------------------------------------------------------ */

:root{
  --bg:#0f1724;            /* banner background (dark) */
  --glass: rgba(255,255,255,0.06);
  --html-start:#ff6b35;    /* HTML gradient start */
  --html-end:#ffbe40;      /* HTML gradient end */
  --css-start:#4fd1c5;     /* CSS gradient start */
  --css-end:#3b82f6;       /* CSS gradient end */
  --text:#f8fafc;
}

*{box-sizing:border-box}
html,body{height:100%;margin:0;font-family:Inter,ui-sans-serif,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial}
body{display:flex;align-items:center;justify-content:center;background:linear-gradient(180deg,#071024 0%, #081127 100%);padding:32px}

.banner{
  display:inline-flex;
  gap:12px;
  align-items:center;
  padding:10px 16px;
  border-radius:14px;
  background:linear-gradient(135deg,var(--glass), rgba(255,255,255,0.02));
  backdrop-filter: blur(6px);
  box-shadow: 0 6px 20px rgba(2,6,23,0.6), inset 0 1px 0 rgba(255,255,255,0.02);
}

.badge{
  font-weight:700;
  color:var(--text);
  padding:8px 14px;
  border-radius:10px;
  font-size:14px;
  letter-spacing:0.6px;
  display:inline-flex;
  align-items:center;
  justify-content:center;
  min-width:68px;
  text-align:center;
  transform-origin:center;
  transition:transform .28s cubic-bezier(.2,.9,.3,1), box-shadow .28s;
  box-shadow: 0 6px 18px rgba(2,6,23,0.5);
}

.badge:first-child{ /* HTML badge gradient */
  background:linear-gradient(120deg,var(--html-start), var(--html-end));
  color:#06121a;
}

.badge.css{ /* CSS badge gradient and italic style */
  background:linear-gradient(120deg,var(--css-start), var(--css-end));
  font-style:italic;
}

.badge:hover{transform: translateY(-6px) scale(1.02); box-shadow: 0 14px 30px rgba(11,22,40,0.6)}

.divider{width:1px;height:34px;border-radius:2px;background:linear-gradient(180deg,rgba(255,255,255,0.06),rgba(255,255,255,0.02));}

/* small responsive scale for embedding in README as an image preview */
@media (max-width:420px){
  .banner{padding:8px 10px;border-radius:10px}
  .badge{padding:6px 8px;font-size:13px;min-width:56px}
  .divider{height:28px}
}

/* Optional: subtle animated shine */
.banner::after{
  content:'';
  position:absolute;
  inset:0;
  border-radius:14px;
  pointer-events:none;
  background:linear-gradient(120deg, rgba(255,255,255,0.02) 0%, rgba(255,255,255,0.00) 40%, rgba(255,255,255,0.03) 70%, rgba(255,255,255,0.02) 100%);
  mix-blend-mode:overlay;
}

