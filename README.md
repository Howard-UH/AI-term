<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <!-- SEO 優化: 頁面標題 -->
  <title>AI 名詞速通指南 - 快速掌握生成式 AI 核心概念</title>
  <!-- SEO 優化: 頁面描述 -->
  <meta name="description" content="本指南用簡潔的語言，解釋了生成式 AI 領域中的常見概念、技術細節、以及潛在的風險與機會。透過清晰的卡片式設計，助你快速建立對 AI 的共同語言。" />
  <!-- SEO 優化: Canonical URL，防止內容重複問題 -->
  <link rel="canonical" href="https://your-domain.com/ai-glossary" />
  
  <!-- 引入 React 與 ReactDOM -->
  <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
  <!-- 引入 Babel 轉譯器，用於處理 JSX -->
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

  <!-- 引入 Tailwind CSS，並在配置中新增設計代幣 -->
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            // 定義客製化的設計代幣顏色
            'concept-common': '#A855F7', // 紫色
            'concept-tech': '#3B82F6', // 藍色
            'concept-opportunity': '#22C55E', // 綠色
            // shadcn/ui 的預設顏色，為了讓卡片元件能正常運作
            border: 'hsl(214.3, 31.8%, 91.4%)',
            background: 'hsl(0, 0%, 100%)',
            foreground: 'hsl(222.2, 84%, 4.9%)',
            card: {
              DEFAULT: 'hsl(0, 0%, 100%)',
              foreground: 'hsl(222.2, 84%, 4.9%)',
            },
            muted: {
              DEFAULT: 'hsl(210, 40%, 96.1%)',
              foreground: 'hsl(215.4, 16.3%, 46.9%)',
            },
          },
        },
      },
    };
  </script>

  <!-- 引入 Inter 字體與基本 CSS -->
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
    
    html, body {
      font-family: 'Inter', sans-serif;
      /* 使用 Tailwind 的背景色 */
      background-color: theme('colors.background');
      color: theme('colors.foreground');
      line-height: 1.6;
    }
  </style>

  <!-- SEO 優化: JSON-LD 結構化資料，提升搜尋引擎對內容的理解 -->
  <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Article",
      "mainEntityOfPage": {
        "@type": "WebPage",
        "@id": "https://your-domain.com/ai-glossary"
      },
      "headline": "AI 名詞速通指南",
      "description": "本指南用簡潔的語言，解釋了生成式 AI 領域中的常見概念、技術細節、以及潛在的風險與機會。透過清晰的卡片式設計，助你快速建立對 AI 的共同語言。",
      "author": {
        "@type": "Person",
        "name": "Gemini AI"
      },
      "publisher": {
        "@type": "Organization",
        "name": "Your Company",
        "logo": {
          "@type": "ImageObject",
          "url": "https://your-domain.com/logo.png"
        }
      },
      "datePublished": "2024-05-20",
      "dateModified": "2024-05-20"
    }
  </script>
