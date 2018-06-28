---
title: CMiniFrameWnd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 766faaa50e4efead96ff72c67aee71fec2386b18
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038594"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd sınıfı
Kayan araç çubukları genellikle görülen yarım yükseklikte çerçeve penceresi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|Oluşturan bir `CMiniFrameWnd` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](#create)|Oluşturur bir `CMiniFrameWnd` yapım sonra nesnesi.|  
|[CMiniFrameWnd::CreateEx](#createex)|Oluşturur bir `CMiniFrameWnd` nesne (ek seçenekler) yapım sonra.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu kısa çerçeve pencereleri simge durumuna küçült/Ekranı Kapla düğmeleri yok veya menüleri ve yalnızca tek tıklamayla bunları kapatmak için sistem menüsünde zorunda dışında normal çerçeve pencereleri gibi davranır.  
  
 Kullanılacak bir `CMiniFrameWnd` nesne, nesne önce tanımlayın. ' I çağırın [oluşturma](#create) kısa çerçeve penceresini görüntülemek için üye işlevi.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CMiniFrameWnd` nesneleri başlıklı makaleye bakın [Docking ve kayan araç çubukları](../../mfc/docking-and-floating-toolbars.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd  
 Oluşturan bir `CMiniFrameWnd` nesnesi, ancak pencere oluşturmaz.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere oluşturmak için çağrı [CMiniFrameWnd::Create](#create).  
  
##  <a name="create"></a>  CMiniFrameWnd::Create  
 Windows mini çerçeve penceresi oluşturur ve ona ekler `CMiniFrameWnd` nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpClassName*  
 Windows sınıfı adları null olarak sonlandırılan bir karakter dizesine noktaları. Sınıf adı genel ile kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevi. Varsa **NULL**, pencere sınıfı sizin için çerçevesi tarafından kaydedilir. MFC varsayılan sınıfı aşağıdaki stillerini ve özniteliklerini sağlar:  
  
-   Ayarlar stili bit **CS_DBLCLKS**, kullanıcının fare tıklattığında hangi gönderir pencere yordamı iletileri çift tıklayın.  
  
-   Ayarlar stil BITS **CS_HREDRAW** ve **CS_VREDRAW**, pencere boyutu değiştiğinde çizilmesine istemci alanını içeriğini doğrudan.  
  
-   Windows standart sınıfı imleci ayarlar **IDC_ARROW**.  
  
-   Sınıf arka planı fırçasını ayarlar **NULL**, pencerenin, arka plan silecek değil.  
  
-   Sınıf simgesi için standart, Sallayan sürekli bayrağı Windows logo simgesini ayarlar.  
  
-   Pencere varsayılan boyutunu ve konumunu, Windows tarafından belirtildiği şekilde ayarlar.  
  
 *lpWindowName*  
 Pencere adı içeren bir null olarak sonlandırılan bir karakter dizesi noktalarına.  
  
 *dwStyle*  
 Pencere stili özniteliklerini belirtir. Bunlar, standart pencere stilleri ve bir veya daha fazla aşağıdaki özel stiller içerebilir:  
  
- **MFS_MOVEFRAME** pencere, yalnızca resim yazısı herhangi bir kenarına tıklayarak taşınacak kısa çerçeve pencere sağlar.  
  
- **MFS_4THICKFRAME** kısa çerçeve penceresi yeniden boyutlandırma devre dışı bırakır.  
  
- **MFS_SYNCACTIVE** kısa çerçeve penceresi kendi üst penceresi etkinleştirme için etkinleştirme eşitler.  
  
- **MFS_THICKFRAME** kısa çerçeve pencere istemci alanını içeriğini izin olarak küçük boyutlu olmasını sağlar.  
  
- **MFS_BLOCKSYSMENU** Sistem menüsünü ve Denetim menüsü erişimi devre dışı bırakır ve resim yazısı (başlık çubuğu) bir parçası için dönüştürür.  
  
 Bkz: [CWnd::Create](../../mfc/reference/cwnd-class.md#create) olası pencere stili değerleri açıklaması. Kısa çerçeve pencereleri için kullanılan normal bileşimi **WS_POPUP&#124;ws_captıon&#124;WS_SYSMENU**.  
  
 *Rect*  
 A `RECT` yapısı pencerenin istenen boyutlarını belirleme.  
  
 *pParentWnd*  
 Üst pencere noktalarına. Kullanım **NULL** en üst düzey windows için.  
  
 *nID*  
 Alt pencere olarak kısa çerçeve penceresi oluşturduysanız, bu alt denetiminin tanımlayıcısıdır; Aksi takdirde 0.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 **Oluşturma** pencere sınıfı adı ve pencere adı başlatır ve stil ve üst varsayılan değerleri kaydeder.  
  
##  <a name="createex"></a>  CMiniFrameWnd::CreateEx  
 Oluşturur bir `CMiniFrameWnd` nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwExStyle*  
 Genişletilmiş stilini belirtir `CMiniFrameWnd` oluşturuluyor. Herhangi biri geçerli [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) penceresine.  
  
 *lpClassName*  
 İşaret Windows sınıfı adları bir null olarak sonlandırılan bir karakter dizesi (bir [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı). Sınıf adı genel ile kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) işlevi veya önceden tanımlanmış control sınıfı adlarının herhangi biri. Değil olmalıdır **NULL**.  
  
 *lpWindowName*  
 Pencere adı içeren bir null olarak sonlandırılan bir karakter dizesi noktalarına.  
  
 *dwStyle*  
 Pencere stili özniteliklerini belirtir. Bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) ve [CWnd::Create](../../mfc/reference/cwnd-class.md#create) olası değerler açıklaması.  
  
 *Rect*  
 İstemci koordinatları penceresi konumu ve boyutu *pParentWnd*.  
  
 *pParentWnd*  
 Üst pencere nesnesi noktalarına.  
  
 *nID*  
 Alt pencere tanımlayıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 `CreateEx` Parametrelerini belirtin **WNDCLASS**, pencere stili ve (isteğe bağlı) ilk konum ve pencere boyutunu. `CreateEx` Ayrıca pencerenin üst (varsa) ve kimliği belirtir  
  
 Zaman `CreateEx` yürütür, Windows gönderir [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), ve [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) pencere iletileri.  
  
 Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CMiniFrameWnd`, ileti eşlemesi için yeni sınıf ekleyin ve yukarıdaki iletiler için üye işlevleri sağlar. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Daha fazla geçersiz kılma **üzerinde *** ileti* ileti işleyicileri daha fazla işlevsellik türetilmiş sınıfınıza ekleyin.  
  
 Varsa **ws_vısıble** stili verilen, Windows penceresi etkinleştirmek ve pencere göstermek için gerekli tüm iletileri gönderir. Pencere stili bir başlık çubuğu belirtiyorsa, pencere başlığı işaret için tarafından *lpszWindowName* parametresi başlık çubuğunda görüntülenir.  
  
 *DwStyle* parametresi, herhangi bir bileşimi olabilir [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 Eski stil palet araç windows artık desteklenmemektedir. Bir "X" Kapat düğmesini sahip değil, eski stil MFC uygulaması önceki Windows sürümlerinde çalıştırırken desteklenen ancak Visual C++ .NET içinde artık desteklenmiyor. Yalnızca yeni `WS_EX_TOOLWINDOW` stili şimdi desteklenir; bu stili açıklaması için bkz: [genişletilmiş pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)
