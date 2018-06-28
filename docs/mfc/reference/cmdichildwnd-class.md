---
title: Cmdıchildwnd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 037a6091f11ad12a8f4e46ccb837c48f1f9a685b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040853"
---
# <a name="cmdichildwnd-class"></a>Cmdıchildwnd sınıfı
Birden çok belge arabirimi (MDI) alt pencere, pencerenin yönetmek için üyeleri ile birlikte Windows işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Oluşturan bir `CMDIChildWnd` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|İle ilişkili Windows MDI alt pencere oluşturur `CMDIChildWnd` nesnesi.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|MDI çerçevesi MDI istemci penceresinin üst öğesini döndürür.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Bu MDI alt pencere etkinleştirir.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Bu MDI alt pencere yok eder.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Bu MDI alt penceresinin en üst düzeye çıkarır.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|Bu MDI alt pencere ekranı kaplamış veya simge durumuna küçültülmüş boyutundan geri yükler.|  
|[CMDIChildWnd::SetHandles](#sethandles)|Menü ve Hızlandırıcı kaynaklarını tanıtıcıları ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 MDI çerçeve penceresi içinde yerine masaüstünde MDI alt pencere görünür ancak bu bir MDI alt pencere tipik çerçeve penceresi benzer görünür. MDI alt pencere menü çubuğu kendi sahip değil, ancak bunun yerine MDI çerçeve penceresi menü paylaşır. Framework şu anda etkin MDI alt pencere temsil etmek için MDI çerçeve menüsü otomatik olarak değiştirir.  
  
 Uygulamanız için yararlı bir MDI alt pencere oluşturmak için öğesinden bir sınıf türetin `CMDIChildWnd`. Üye değişkenleri, uygulamaya özgü verileri depolamak için türetilmiş bir sınıf ekleyin. Uygulama ileti işleyicisi üye işlevleri ve bir ileti iletileri penceresine yönlendirilirsiniz olduğunda ne olacağını belirlemek için türetilen sınıfta eşleyin.  
  
 MDI alt pencere oluşturmak için üç yolu vardır:  
  
-   Doğrudan kullanarak oluşturmak `Create`.  
  
-   Doğrudan kullanarak oluşturmak `LoadFrame`.  
  
-   Dolaylı bir belge şablonu aracılığıyla oluşturun.  
  
 Çağırmadan önce `Create` veya `LoadFrame`, C++ kullanarak yığın çerçeve penceresi nesnesinde oluşturmalıdır **yeni** işleci. Çağırmadan önce `Create` pencere sınıfı ile kayıt yaptırabilirsiniz [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) çerçeve simgesini ve sınıf stilleri ayarlamak için genel işlevi.  
  
 Kullanım `Create` çerçeve oluşturma parametreleri olarak hemen bağımsız değişkenleri geçirmek için üye işlevi.  
  
 `LoadFrame` daha az sayıda bağımsız değişken gerektirir `Create`ve bunun yerine varsayılan değerlerine çoğunu çerçeve resim yazısı simgesi, Hızlandırıcı tablosu ve menü çeşitli kaynaklardan alır. Tarafından erişilebilir olmasını `LoadFrame`, tüm bu kaynaklar aynı kaynak kimliği olmalıdır (örneğin, **IDR_MAINFRAME**).  
  
 Zaman bir `CMDIChildWnd` nesnesini içeren görünümleri ve belgeleri, çerçevesiyle yerine doğrudan Programcı tarafından dolaylı olarak oluşturma. `CDocTemplate` Çerçeve oluşturulmasını, içeren görünümler oluşturma ve uygun belge görünümlerine bağlantı nesnesi düzenler. Parametreleri `CDocTemplate` Oluşturucusu belirtin `CRuntimeClass` üç sınıflarını söz konusu (belge, çerçeve ve Görünüm). A `CRuntimeClass` nesnesi çerçevesi tarafından dinamik olarak (örneğin, dosya yeni veya MDI pencere yeni komutunu kullanarak) kullanıcı tarafından belirtilen zaman yeni çerçeve oluşturmak için kullanılır.  
  
 Çerçeve pencere sınıfı türetilmiş `CMDIChildWnd` ile bildirilmelidir `DECLARE_DYNCREATE` yukarıdaki için sırada `RUNTIME_CLASS` düzgün çalışması için bir mekanizma.  
  
 `CMDIChildWnd` Sınıfının devraldığı kendi varsayılan uygulamasından çoğunu `CFrameWnd`. Bu özelliklerin ayrıntılı bir listesi için lütfen bakın [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıf açıklaması. `CMDIChildWnd` Sınıfı aşağıdaki ek özelliklere sahiptir:  
  
-   İle birlikte `CMultiDocTemplate` sınıfı, birden çok `CMDIChildWnd` nesneleri aynı belge şablondan Windows sistem kaynağı kaydetme menüsünün aynı paylaşır.  
  
-   Şu anda etkin MDI alt pencere menüsü tamamen MDI çerçeve pencere menüsü yerini alır ve şu anda etkin MDI alt pencere resim yazısını MDI çerçeve penceresinin başlık eklenir. Daha fazla MDI çerçeve penceresi ile birlikte uygulanan MDI alt pencere işlevleri örnekleri için bkz: `CMDIFrameWnd` sınıf açıklaması.  
  
 C++ kullanmayın **silmek** işleci bir çerçeve penceresi yok. Bunun yerine `CWnd::DestroyWindow` kullanın. `CFrameWnd` Uyarlamasını `PostNcDestroy` pencere bozulduğunda C++ nesneyi siler. Kullanıcının varsayılan çerçeve penceresi kapattığı zaman `OnClose` işleyici çağıracaktır `DestroyWindow`.  
  
 Daha fazla bilgi için `CMDIChildWnd`, bkz: [çerçeve pencereleri](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd  
 Çağrı oluşturmak için bir `CMDIChildWnd` nesnesi.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı **oluşturma** görünür penceresi oluşturulamadı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMDIChildWnd::Create](#create).  
  
##  <a name="create"></a>  CMDIChildWnd::Create  
 Windows MDI alt pencere oluşturmak ve ona eklemek için bu üye işlevini çağırın `CMDIChildWnd` nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CMDIFrameWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszClassName*  
 İşaret Windows sınıfı adları bir null olarak sonlandırılan bir karakter dizesi (bir [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı). Sınıf adı kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlevi. Olmalıdır **NULL** bir standart `CMDIChildWnd`.  
  
 *lpszWindowName*  
 Pencere adı temsil eden bir null olarak sonlandırılan bir karakter dizesi noktalarına. Başlık çubuğunu metin olarak kullanılır.  
  
 *dwStyle*  
 Pencerenin belirtir [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri. **WS_CHILD** stili gereklidir.  
  
 *Rect*  
 Boyutunu ve pencere konumunu içerir. `rectDefault` Değeri verir boyutu ve yeni konumunu belirtmek Windows `CMDIChildWnd`.  
  
 *pParentWnd*  
 Pencerenin üst belirtir. Varsa **NULL**, ana uygulama penceresi kullanılır.  
  
 *pContext*  
 Belirten bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Bu parametre olabilir **NULL**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda etkin MDI alt çerçeve penceresi üst çerçeve penceresi resim yazısını belirleyebilirsiniz. Bu özellik kapatma tarafından devre dışı **fws_addtotıtle** stili bit alt çerçeve penceresi.  
  
 Alt pencere oluşturmak için bir kullanıcı komutuna yanıt olarak framework bu üye işlevi çağırır ve çerçevesi kullanır *pContext* düzgün alt pencere uygulamaya bağlanmak için parametre. Çağırdığınızda `Create`, *pContext* olabilir **NULL**.  
  
### <a name="example"></a>Örnek  
 Örnek 1:  
  
 [!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>Örnek  
 Örnek 2:  
  
 [!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame  
 MDI üst çerçevesi döndürmek için bu işlevini çağırın.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 MDI üst çerçeve penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen kaldırılmasını iki üst dilimidir `CMDIChildWnd` ve üst tür penceresinin **MDICLIENT** , yöneten `CMDIChildWnd` nesnesi. Çağrı [GetParent](../../mfc/reference/cwnd-class.md#getparent) dönmek için üye işlevi `CMDIChildWnd` nesne hemen **MDICLIENT** üst geçici olarak `CWnd` işaretçi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).  
  
##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate  
 MDI alt penceresine MDI çerçeve penceresi bağımsız olarak etkinleştirmek için bu üye işlevini çağırın.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve etkin olduğunda en son etkinleştirilmesinden alt pencere de etkinleştirilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).  
  
##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy  
 MDI alt pencere yok etmek için bu üye işlevini çağırın.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi alt penceresinin başlık çerçeve penceresinden kaldırır ve alt pencere devre dışı bırakır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize  
 MDI alt penceresinin en üst düzeye çıkarmak için bu üye işlevini çağırın.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Alt pencere ekranı, Windows çerçeve penceresi istemci alanını doldurma kendi istemci alanını olmak için yeniden boyutlandırır. Windows kullanıcı geri yükleyin veya alt pencereyi kapatın, bu alt pencere Denetim menüsü çerçeve menü çubuğunda yerleştirir ve çerçeve penceresi başlığı alt penceresinin başlık ekler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore  
 MDI alt pencere ekranı kaplamış veya simge durumuna küçültülmüş boyutundan geri yüklemek için bu üye işlevini çağırın.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles  
 Menü ve Hızlandırıcı kaynaklarını tanıtıcıları ayarlar.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>Parametreler  
 *hMenu*  
 Menü kaynak tanıtıcısı.  
  
 *hAccel*  
 Hızlandırıcı kaynak tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 MDI alt pencere nesnesi tarafından kullanılan menü ve Hızlandırıcı kaynakları ayarlamak için bu işlevini çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [MFC örnek MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Sınıfı](../../mfc/reference/cmdiframewnd-class.md)
