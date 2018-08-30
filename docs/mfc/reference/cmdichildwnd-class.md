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
ms.openlocfilehash: 4d31392a59707e5a7d072615ed7c930eaf1e14b9
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207634"
---
# <a name="cmdichildwnd-class"></a>Cmdıchildwnd sınıfı
Bir Windows işlevlerini birden çok Belgeli Arabirim (MDI) alt penceresi ve pencereyi yönetmek için üyeleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|Oluşturur bir `CMDIChildWnd` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|İle ilişkili Windows MDI alt penceresi yaratır `CMDIChildWnd` nesne.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|Üst MDI MSI istemci penceresi karesini döndürür.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|Bu MDI alt penceresini etkinleştirir.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|Bu MDI alt penceresini yok eder.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|Bu MDI alt penceresinin en üst düzeye çıkarır.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|Bu MDI alt penceresi simge durumuna küçültülmüş ya da tam ekran boyutunu geri yükler.|  
|[CMDIChildWnd::SetHandles](#sethandles)|Menü ve Hızlandırıcı kaynakları için tutamaçları ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir MDI çerçeve penceresinin içinde yerine masaüstünde MDI alt penceresi görünür dışında bir MDI alt penceresi tipik bir çerçeve penceresi gibi görünüyor. MDI alt penceresine bir menü çubuğu kendi yok, ancak bunun yerine MDI çerçeve penceresinin menü paylaşır. Framework, şu anda etkin MDI alt penceresini temsil eden MDI çerçeve menüsü otomatik olarak değiştirir.  
  
 Uygulamanız için kullanışlı bir MDI alt penceresi oluşturmak için öğesinden bir sınıf türetin `CMDIChildWnd`. Uygulamanıza özgü verileri depolamak için türetilmiş sınıf üye değişkenlerini ekleyin. Türetilen bir sınıfta iletileri penceresine yönlendirilirsiniz olduğunda ne olacağını belirlemek için uygulama ileti işleyicisi üye işlevleri ve bir ileti eşleyin.  
  
 Bir MDI alt penceresi oluşturmak için üç yolu vardır:  
  
-   Doğrudan kullanarak oluşturmak `Create`.  
  
-   Doğrudan kullanarak oluşturmak `LoadFrame`.  
  
-   Dolaylı olarak bir belge şablonu aracılığıyla oluşturun.  
  
 Çağırmadan önce `Create` veya `LoadFrame`, C++ kullanarak yığın çerçeve pencere nesnesinde oluşturmalıdır **yeni** işleci. Çağırmadan önce `Create` pencere sınıfı ile de kaydedebilirsiniz [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) simgesi ve sınıf stilleri çerçevesi için ayarlanacak genel işlev.  
  
 Kullanım `Create` çerçeve oluşturma parametreleri olarak anında bağımsız değişkenleri geçirmek için üye işlevi.  
  
 `LoadFrame` daha az sayıda bağımsız değişken gerektirir `Create`ve bunun yerine varsayılan değerlerine çoğunu çerçevenin başlık, simgesi, Hızlandırıcı tablosu ve menü gibi kaynaklardan alır. Tarafından erişilebilir olmasını `LoadFrame`, tüm bu kaynaklar aynı kaynak kimliği (örneğin, IDR_MAINFRAME) olması gerekir.  
  
 Olduğunda bir `CMDIChildWnd` nesne, görünümleri ve belgeleri içerir, bunlar yerine doğrudan programcısı tarafından framework tarafından dolaylı olarak oluşturulur. `CDocTemplate` Çerçeve oluşturulmasını, içeren görünümler oluşturma ve uygun belge görünümleri bağlantı nesnesi düzenler. Parametreleri `CDocTemplate` Oluşturucusu belirtin `CRuntimeClass` üç sınıflarını dahil (belge, çerçeve ve Görünüm). A `CRuntimeClass` nesnesi (örneğin, dosya yeni komutunun veya MDI pencere yeni komutunu kullanarak) kullanıcı tarafından belirtilen yeni çerçeve dinamik olarak oluşturmak için framework tarafından kullanılır.  
  
 Öğesinden türetilen bir çerçeve pencere sınıf `CMDIChildWnd` DECLARE_DYNCREATE ile düzgün çalışması yukarıdaki RUNTIME_CLASS mekanizması için sırada bildirilmesi gerekir.  
  
 `CMDIChildWnd` Sınıfından devralan varsayılan uygulanması çoğunu `CFrameWnd`. Bu özelliklerin ayrıntılı listesi için bkz [CFrameWnd](../../mfc/reference/cframewnd-class.md) açıklaması sınıfı. `CMDIChildWnd` Sınıfı aşağıdaki ek özelliklere sahiptir:  
  
-   İle birlikte `CMultiDocTemplate` sınıfı, birden çok `CMDIChildWnd` aynı belge şablondaki nesneleri Windows sistem kaynağı kaydedilirken, aynı menü paylaşır.  
  
-   Etkin MDI alt penceresi menüsü MDI çerçeve penceresinin menü tamamen değiştirir ve şu anda etkin MDI alt penceresinin başlık MDI çerçeve penceresinin resim yazısı eklenir. Daha fazla örnekleri bir MDI çerçeve penceresinin birlikte uygulanan MDI alt penceresi işlevlerini için bkz: `CMDIFrameWnd` açıklaması sınıfı.  
  
 C++ kullanmayın **Sil** çerçeve penceresini yok etmek için işleci. Bunun yerine `CWnd::DestroyWindow` kullanın. `CFrameWnd` Uygulaması `PostNcDestroy` penceresi kaldırıldığında C++ nesnesi siler. Kullanıcının varsayılan çerçeve penceresi kapattığı zaman `OnClose` işleyici çağırır `DestroyWindow`.  
  
 Daha fazla bilgi için `CMDIChildWnd`, bkz: [çerçeve Windows](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd  
 Çağrı oluşturmak için bir `CMDIChildWnd` nesne.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `Create` görünür pencere oluşturmak için.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CMDIChildWnd::Create](#create).  
  
##  <a name="create"></a>  CMDIChildWnd::Create  
 Bir Windows MDI alt penceresi oluştur ve buna eklemek için bu üye işlevini çağırın `CMDIChildWnd` nesne.  
  
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
 Windows sınıf adları null ile sonlandırılmış dizeye işaret (bir [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı). Sınıf adı ile kayıtlı herhangi bir ad olabilir [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) genel işlev. Standart için NULL olmalıdır `CMDIChildWnd`.  
  
 *lpszWindowName*  
 Pencere adının temsil eden bir boş sonlandırılmış karakter dizesi işaret eder. Başlık çubuğunu metin olarak kullanılır.  
  
 *dwStyle*  
 Pencerenin belirtir [stili](../../mfc/reference/styles-used-by-mfc.md#window-styles) öznitelikleri. WS_CHILD stili gereklidir.  
  
 *Rect*  
 Pencerenin konumunu ve boyutunu içerir. `rectDefault` Değer sağlayan yeni konumunu ve boyutunu belirtmek Windows `CMDIChildWnd`.  
  
 *pParentWnd*  
 Pencerenin üst belirtir. NULL ise, ana uygulama penceresini kullanılır.  
  
 *pContext*  
 Belirtir bir [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) yapısı. Bu parametre NULL olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Etkin MDI alt çerçeve penceresi ana çerçeve penceresinin başlığını belirleyebilirsiniz. Bu özellik, alt çerçeve penceresi fws_addtotıtle stili bit devre dışı bırakarak devre dışı bırakıldı.  
  
 Framework alt pencere oluşturmak için bir kullanıcı komutuna yanıt olarak bu üye işlevini çağırır ve framework kullanan *pContext* alt pencerenin uygulamayı düzgün bir şekilde bağlanmak için parametre. Çağırdığınızda `Create`, *pContext* NULL olabilir.  
  
### <a name="example"></a>Örnek  
 Örnek 1:  
  
 [!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>Örnek  
 Örnek 2:  
  
 [!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame  
 MDI ana çerçeve döndürmek için bu işlevi çağırın.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 MDI ana çerçeve penceresine bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen kaldırıldığında iki ana karedir `CMDIChildWnd` ve üst tür yöneten MDICLIENT penceresi `CMDIChildWnd` nesne. Çağrı [GetParent](../../mfc/reference/cwnd-class.md#getparent) döndürülecek üye işlevi `CMDIChildWnd` nesnenin hemen MDICLIENT üst geçici olarak `CWnd` işaretçi.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).  
  
##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate  
 Bir MDI alt penceresi MDI çerçeve penceresinin bağımsız olarak etkinleştirmek için bu üye işlevini çağırın.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve etkin olduğunda, son etkinleştirildiği alt penceresi de etkinleştirilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).  
  
##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy  
 Bir MDI alt penceresini yok etmek için bu üye işlevini çağırın.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi çerçeve penceresinde alt pencerenin başlığı kaldırır ve alt penceresi devre dışı bırakır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize  
 Bir MDI alt penceresinin en üst düzeye çıkarmak için bu üye işlevini çağırın.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Windows, istemci alanını çerçeve penceresinin istemci alanını doldurmak için bir alt penceresi büyütüldüğünde göre yeniden boyutlandırır. Windows kullanıcı geri yükleyin veya alt pencereyi kapatın, bu alt pencerenin denetim menüsünden çerçeve menü çubuğundaki yerleştirir ve alt pencerenin başlığı çerçeve pencere başlığı ekler.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore  
 Bir MDI alt penceresi simge durumuna küçültülmüş ya da tam ekran boyutunu geri yüklemek için bu üye işlevini çağırın.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles  
 Menü ve Hızlandırıcı kaynakları için tutamaçları ayarlar.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>Parametreler  
 *hMenu*  
 Bir menü kaynağı tanıtıcısı.  
  
 *hAccel*  
 Bir Hızlandırıcı kaynak tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 MDI alt penceresi nesne tarafından kullanılan menüsü ve Hızlandırıcı kaynakları ayarlamak için bu işlevi çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [MFC örnek MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd Sınıfı](../../mfc/reference/cmdiframewnd-class.md)
