---
title: "CContainedWindowT sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
dev_langs: C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cf792fed2f7a5cac45826649224a565228f9d73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT sınıfı
Bu sınıf, başka bir nesne içinde bulunan bir pencere uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Parametreler  
 *TBase*  
 Yeni sınıfın temel sınıf. Varsayılan taban sınıf `CWindow`.  
  
 `TWinTraits`  
 Pencerenizi için stiller tanımlar nitelikler sınıfı. Varsayılan, `CControlWinTraits` değeridir.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) bir uzmanlığı olan `CContainedWindowT`. Taban sınıfı veya özellikleri değiştirmek istiyorsanız, kullanmak `CContainedWindowT` doğrudan.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Oluşturucu. Veri üyeleri hangi ileti eşlemesi içerdiği pencere iletileri işleyecek belirtmek için başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|Bir pencere oluşturur.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Geçerli iletisi döndürür.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Kapsanan penceresinin pencere sınıfı kaydeder.|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Alt sınıfların bir pencere.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Hangi ileti eşlemesi içerdiği pencere iletileri işlemek için kullanılan değiştirir.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Daha önce altsınıflanmış bir pencere getirir.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Statik) Kapsanan pencereye gönderilen iletileri işler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Hangi ileti eşlemesi içerdiği pencere iletileri işleyecek tanımlar.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Yeni bir pencere sınıfı dayanacak varolan bir pencere sınıfı adını belirtir.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfının özgün pencere yordamı noktalarına.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Noktaları içeren nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CContainedWindowT`başka bir nesne içinde bulunan bir pencere uygular. `CContainedWindowT`kullanıcının bir ileti eşleme uygun işleyicileri doğrudan iletileri içeren nesnesindeki pencere yordamı kullanır. Oluşturulurken bir `CContainedWindowT` nesnesi, belirttiğiniz hangi ileti eşlemesi kullanılmalıdır.  
  
 `CContainedWindowT`Yeni bir pencere varolan bir pencere sınıfı tarafından üst Sınıflama oluşturmanıza olanak sağlar. **Oluşturma** yöntemi önce varolan bir sınıfa bağlı, ancak kullanan bir pencere sınıfı kaydeder `CContainedWindowT::WindowProc`. **Oluşturma** bu yeni pencere sınıfına dayalı bir pencere oluşturur. Her bir örneğini `CContainedWindowT` sınıfın farklı pencere sınıfı olabilir.  
  
 `CContainedWindowT`Ayrıca penceresi sınıflara destekler. `SubclassWindow` Yöntemi iliştirir varolan penceresine `CContainedWindowT` nesne ve pencere yordamı değişiklikleri `CContainedWindowT::WindowProc`. Her örneği `CContainedWindowT` farklı bir pencere bir alt kümesi olabilir.  
  
> [!NOTE]
>  Verilen herhangi için `CContainedWindowT` nesne, ya da çağrısı **oluşturma** veya `SubclassWindow`. Her iki yöntem aynı nesne üzerinde çağıracağı değil.  
  
 Kullandığınızda **göre Denetimi Ekle** seçeneği ATL Proje Sihirbazı'nda Sihirbazı otomatik olarak ekleyecek bir `CContainedWindowT` denetimi uygulama sınıfı veri üyesi. Aşağıdaki örnek, içerdiği pencere nasıl bildirilmiş gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Daha fazla bilgi|Bkz. |  
|--------------------------------|---------|  
|Denetimler oluşturma|[ATL öğretici](../../atl/active-template-library-atl-tutorial.md)|  
|ATL Windows'da kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|  
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595) ve sonraki konularda Windows SDK'sı|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 Veri üyeleri Oluşturucu başlatır.  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>Parametreler  
 `lpszClassName`  
 [in] Kapsanan penceresi dayanacak varolan bir pencere sınıfı adı.  
  
 `pObject`  
 [in] İleti eşlemesi bildirir içeren nesne için bir işaretçi. Bu nesnenin sınıf öğesinden türetilmelidir [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Kapsanan pencere iletileri işleyecek ileti eşlemesi tanımlar. Varsayılan değer, 0, varsayılan ileti eşlemesi ile bildirilen belirtir [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Bir alternatif ileti eşlemesi kullanmak için bildirilen ile [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçirmek `msgMapID`.  
  
### <a name="remarks"></a>Açıklamalar  
 Aracılığıyla yeni bir pencere oluşturmak istiyorsanız [oluşturma](#create), varolan bir pencere sınıfı için adını geçmelidir `lpszClassName` parametresi. Bir örnek için bkz: [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) genel bakış.  
  
 Üç oluşturucular vardır:  
  
-   Üç bağımsız değişken Oluşturucu genellikle adlı adrestir.  
  
-   İki bağımsız değişken Oluşturucu sınıfı adından kullanan **TBase::GetWndClassName**.  
  
-   Daha sonra bağımsız değişkenleri eklemek istiyorsanız, bağımsız değişken içermeyen Oluşturucusu kullanılır. Daha sonra çağırdığınızda pencere sınıf adı, ileti eşleme nesnesi ve ileti eşleme kimliği sağlamalısınız **oluşturma**.  
  
 Varsa, varolan bir pencereyi alt sınıf aracılığıyla [SubclassWindow](#subclasswindow), `lpszClassName` değeri kullanılmaz; bu nedenle, geçirebilirsiniz **NULL** Bu parametre için.  
  
##  <a name="create"></a>CContainedWindowT::Create  
 Çağrıları [RegisterWndSuperclass](#registerwndsuperclass) varolan bir sınıfa bağlı, ancak kullanan bir pencere sınıfı kaydetmek için [CContainedWindowT::WindowProc](#windowproc).  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszClassName`  
 [in] Kapsanan penceresi dayanacak varolan bir pencere sınıfı adı.  
  
 `pObject`  
 [in] İleti eşlemesi bildirir içeren nesne için bir işaretçi. Bu nesnenin sınıf öğesinden türetilmelidir [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Kapsanan pencere iletileri işleyecek ileti eşlemesi tanımlar. Varsayılan değer, 0, varsayılan ileti eşlemesi ile bildirilen belirtir [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Bir alternatif ileti eşlemesi kullanmak için bildirilen ile [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçirmek `msgMapID`.  
  
 `hWndParent`  
 [in] Üst veya sahibi penceresine işleci.  
  
 `rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı penceresinin konumunu belirtme. `RECT` Veya başvuruya göre işaretçi geçirilebilir.  
  
 `szWindowName`  
 [in] Pencerenin adını belirtir. Varsayılan değer **NULL**.  
  
 `dwStyle`  
 [in] Pencere stili. Varsayılan değer **WS_CHILD &#124; Ws_vısıble**. Olası değerler listesi için bkz: [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK'sındaki.  
  
 `dwExStyle`  
 [in] Genişletilmiş pencere stili. Varsayılan değer yok genişletilmiş stili yani 0 ' dır. Olası değerler listesi için bkz: [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `MenuOrID`  
 [in] Alt pencere için pencere tanımlayıcısı. Üst düzey bir pencere için bir menü işlemek için pencere. Varsayılan değer **0U**.  
  
 `lpCreateParam`  
 [in] Pencere oluşturma verileri için bir işaretçi. Tam açıklama için son parametre açıklamasına bakın [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, yeni oluşturulan penceresine; tanıtıcısı Aksi takdirde, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Varolan pencere sınıfı adı kaydedilir [m_lpszClassName](#m_lpszclassname). **Oluşturma** bu yeni sınıfına dayalı bir pencere oluşturur. Yeni oluşturulan penceresi otomatik olarak bağlı `CContainedWindowT` nesnesi.  
  
> [!NOTE]
>  Çağırmayın **oluşturma** adlı durumunda [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  0 değeri olarak kullanılıyorsa, `MenuOrID` parametresi 0U belirtilmelidir (Derleyici Hatası önlemek için varsayılan değer).  
  
##  <a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 Tarafından çağrılır [WindowProc](#windowproc) ileti eşlemesi tarafından işlenmemiş iletilerini işlemek için.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `uMsg`  
 [in] Pencereyi gönderilen ileti.  
  
 `wParam`  
 [in] Ek ileti özgü bilgiler.  
  
 `lParam`  
 [in] Ek ileti özgü bilgiler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `DefWindowProc` çağrıları [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) belirtilen pencere yordamı ileti bilgilerini göndermek için Win32 işlevi [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
##  <a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 Geçerli iletiyi döndürür ( **m_pCurrentMsg**).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde paketlenmiş iletinin geçerli `MSG` yapısı.  
  
##  <a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 Kapsanan penceresi şu anda kullanılan ileti eşlemesi tanıtıcısı tutar.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ileti eşlemesi içeren nesnesinde bildirilmesi gerekir.  
  
 Varsayılan ileti eşlemesi bildirilen ile [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), her zaman sıfır tarafından tanımlanır. Bir alternatif ileti eşlemesi bildirilen ile [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), tarafından tanımlanan `msgMapID`.  
  
 `m_dwMsgMapID`ilk oluşturucusu tarafından başlatılır ve çağırarak değiştirilebilir [SwitchMessageMap](#switchmessagemap). Bir örnek için bkz: [CContainedWindowT genel bakış](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 Varolan bir pencere sınıfı adını belirtir.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir pencere oluşturduğunuzda [oluşturma](#create) bu varolan sınıfa bağlı, ancak kullanan yeni bir pencere sınıfı kaydeder [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName`yapıcı tarafından başlatılır. Bir örnek için bkz: [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel bakış.  
  
##  <a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 Kapsanan penceresi Sınıflandırma, `m_pfnSuperWindowProc` pencere sınıfı özgün pencere yordamı işaret eder.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yani kapsanan pencere superclassed ise, varolan bir sınıfa değiştiren bir pencere sınıfına dayalıdır `m_pfnSuperWindowProc` işaret varolan penceresi sınıfının pencere yordamı.  
  
 [DefWindowProc](#defwindowproc) yöntemi kaydedilen pencere yordamı için ileti bilgileri gönderir `m_pfnSuperWindowProc`.  
  
##  <a name="m_pobject"></a>CContainedWindowT::m_pObject  
 İşaret nesnesini içeren `CContainedWindowT` nesnesi.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekir, sınıf türetin bu kapsayıcı [CMessageMap](../../atl/reference/cmessagemap-class.md), içerdiği pencere tarafından kullanılan ileti eşlemesi bildirir.  
  
 `m_pObject`yapıcı tarafından başlatılır. Bir örnek için bkz: [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel bakış.  
  
##  <a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 Tarafından çağrılır [oluşturma](#create) kapsanan penceresinin pencere sınıfı kaydetmek için.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, atom, Kaydedilmekte pencere sınıfı tanıtan; Aksi durumda, sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu pencere sınıfı üzerinde mevcut bir sınıfın temel ancak kullanan [CContainedWindowT::WindowProc](#windowproc). Varolan penceresi sınıfın adını ve pencere yordamı kaydedilir [m_lpszClassName](#m_lpszclassname) ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)sırasıyla.  
  
##  <a name="subclasswindow"></a>CContainedWindowT::SubclassWindow  
 Pencerenin tanımlanan alt sınıfların `hWnd` ve ekleninceye `CContainedWindowT` nesnesi.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] Sınıflandırma penceresine işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** pencere başarıyla altsınıflanmış; Aksi takdirde ise **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Altsınıflanmış penceresi artık kullanır [CContainedWindowT::WindowProc](#windowproc). Özgün pencere yordamı kaydedilir [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Çağırmayın `SubclassWindow` adlı durumunda [oluşturma](#create).  
  
##  <a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 Hangi ileti eşlemesi içerdiği pencere iletileri işlemek için kullanılan değiştirir.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwMsgMapID`  
 [in] İleti eşleme tanımlayıcısı. Varsayılan ileti eşlemesi kullanmak için bildirilen ile [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), sıfır geçirin. Bir alternatif ileti eşlemesi kullanmak için bildirilen ile [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçirmek `msgMapID`.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti eşlemesi içeren nesnesinde tanımlanması gerekir.  
  
 İleti eşleme tanımlayıcısı başlangıçta oluşturucuda belirtin.  
  
##  <a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 Altsınıflanmış penceresinden ayırır `CContainedWindowT` nesne ve kaydedilen özgün pencere yordamı yükler [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bForce`  
 [in] Kümesine **TRUE** geri yüklenmesi özgün pencere yordamı zorlamak için olsa bile bu pencere yordamı `CContainedWindowT` nesne şu anda etkin değil. Varsa `bForce` ayarlanır **FALSE** ve bu pencere yordamı `CContainedWindowT` nesne şu anda etkin değil, özgün pencere yordamı yüklenemez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce sınıflandırma penceresine işleci. Varsa `bForce` ayarlanır **FALSE** ve bu pencere yordamı `CContainedWindowT` nesnesi şu anda etkin değil, döndürür **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere yok önce özgün pencere yordamı geri yüklemek istiyorsanız bu yöntemi kullanın. Aksi takdirde, [WindowProc](#windowproc) pencere bozulduğunda otomatik olarak bunu yapar.  
  
##  <a name="windowproc"></a>CContainedWindowT::WindowProc  
 Bu statik yöntem pencere yordamı uygular.  
  
```
static LRESULT CALLBACK WindowProc(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] Penceresine işleci.  
  
 `uMsg`  
 [in] Pencereyi gönderilen ileti.  
  
 `wParam`  
 [in] Ek ileti özgü bilgiler.  
  
 `lParam`  
 [in] Ek ileti özgü bilgiler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
 `WindowProc`tarafından tanımlanan ileti eşlemesi iletileri yönlendiren [m_dwMsgMapID](#m_dwmsgmapid). Gerekirse, `WindowProc` çağrıları [DefWindowProc](#defwindowproc) ek ileti işleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWindow sınıfı](../../atl/reference/cwindow-class.md)   
 [CWindowImpl sınıfı](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap sınıfı](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
