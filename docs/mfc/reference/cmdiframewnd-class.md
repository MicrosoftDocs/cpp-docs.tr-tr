---
title: CMDIFrameWnd sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
dev_langs:
- C++
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bb9f87ed5ae3027e7743a36c2484017d6381f95
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374045"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd sınıfı
Birden çok belge arabirimi (MDI) çerçeve penceresi, pencerenin yönetmek için üyeleri ile birlikte Windows işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|Oluşturan bir `CMDIFrameWnd`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](#createclient)|Bir Windows oluşturur **MDICLIENT** Bu pencere `CMDIFrameWnd`. Tarafından çağrılır `OnCreate` üye işlevini `CWnd`.|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|Yeni bir alt pencere oluşturur.|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|Pencere açılır menüsünü döndürür.|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|Farklı bir MDI alt penceresi etkinleştirir.|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|Tüm alt pencereleri basamaklı bir biçimde düzenler.|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|Alt ekranı olup olmadığını belirten bir bayrak yanı sıra şu anda etkin MDI alt penceresinde alır.|  
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|Tüm simge durumuna küçültülmüş belge alt pencereleri düzenler.|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI alt penceresinin en üst düzeye çıkarır.|  
|[CMDIFrameWnd::MDINext](#mdinext)|Alt pencere etkin alt pencere hemen arkasında etkinleştirir ve şu anda etkin alt pencere diğer tüm alt pencereleri yerleştirir.|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|Önceki alt pencere etkinleştirir ve şu anda etkin alt pencere hemen arkasında yerleştirir.|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI alt pencere ekranı kaplamış veya simge durumuna küçültülmüş boyutundan geri yükler.|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI çerçeve pencere menüsü, penceresi açılır menüsünden veya her ikisini yerini alır.|  
|[CMDIFrameWnd::MDITile](#mditile)|Tüm alt pencereleri döşeli biçimde düzenler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamanız için yararlı bir MDI çerçeve penceresi oluşturmak için öğesinden bir sınıf türetin `CMDIFrameWnd`. Üye değişkenleri, uygulamaya özgü verileri depolamak için türetilmiş bir sınıf ekleyin. Uygulama ileti işleyicisi üye işlevleri ve bir ileti iletileri penceresine yönlendirilirsiniz olduğunda ne olacağını belirlemek için türetilen sınıfta eşleyin.  
  
 MDI çerçeve penceresi çağırarak oluşturabileceğiniz [oluşturma](../../mfc/reference/cframewnd-class.md#create) veya [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) üye işlevini `CFrameWnd`.  
  
 Çağırmadan önce **oluşturma** veya `LoadFrame`, C++ kullanarak yığın çerçeve penceresi nesnesinde oluşturmalıdır **yeni** işleci. Çağırmadan önce **oluşturma** pencere sınıfı ile kayıt yaptırabilirsiniz [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) çerçeve simgesini ve sınıf stilleri ayarlamak için genel işlevi.  
  
 Kullanım **oluşturma** çerçeve oluşturma parametreleri olarak hemen bağımsız değişkenleri geçirmek için üye işlevi.  
  
 `LoadFrame` daha az sayıda bağımsız değişken gerektirir **oluşturma**ve bunun yerine varsayılan değerlerine çoğunu çerçeve resim yazısı simgesi, Hızlandırıcı tablosu ve menü çeşitli kaynaklardan alır. Tarafından erişilmek üzere `LoadFrame`, tüm bu kaynaklar aynı kaynak kimliği olmalıdır (örneğin, **IDR_MAINFRAME**).  
  
 Ancak **MDIFrameWnd** türetilir `CFrameWnd`, çerçeve pencere sınıfı türetilmiş `CMDIFrameWnd` ile bildirilmesi değil `DECLARE_DYNCREATE`.  
  
 `CMDIFrameWnd` Sınıfının devraldığı kendi varsayılan uygulamasından çoğunu `CFrameWnd`. Bu özelliklerin ayrıntılı bir listesi için bkz [CFrameWnd](../../mfc/reference/cframewnd-class.md) sınıf açıklaması. `CMDIFrameWnd` Sınıfı aşağıdaki ek özelliklere sahiptir:  
  
-   MDI çerçeve penceresi yönetir **MDICLIENT** denetim çubukları ile birlikte yeniden konumlandırma penceresi. MDI istemci MDI alt çerçeve pencereleri doğrudan üst penceredir. **WS_HSCROLL** ve **WS_VSCROLL** belirtilen pencere stilleri bir `CMDIFrameWnd` ana çerçeve penceresi yerine MDI istemcisi penceresinde geçerli kullanıcı (olduğu gibi Windows MDI istemci alanı kaydırabilirsiniz böylece Yöneticisi, örneğin program).  
  
-   MDI çerçeve penceresi etkin MDI alt pencere olduğunda menü çubuğu olarak kullanılan bir varsayılan menü sahip olur. Bir etkin MDI alt olduğunda MDI çerçeve pencere menü çubuğu MDI alt pencere menüsü tarafından otomatik olarak değiştirilir.  
  
-   Varsa bir MDI çerçeve penceresi geçerli MDI alt pencere birlikte çalışır. Örneğin, komut iletileri MDI çerçeve penceresi önce şu anda etkin MDI alt verilmiş.  
  
-   MDI çerçeve penceresi aşağıdaki standart pencere menü komutları için varsayılan işleyiciler sahiptir:  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   MDI çerçeve penceresi de uygulaması sahip **ıd_wındow_new**, yeni bir çerçeve ve geçerli belge görünümü oluşturur. Bir uygulama bu varsayılan komutu uygulamaları MDI pencere işleme özelleştirmek için geçersiz kılabilirsiniz.  
  
 C++ kullanmayın **silmek** işleci bir çerçeve penceresi yok. Bunun yerine `CWnd::DestroyWindow` kullanın. `CFrameWnd` Uyarlamasını `PostNcDestroy` pencere bozulduğunda C++ nesneyi siler. Kullanıcının varsayılan çerçeve penceresi kapattığı zaman `OnClose` işleyici çağıracaktır `DestroyWindow`.  
  
 Daha fazla bilgi için `CMDIFrameWnd`, bkz: [çerçeve pencereleri](../../mfc/frame-windows.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd  
 Oluşturan bir `CMDIFrameWnd` nesnesi.  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı **oluşturma** veya `LoadFrame` görünür MDI çerçeve penceresi oluşturmak için üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="createclient"></a>  CMDIFrameWnd::CreateClient  
 Yönetir MDI istemci pencere oluşturur `CMDIChildWnd` nesneleri.  
  
```  
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpCreateStruct`  
 Uzun bir işaretçi bir [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) yapısı.  
  
 `pWindowMenu`  
 Pencere açılır menü için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi, geçersiz kılarsanız çağrılmalıdır `OnCreate` doğrudan üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="createnewchild"></a>  CMDIFrameWnd::CreateNewChild  
 Yeni bir alt pencere oluşturur.  
  
```  
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,  
    UINT nResource,  
    HMENU hMenu = NULL,  
    HACCEL hAccel = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pClass`  
 Oluşturulacak alt pencere çalışma zamanı sınıfı.  
  
 *nResource*  
 Alt pencere ile ilişkilendirilmiş paylaşılan kaynakları kimliği.  
  
 `hMenu`  
 Alt pencere menüsü.  
  
 `hAccel`  
 Alt pencere Hızlandırıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows bir MDI çerçeve penceresinin alt oluşturmak için bu işlevi kullanın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 Bu örnekte Bilgi Bankası makalesi Q201045, yapılan bir alıntı, "nasıl yapılır: birden çok pencere türleri Non-belge/görünüm MDI uygulama ekleyin." Bilgi Bankası makaleleri kullanılabilir [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup  
 Bir tanıtıcı "Penceresinde" (açılır menü ile MDI pencere yönetimi için menü öğeleri) adlı geçerli açılır menü elde etmek için bu üye işlevini çağırın.  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>Parametreler  
 *hMenuBar*  
 Geçerli menü çubuğu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir pencere açılır menüsünü var; Aksi takdirde **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama gibi standart pencere menü komutları içeren bir açılır menü için görünür **ıd_wındow_new** ve **ıd_wındow_tıle_horz**.  
  
 Standart menü komut kimlikleri kullanmayan bir pencere menüsü varsa, bu üye işlevi geçersiz kılar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate  
 Farklı bir MDI alt penceresi etkinleştirir.  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWndActivate*  
 Etkinleştirilecek MDI alt pencere noktalarına.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi gönderir [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) etkinleştirilmekte olan alt pencere ve devre dışı bırakılan alt pencere ileti.  
  
 Kullanıcı odağı MDI alt penceresine klavye ve fare kullanarak değiştirirse, gönderilen iletinin budur.  
  
> [!NOTE]
>  MDI alt pencere MDI çerçeve penceresi bağımsız olarak etkinleştirilir. Çerçeve etkin olduğunda en son etkinleştirilmesinden alt pencere gönderilen bir [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) bir etkin pencere çerçevesi ve başlık çubuğu, ancak çizmek için ileti başka bir almaz `WM_MDIACTIVATE` ileti.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup).  
  
##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade  
 Cascade biçiminde tüm MDI alt pencereleri düzenler.  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>Parametreler  
 `nType`  
 Cascade bayrağı belirtir. Yalnızca aşağıdaki bayrağı belirtilebilir: `MDITILE_SKIPDISABLED`, engelleyen devre dışı MDI alt pencereleri basamaklı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürümü `MDICascade`, hiçbir parametrelerle devre dışı olanlar da dahil olmak üzere tüm MDI alt pencereleri basamaklı. İkinci sürümü belirtirseniz, isteğe bağlı olarak değil devre dışı MDI alt Pencereleri Basamakla mu `MDITILE_SKIPDISABLED` için `nType` parametresi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive  
 Geçerli etkin MDI alt pencerenin alt pencere ekranı olup olmadığını belirten bir bayrak birlikte alır.  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *pbMaximized*  
 Bir işaretçi bir **BOOL** dönüş değeri. Kümesine **TRUE** pencere ekranı kaplamış; Aksi takdirde ise dönüşte **FALSE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin MDI alt pencere için bir işaretçi.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdiiconarrange"></a>  CMDIFrameWnd::MDIIconArrange  
 Tüm simge durumuna küçültülmüş belge alt pencereleri düzenler.  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Değil en aza alt öğe pencerelerini etkilemez.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMDIFrameWnd::MDICascade](#mdicascade).  
  
##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize  
 Belirtilen MDI alt penceresinin en üst düzeye çıkarır.  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 En üst düzeye çıkarmak için penceresine noktaları.  
  
### <a name="remarks"></a>Açıklamalar  
 Alt pencere ekranı, Windows istemci pencereyi doldurmak kendi istemci alanını olmak için yeniden boyutlandırır. Kullanıcı geri yükleyin veya alt penceresini kapatmak için Windows alt pencere Denetim menüsü çerçeve menü çubuğunda yerleştirir. Ayrıca alt penceresinin başlık çerçeve penceresi başlık ekler.  
  
 Şu anda etkin MDI alt pencere ekranı zaman başka bir MDI alt pencere etkinleştirilmişse, Windows şu anda etkin alt geri yükler ve yeni etkinleştirilmiş alt pencere en üst düzeye çıkarır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).  
  
##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext  
 Alt pencere etkin alt pencere hemen arkasında etkinleştirir ve şu anda etkin alt pencere diğer tüm alt pencereleri yerleştirir.  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda etkin MDI alt pencere ekranı, üye işlevi şu anda etkin alt geri yükler ve yeni etkinleştirilmiş alt en üst düzeye çıkarır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev  
 Önceki alt pencere etkinleştirir ve şu anda etkin alt pencere hemen arkasında yerleştirir.  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda etkin MDI alt pencere ekranı, üye işlevi şu anda etkin alt geri yükler ve yeni etkinleştirilmiş alt en üst düzeye çıkarır.  
  
##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore  
 MDI alt pencere ekranı kaplamış veya simge durumuna küçültülmüş boyutundan geri yükler.  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Geri yüklemek için penceresine noktaları.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore).  
  
##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu  
 MDI çerçeve pencere menüsü, penceresi açılır menüsünden veya her ikisini yerini alır.  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>Parametreler  
 *pFrameMenu*  
 Yeni Çerçeve Pencere menüsü menü belirtir. Varsa **NULL**, menü değiştirilmedi.  
  
 `pWindowMenu`  
 Yeni pencere açılır menüsünü menü belirtir. Varsa **NULL**, menü değiştirilmedi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu ileti tarafından değiştirilen çerçeve pencere menüsü gösteren bir işaretçi. İşaretçinin geçici olabilir ve daha sonra kullanmak üzere depolanmadığından.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra `MDISetMenu`, bir uygulama çağırmalısınız [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) üye işlevini `CWnd` menü çubuğu güncelleştirmek için.  
  
 Bu çağrı penceresi açılır menü değiştirirse, MDI alt pencere menü öğeleri önceki Pencere menüsünden kaldırıldı ve yeni pencere açılır menüsünü eklendi.  
  
 MDI alt pencere ekranı ve bu çağrıyı MDI çerçeve pencere menüsü yerini alır, Denetim menü ve geri yükleme denetimleri önceki çerçeve Pencere menüsünden kaldırılır ve yeni menüsüne eklenen.  
  
 MDI alt pencereleri yönetmek için Framework'te kullanıyorsanız bu üye işlevini çağırmanız gerekmez.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>  CMDIFrameWnd::MDITile  
 Tüm alt pencereleri döşeli biçimde düzenler.  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>Parametreler  
 `nType`  
 Döşeme bayrağı belirtir. Bu parametre, aşağıdaki bayraklar herhangi biri olabilir:  
  
- `MDITILE_HORIZONTAL` Bu bir pencere başka görünmesi döşeme MDI alt pencereleri.  
  
- `MDITILE_SKIPDISABLED` Devre dışı MDI alt pencereleri döşenir gelen engeller.  
  
- `MDITILE_VERTICAL` Bu bir pencere başka görünmesi döşeme MDI alt pencereleri.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürümü `MDITile`, parametre olmadan windows Windows 3.1 ve sonraki sürümleri altında dikey olarak yerleştirir. İkinci sürümü windows dikey veya yatay olarak bağlı olarak değeri bölmeleri `nType` parametresi.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMDIFrameWnd::MDICascade](#mdicascade).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [MFC örnek MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC örnek SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd Sınıfı](../../mfc/reference/cmdichildwnd-class.md)
