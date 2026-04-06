<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LexMark | Inteligência Jurídica</title>
    <script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body { margin: 0; background: #0a0a0f; color: #d4d0c8; font-family: 'DM Sans', sans-serif; }
        .card { background: #12121a; border: 1px solid #c9a84c33; border-radius: 15px; padding: 25px; margin-bottom: 20px; }
        .btn-gold { background: linear-gradient(135deg, #c9a84c, #e8c96d); color: #0a0a0f; border: none; padding: 15px; border-radius: 10px; font-weight: bold; width: 100%; cursor: pointer; }
    </style>
</head>
<body>
    <div id="root"></div>
    <script type="text/babel">
        const { useState } = React;
        function App() {
            const [tema, setTema] = useState("");
            const [res, setRes] = useState("");
            const [loading, setLoading] = useState(false);

            const gerar = async () => {
                setLoading(true);
                // Aqui vai a lógica da IA que conversamos
                setTimeout(() => {
                    setRes("<strong>Post Gerado:</strong><br/>Conteúdo jurídico pronto para o Instagram da Débora!");
                    setLoading(false);
                }, 1500);
            };

            return (
                <div style={{ padding: '20px', maxWidth: '500px', margin: '0 auto' }}>
                    <h1 style={{ color: '#e8c96d', textAlign: 'center' }}>⚖️ LexMark</h1>
                    <div className="card">
                        <input style={{ width: '100%', padding: '12px', background: '#1a1a26', border: '1px solid #c9a84c44', color: '#fff', borderRadius: '8px', marginBottom: '15px' }} 
                               placeholder="Tema do post..." onChange={e => setTema(e.target.value)} />
                        <button className="btn-gold" onClick={gerar}>{loading ? "Gerando..." : "GERAR CONTEÚDO"}</button>
                    </div>
                    {res && <div className="card" dangerouslySetInnerHTML={{ __html: res }} />}
                </div>
            );
        }
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