</head>
<body>
  <div id="root"></div>

  <script type="text/babel">
    const { Card, CardContent, CardHeader, CardTitle } = (() => {
      // 為了讓程式碼自給自足，將 shadcn/ui 的卡片元件直接定義在這裡
      // 實際專案中，這些元件會被 import 進來
      const Card = ({ className, children }) => (
        <div className={`rounded-lg border bg-card text-card-foreground shadow-sm ${className}`}>
          {children}
        </div>
      );
      const CardHeader = ({ className, children }) => (
        <div className={`flex flex-col space-y-1.5 p-6 ${className}`}>
          {children}
        </div>
      );
      const CardTitle = ({ className, children }) => (
        <h3 className={`text-2xl font-semibold leading-none tracking-tight ${className}`}>
          {children}
        </h3>
      );
      const CardContent = ({ className, children }) => (
        <div className={`p-6 pt-0 ${className}`}>
          {children}
        </div>
      );
      return { Card, CardContent, CardHeader, CardTitle };
    })();

    const sections = [
      {
        key: "common",
        title: "常見概念",
        color: "concept-common",
        items: [
          { term: "Gen AI", def: "生成式 AI。模型能根據資料樣本產生新內容（文字、圖片、程式碼等）。" },
          { term: "AIGC", def: "AI Generated Content。用 AI 自動化或輔助產生內容的一種生產方式。" },
          { term: "LLM", def: "Large Language Model。大型語言模型，具語言理解/生成與推理能力的通用模型。" },
          { term: "GPT", def: "Generative Pre-trained Transformer。OpenAI 系列 LLM 的架構與產品家族。" },
          { term: "OpenAI", def: "研發 GPT 等模型與工具的組織/公司，提供 API 與應用（ChatGPT）。" },
          { term: "GPU", def: "圖形處理器。擅長大規模並行運算，是訓練與推理的重要硬體。" },
        ],
      },
      {
        key: "tech",
        title: "技術概念",
        color: "concept-tech",
        items: [
          { term: "Vectorize", def: "向量化/嵌入。把文字、圖片轉為高維向量，便於相似度檢索。" },
          { term: "Pre-train", def: "預訓練。先在海量通用資料學習一般能力，形成基礎模型。" },
          { term: "Fine-tune", def: "微調。用專屬資料進一步訓練，使模型符合特定領域或風格。" },
          { term: "Prompt", def: "提示詞。給模型的指令/上下文，影響輸出品質與風格。" },
          { term: "RAG", def: "檢索增強生成。先檢索知識庫，再把結果餵給模型生成，降低遺漏與過時。" },
          { term: "Parameter Size", def: "參數量。模型容量與資源需求的指標，越大通常能力越強但成本越高。" },
        ],
      },
      {
        key: "opportunity",
        title: "風險與機會",
        color: "concept-opportunity",
        items: [
          { term: "Hallucination", def: "幻覺。模型自信地說錯或編造內容；以 RAG、校驗與限制可緩解。" },
          { term: "Prompt Injection", def: "提示注入。惡意指令誘導模型違背原任務或洩漏機密。需做輸入淨化與權限邊界。" },
          { term: "No code/Low code", def: "無/低程式。以配置、拖拉快速搭建 AI 應用，降低門檻。" },
          { term: "RPA", def: "機器流程自動化。以腳本/代理操控軟體，常與 LLM 結合做任務自動化。" },
          { term: "AI PC", def: "內建 NPU 的個人電腦，強化在地端 AI 推理與隱私。" },
          { term: "LLM OS", def: "以 LLM 為中樞的人機介面/代理層願景，聚合工具與上下文。" },
        ],
      },
    ];

    // 新增顏色對應物件，將 props 值與完整的 Tailwind 類別名稱對應
    const colorMap = {
      'concept-common': { bar: 'bg-concept-common', text: 'text-concept-common' },
      'concept-tech': { bar: 'bg-concept-tech', text: 'text-concept-tech' },
      'concept-opportunity': { bar: 'bg-concept-opportunity', text: 'text-concept-opportunity' },
    };

    const Section = ({ title, color, items }) => (
      <section className="w-full">
        <Card className="relative overflow-hidden border bg-card hover:shadow-xl transition-transform duration-300 will-change-transform hover:-translate-y-0.5">
          {/* 強調條，現在使用 colorMap 來取得完整的類別名稱 */}
          <div className={`h-1 w-full ${colorMap[color].bar}`}></div>
          <CardHeader>
            <CardTitle className="text-2xl">{title}</CardTitle>
          </CardHeader>
          <CardContent className="space-y-3">
            {items.map((i) => (
              <article key={i.term} className="rounded-lg border p-4 bg-background/60 transition-colors duration-200">
                {/* 標題顏色，同樣使用 colorMap 來取得完整的類別名稱 */}
                <h3 className={`text-base font-semibold ${colorMap[color].text}`}>{i.term}</h3>
                <p className="text-sm text-muted-foreground leading-relaxed">{i.def}</p>
              </article>
            ))}
          </CardContent>
        </Card>
      </section>
    );

    const App = () => {
      return (
        <div className="min-h-screen bg-background">
          <header className="container mx-auto py-12 px-6">
            <h1 className="text-4xl font-bold tracking-tight">AI 名詞速通指南</h1>
            <p className="mt-3 text-muted-foreground max-w-2xl">三色快讀：<span className="text-concept-common">紫</span>（常見）、<span className="text-concept-tech">藍</span>（技術）、<span className="text-concept-opportunity">綠</span>（風險與機會）。每個詞 1 句話，快速建立共同語言。</p>
          </header>
          <main className="container mx-auto grid gap-6 pb-16 px-6 md:grid-cols-2 lg:grid-cols-3">
            {sections.map((s) => (
              <Section key={s.key} title={s.title} color={s.color} items={s.items} />
            ))}
          </main>
          <footer className="container mx-auto pb-12 px-6 text-xs text-muted-foreground">
            建議學習路徑：先掌握常見→理解技術→評估風險與機會。
          </footer>
        </div>
      );
    };

    // 渲染 React 應用程式
    const root = ReactDOM.createRoot(document.getElementById('root'));
    root.render(<App />);
  </script>
</body>
</html>
