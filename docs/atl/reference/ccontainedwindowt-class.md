---
title: CContainedWindowT sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94468f2499a349847f62ed65a03e88cf776536ce
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207202"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT sınıfı
Bu sınıf, başka bir nesne içinde yer alan bir pencere uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>Parametreler  
 *Ttemel*  
 Yeni sınıfın temel sınıf. Varsayılan temel sınıf `CWindow`.  
  
 *TWinTraits*  
 Stilleri pencerenizin tanımlar nitelikler sınıfı. Varsayılan, `CControlWinTraits` değeridir.  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md) özelleştirmesi olan `CContainedWindowT`. Temel sınıf veya nitelikler değiştirmek istiyorsanız, kullanın `CContainedWindowT` doğrudan.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|Oluşturucu. Hangi ileti eşlemesi kapsanan pencere iletilerini işleyecek belirtmek için veri üyeleri başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|Bir pencere oluşturur.|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|Geçerli bir ileti döndürür.|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|Kapsanan pencerenin pencere sınıfını kaydeder.|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|Alt sınıfların bir pencere.|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|Değişiklikleri hangi ileti eşlemesi kapsanan pencere iletilerini işlemek için kullanılır.|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|Daha önce alt sınıflanan bir pencere getirir.|  
|[CContainedWindowT::WindowProc](#windowproc)|(Statik) Kapsanan pencerenin gönderilen iletileri işler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|Hangi ileti eşlemesi kapsanan pencere iletilerini işleyecek tanımlar.|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|Yeni bir pencere sınıf dayanacak var olan bir pencere sınıfı adını belirtir.|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfın özgün pencere yordamını işaret eder.|  
|[CContainedWindowT::m_pObject](#m_pobject)|Kapsayıcı nesnenin işaret eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CContainedWindowT` başka bir nesne içinde yer alan bir pencere uygular. `CContainedWindowT`Pencere yordamı kullanan bir ileti eşleme uygun işleyicilere doğrudan iletileri içeren nesnesindeki güçlendirin. Oluştururken bir `CContainedWindowT` nesnesi, belirttiğiniz hangi ileti eşlemesi kullanılmalıdır.  
  
 `CContainedWindowT` Yeni bir pencere, var olan bir pencere sınıfı tarafından superclassing oluşturmanıza olanak sağlar. `Create` Yöntemi ilk kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıfını kaydeder `CContainedWindowT::WindowProc`. `Create` ardından bu yeni pencere sınıfına göre bir pencere oluşturur. Her bir örneği `CContainedWindowT` sınıfın farklı pencere sınıfını kullanabilirsiniz.  
  
 `CContainedWindowT` Ayrıca, pencere sınıflara destekler. `SubclassWindow` Yöntemi varolan pencereye ekler `CContainedWindowT` nesne ve pencere yordamına değişiklikleri `CContainedWindowT::WindowProc`. Her bir örneğini `CContainedWindowT` farklı bir pencere öğesinin alt sınıfı olabilir.  
  
> [!NOTE]
>  Verilen herhangi biri için `CContainedWindowT` nesne, çağırın ya da `Create` veya `SubclassWindow`. İki yöntem de aynı nesne üzerinde çağıracağı değil.  
  
 Kullandığınızda **göre denetimi ekleme** Sihirbazı otomatik olarak ekler ATL Proje Sihirbazı'nda seçeneği bir `CContainedWindowT` sınıfı denetimi uygulamak için veri üyesi. Aşağıdaki örnek, kapsanan pencerenin nasıl bildirildiği gösterir:  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|Daha fazla bilgi|Bkz. |  
|--------------------------------|---------|  
|Denetimler oluşturma|[ATL öğretici](../../atl/active-template-library-atl-tutorial.md)|  
|ATL kullanarak|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|  
|ATL projesi Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](https://msdn.microsoft.com/library/windows/desktop/ms632595) ve sonraki konularda Windows SDK'sı|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>  CContainedWindowT::CContainedWindowT  
 Veri üyeleri Oluşturucusu başlatır.  
  
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
 *lpszClassName*  
 [in] Kapsanan pencere dayanacak var olan bir pencere sınıfı adı.  
  
 *pObject*  
 [in] İleti eşlemesi bildirir içeren nesneye bir işaretçi. Bu nesnenin sınıfı öğesinden türetilmelidir [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 *dwMsgMapID*  
 [in] Kapsanan pencere iletilerini işleyecek ileti eşlemesi tanımlar. Varsayılan değer olan 0 ile bildirilen varsayılan ileti eşlemesi belirtir [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Bir diğer ileti eşlemesi kullanmak için bildirilen [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçmesi `msgMapID`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir pencere aracılığıyla oluşturmak istiyorsanız [Oluştur](#create), için var olan bir pencere sınıf adını geçmelidir *lpszClassName* parametresi. Bir örnek için bkz. [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) genel bakış.  
  
 Üç Oluşturucusu vardır:  
  
-   Üç bağımsız değişken genellikle olarak adlandırılan bir oluşturucudur.  
  
-   İki bağımsız değişken Oluşturucu sınıf adından kullanan `TBase::GetWndClassName`.  
  
-   Bağımsız değişkenler daha sonra sağlamak istiyorsanız, oluşturucu bağımsız değişken olmadan kullanılır. Daha sonra çağırdığınızda, pencere sınıf adı, ileti eşleme nesnesi ve ileti Haritası kimliği sağlamalısınız `Create`.  
  
 Varsa, var olan bir pencereyi alt sınıf aracılığıyla [SubclassWindow](#subclasswindow), *lpszClassName* değeri kullanılmaz; bu nedenle, bu parametre için NULL geçirebilirsiniz.  
  
##  <a name="create"></a>  CContainedWindowT::Create  
 Çağrıları [RegisterWndSuperclass](#registerwndsuperclass) kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıfını [CContainedWindowT::WindowProc](#windowproc).  
  
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
 *lpszClassName*  
 [in] Kapsanan pencere dayanacak var olan bir pencere sınıfı adı.  
  
 *pObject*  
 [in] İleti eşlemesi bildirir içeren nesneye bir işaretçi. Bu nesnenin sınıfı öğesinden türetilmelidir [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 *dwMsgMapID*  
 [in] Kapsanan pencere iletilerini işleyecek ileti eşlemesi tanımlar. Varsayılan değer olan 0 ile bildirilen varsayılan ileti eşlemesi belirtir [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). Bir diğer ileti eşlemesi kullanmak için bildirilen [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçmesi `msgMapID`.  
  
 *hWndParent*  
 [in] Üst veya sahibi penceresine tanıtıcısı.  
  
 *Rect*  
 [in] A [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) pencerenin konumunu belirten yapısı. `RECT` İşaretçi veya başvuruya göre geçirilebilir.  
  
 *szWindowName*  
 [in] Pencerenin adını belirtir. Varsayılan değer NULL olur.  
  
 *dwStyle*  
 [in] Pencere stili. Varsayılan değer: WS_CHILD &#124; ws_vısıble. Olası değerler listesi için bkz. [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK.  
  
 *dwExStyle*  
 [in] Genişletilmiş pencere stili. Varsayılan değer, genişletilmiş stil yok anlamına gelen 0 ' dır. Olası değerler listesi için bkz. [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK.  
  
 *MenuOrID*  
 [in] Alt pencere için pencere tanımlayıcısı. Bir üst düzey pencere için bir pencere için menü tanıtıcısı. Varsayılan değer **0U**.  
  
 *lpCreateParam*  
 [in] Pencere oluşturma veri işaretçisi. Tam açıklama için son parametresi açıklamasına bakın [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, yeni oluşturulan penceresine; tanıtıcısı Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Mevcut Windows sınıf adı kaydedilir [m_lpszClassName](#m_lpszclassname). `Create` ardından bu yeni sınıfına göre bir pencere oluşturur. Yeni oluşturulan penceresi otomatik olarak bağlı `CContainedWindowT` nesne.  
  
> [!NOTE]
>  Çağırmayın `Create` zaten çağrılırsa [SubclassWindow](#subclasswindow).  
  
> [!NOTE]
>  0 değeri olarak kullanılıyorsa *MenuOrID* parametresi 0U belirtilmelidir (Derleyici Hatası kaçınmak için varsayılan değer).  
  
##  <a name="defwindowproc"></a>  CContainedWindowT::DefWindowProc  
 Çağıran [WindowProc](#windowproc) ileti eşlemesi tarafından işlenmemiş iletilerini işlemek için.  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 *uMsg*  
 [in] Pencereye gönderilen ileti.  
  
 *wParam*  
 [in] İletiye özgü ek bilgiler.  
  
 *lParam*  
 [in] İletiye özgü ek bilgiler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `DefWindowProc` çağrıları [CallWindowProc](https://msdn.microsoft.com/library/windows/desktop/ms633571) belirtilen pencere yordamını ileti bilgileri göndermek için Win32 işlevini [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
##  <a name="getcurrentmessage"></a>  CContainedWindowT::GetCurrentMessage  
 Geçerli bir ileti döndürür (`m_pCurrentMsg`).  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde paketlenmiş, geçerli ileti `MSG` yapısı.  
  
##  <a name="m_dwmsgmapid"></a>  CContainedWindowT::m_dwMsgMapID  
 Kapsanan pencere için şu anda kullanılan ileti eşlemesi tanımlayıcısını tutar.  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ileti eşlemesi içeren bir nesne bildirilmelidir.  
  
 Varsayılan ileti eşlemesi ile bildirilmiş [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), her zaman sıfır tarafından tanımlanır. Bir diğer ileti eşlemesi ile bildirilmiş [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), tarafından tanımlanan `msgMapID`.  
  
 `m_dwMsgMapID` ilk Oluşturucu tarafından başlatılır ve çağırarak değiştirilebilir [SwitchMessageMap](#switchmessagemap). Bir örnek için bkz. [CContainedWindowT genel bakış](../../atl/reference/ccontainedwindowt-class.md).  
  
##  <a name="m_lpszclassname"></a>  CContainedWindowT::m_lpszClassName  
 Var olan bir pencere sınıfının adını belirtir.  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir pencere oluşturduğunuzda [Oluştur](#create) kullanır ancak bu mevcut bir sınıfı temel alan yeni bir pencere sınıfını kaydeder [CContainedWindowT::WindowProc](#windowproc).  
  
 `m_lpszClassName` Oluşturucu tarafından başlatılır. Bir örnek için bkz. [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel bakış.  
  
##  <a name="m_pfnsuperwindowproc"></a>  CContainedWindowT::m_pfnSuperWindowProc  
 Kapsanan pencerenin alt sınıflanan, `m_pfnSuperWindowProc` pencere sınıfını özgün pencere yordamını işaret eder.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Anlamına gelir kapsanan pencerenin üst ise, varolan bir sınıf değiştiren bir pencere sınıfına dayalıdır `m_pfnSuperWindowProc` noktaları için mevcut pencere sınıfın pencere yordamını.  
  
 [DefWindowProc](#defwindowproc) yöntemi kaydedilmiş pencere yordamını ileti bilgileri gönderir `m_pfnSuperWindowProc`.  
  
##  <a name="m_pobject"></a>  CContainedWindowT::m_pObject  
 İşaret nesnesini içeren `CContainedWindowT` nesne.  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu kapsayıcı, sınıfın türetilmesi gereken [CMessageMap](../../atl/reference/cmessagemap-class.md), kapsanan pencere tarafından kullanılan ileti eşlemesi bildirir.  
  
 `m_pObject` Oluşturucu tarafından başlatılır. Bir örnek için bkz. [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md) genel bakış.  
  
##  <a name="registerwndsuperclass"></a>  CContainedWindowT::RegisterWndSuperclass  
 Çağıran [Oluştur](#create) kapsanan pencerenin pencere sınıfını kaydedilecek.  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, atom, Kaydedilmekte pencere sınıfını tanımlamasının; Aksi takdirde sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu pencere sınıfını mevcut bir sınıfı temel alarak ancak kullanan [CContainedWindowT::WindowProc](#windowproc). Var olan pencereyi sınıfın adı ve pencere yordamı kaydedilir [m_lpszClassName](#m_lpszclassname) ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)sırasıyla.  
  
##  <a name="subclasswindow"></a>  CContainedWindowT::SubclassWindow  
 Pencerenin tanımlanan alt sınıfları *hWnd* ve ekler `CContainedWindowT` nesne.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWnd*  
 [in] Sınıflandırma penceresine tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin başarıyla sınıflandırma TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Altsınıflanmış penceresi artık kullanan [CContainedWindowT::WindowProc](#windowproc). Özgün pencere yordamını kaydedilir [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Çağırmayın `SubclassWindow` zaten çağrılırsa [Oluştur](#create).  
  
##  <a name="switchmessagemap"></a>  CContainedWindowT::SwitchMessageMap  
 Hangi ileti eşlemesi kapsanan pencere iletilerini işlemek için kullanılan değiştirir.  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwMsgMapID*  
 [in] İleti eşleme tanımlayıcısı. Varsayılan ileti eşlemesi kullanmak için bildirilen [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), sıfır geçirin. Bir diğer ileti eşlemesi kullanmak için bildirilen [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), geçmesi `msgMapID`.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti eşlemesi içeren bir nesne içinde tanımlanması gerekir.  
  
 İleti eşleme tanımlayıcısı başlangıçta oluşturucuda belirtin.  
  
##  <a name="unsubclasswindow"></a>  CContainedWindowT::UnsubclassWindow  
 Altsınıflanmış penceresinden ayırır `CContainedWindowT` nesne ve kaydedilmiş özgün pencere yordamını döndürür [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 *bForce*  
 [in] Geri yüklenecek özgün pencere yordamını zorla true olarak ayarlayın olsa bile bu pencere yordamını `CContainedWindowT` nesnesi şu anda etkin değil. Varsa *bForce* FALSE ve pencere yordamı için bu ayar `CContainedWindowT` nesnesi şu anda etkin değil, özgün pencere yordamını geri yüklenmez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce sınıflandırma penceresine tanıtıcısı. Varsa *bForce* FALSE ve pencere yordamı için bu ayar `CContainedWindowT` nesnesi şu anda etkin değil, NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencerenin yok önce özgün pencere yordamını geri yüklemek istiyorsanız bu yöntemi kullanın. Aksi takdirde, [WindowProc](#windowproc) penceresi kaldırıldığında otomatik olarak bunu yapar.  
  
##  <a name="windowproc"></a>  CContainedWindowT::WindowProc  
 Bu statik yöntem, pencere yordamı uygular.  
  
```
static LRESULT CALLBACK WindowProc(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWnd*  
 [in] Pencereye tanıtıcısı.  
  
 *uMsg*  
 [in] Pencereye gönderilen ileti.  
  
 *wParam*  
 [in] İletiye özgü ek bilgiler.  
  
 *lParam*  
 [in] İletiye özgü ek bilgiler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İleti işleme sonucu.  
  
### <a name="remarks"></a>Açıklamalar  
 `WindowProc` tarafından tanımlanan ileti haritasına iletileri yönlendiren [m_dwMsgMapID](#m_dwmsgmapid). Gerekirse, `WindowProc` çağrıları [DefWindowProc](#defwindowproc) ek ileti işleme için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWindow sınıfı](../../atl/reference/cwindow-class.md)   
 [Cwindowımpl sınıfı](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap sınıfı](../../atl/reference/cmessagemap-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
