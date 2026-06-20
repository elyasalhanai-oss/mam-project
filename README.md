# mam-project
موقع نظام MAM التجاري بالذكاء الاصطناعي
<!doctype html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>MAM — AI Commerce OS</title>
<script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<style>
  html,body{margin:0;padding:0;background:#07111F;color:#fff;font-family:system-ui,sans-serif;-webkit-user-select:none;user-select:none;}
  #root{min-height:100vh;}
  .btn-tap{transition:transform 0.1s; cursor:pointer; flex:1; padding:16px 0; textAlign:center; font-weight:bold;}
  .btn-tap:active{transform:scale(0.95);}
  .card {background:#0D1B2E; padding:15px; borderRadius:12px; border:1px solid rgba(255,255,255,0.06); marginBottom:15px;}
</style>
</head>
<body>
<div id="root"></div>
<script type="text/babel">
const { useState } = React;

function App() {
  const [portal, setPortal] = useState('customer');
  return (
    <div style={{ background: '#07111F', minHeight: '100vh', color: '#fff', pb: '80px' }}>
      {/* الشريط العلوي */}
      <div style={{ padding: '15px 20px', borderBottom: '1px solid rgba(255,255,255,0.06)', background: '#0D1B2E', textAlign: 'center', fontWeight: '900' }}>
        MAM — AI COMMERCE OS
      </div>
      
      {/* محتوى البوابات */}
      <div style={{ padding: '20px' }}>
        {portal === 'customer' && (
          <div>
            <h2 style={{ color: '#00C896' }}>🛍️ بوابة العميل الذكية</h2>
            <div className="card">
              <h4>🤖 مساعد التسوق الذكي</h4>
              <p style={{ color: '#8F9CAE', fontSize: 13 }}>يبحث ويقارن الأسعار تلقائياً بين المتاجر ليعثر على أفضل العروض المناسبة لميزانيتك.</p>
            </div>
          </div>
        )}

        {portal === 'merchant' && (
          <div>
            <h2 style={{ color: '#1A6FFF' }}>🏪 بوابة التاجر الذكية</h2>
            <div className="card">
              <h4>📊 نظام المزاد العكسي والفوترة</h4>
              <p style={{ color: '#8F9CAE', fontSize: 13 }}>يتيح لك تقديم عروض أسعار حية ومباشرة للمتسوقين وإصدار الفواتير تلقائياً.</p>
            </div>
          </div>
        )}

        {portal === 'advertiser' && (
          <div>
            <h2 style={{ color: '#A855F7' }}>📢 بوابة المعلن والـ RTB</h2>
            <div className="card">
              <h4>📈 نظام المزايدة اللحظية</h4>
              <p style={{ color: '#8F9CAE', fontSize: 13 }}>استهدف مساحات إعلانية مخصصة داخل فواتير الشراء واعرض إعلاناتك بدقة عالية وفي الوقت الحقيقي.</p>
            </div>
          </div>
        )}
      </div>

      {/* شريط التنقل السفلي الثابت */}
      <div style={{ position: 'fixed', bottom: 0, left: 0, right: 0, background: '#0D1B2E', borderTop: '1px solid rgba(255,255,255,0.06)', display: 'flex', zIndex: 999 }}>
        <div onClick={() => setPortal('customer')} className="btn-tap" style={{ color: portal === 'customer' ? '#00C896' : '#8F9CAE' }}>🛍️ العميل</div>
        <div onClick={() => setPortal('merchant')} className="btn-tap" style={{ color: portal === 'merchant' ? '#1A6FFF' : '#8F9CAE' }}>🏪 التاجر</div>
        <div onClick={() => setPortal('advertiser')} className="btn-tap" style={{ color: portal === 'advertiser' ? '#A855F7' : '#8F9CAE' }}>📢 المعلن</div>
      </div>
    </div>
  );
}

ReactDOM.createRoot(document.getElementById('root')).render(<App />);
</script>
</body>
</html>
