---
title: Cwindowımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb99d0cb37fff5abe5a7eb54d3ba9c4226e5fd1c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197207"
---
# <a name="cwindowimpl-class"></a>Cwindowımpl sınıfı
Oluşturma veya bir pencere sınıflara için yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Yeni sınıfınıza türetilen `CWindowImpl`.  
  
 *Ttemel*  
 Sınıfın temel sınıf. Varsayılan olarak, temel bir sınıftır [CWindow](../../atl/reference/cwindow-class.md).  
  
 *TWinTraits*  
 A [nitelikler sınıfı](../../atl/understanding-window-traits.md) stilleri pencerenizin tanımlayan. Varsayılan, `CControlWinTraits` değeridir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|Bir pencere oluşturur.|  
  
### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT yöntemleri  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|  
|[GetCurrentMessage](#getcurrentmessage)|Geçerli bir ileti döndürür.|  
|[GetWindowProc](#getwindowproc)|Geçerli pencere yordamını döndürür.|  
|[OnFinalMessage](#onfinalmessage)|Son ileti alındıktan sonra çağırılır (genellikle WM_NCDESTROY).|  
|[SubclassWindow](#subclasswindow)|Alt sınıfların bir pencere.|  
|[UnsubclassWindow](#unsubclasswindow)|Daha önce alt sınıflanan bir pencere getirir.|  
  
### <a name="static-methods"></a>Statik yöntemler  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|Statik bir örneğini döndürür [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md), pencere sınıf bilgilerini yönetir.|  
|[WindowProc](#windowproc)|Pencereye gönderilen iletileri işler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfın özgün pencere yordamını işaret eder.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `CWindowImpl` varolan pencereye bir pencere veya ImageSource alt sınıfı oluşturmak için. `CWindowImpl` pencere yordamını uygun işleyicileri iletilerini yönlendirmek için ileti eşlemesi kullanır.  
  
 `CWindowImpl::Create` tarafından yönetilen pencere sınıfı bilgilere dayanarak bir pencere oluşturur [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl` içeren [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) yani makrosu `CWndClassInfo` yeni bir pencere sınıfını kaydeder. Var olan bir pencere sınıfı için sınıf isterseniz, sınıfından türetilir `CWindowImpl` ve [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu. Bu durumda, `CWndClassInfo` kullanır ancak mevcut bir sınıfı temel alan bir pencere sınıfını kaydeder `CWindowImpl::WindowProc`. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Çünkü `CWndClassInfo` tek bir pencere sınıfı örneği oluşturulan her pencere bilgilerini yöneten `CWindowImpl` aynı pencere sınıfını esas alır.  
  
 `CWindowImpl` Ayrıca, pencere sınıflara destekler. `SubclassWindow` Yöntemi varolan pencereye ekler `CWindowImpl` nesne ve pencere yordamına değişiklikleri `CWindowImpl::WindowProc`. Her bir örneğini `CWindowImpl` farklı bir pencere öğesinin alt sınıfı olabilir.  
  
> [!NOTE]
>  Verilen herhangi biri için `CWindowImpl` nesne, çağırın ya da `Create` veya `SubclassWindow`. İki yöntem de aynı nesne üzerinde çağırmak yok.  
  
 Ek olarak `CWindowImpl`, ATL sağlar [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) bulunan bir pencere içinde başka bir nesne oluşturma.  
  
 Temel sınıf yok edicisini (~ `CWindowImplRoot`) nesne yok edilene önce pencereyi kalktığını sağlar.  
  
 `CWindowImpl` öğesinden türetilen `CWindowImplBaseT`, öğesinden türetildiğini `CWindowImplRoot`, öğesinden türetildiğini `TBase` ve [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Daha fazla bilgi|Bkz. |  
|--------------------------------|---------|  
|Denetimler oluşturma|[ATL öğretici](../../atl/active-template-library-atl-tutorial.md)|  
|ATL kullanarak|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|  
|ATL projesi Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="create"></a>  CWindowImpl::Create  
 Yeni bir pencere sınıfını esas bir pencere oluşturur.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWndParent*  
 [in] Üst veya sahibi penceresine tanıtıcısı.  
  
 *Rect*  
 [in] A [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) pencerenin konumunu belirten yapısı. `RECT` İşaretçi veya başvuruya göre geçirilebilir.  
  
 *szWindowName*  
 [in] Pencerenin adını belirtir. Varsayılan değer NULL olur.  
  
 *dwStyle*  
 [in] Pencere stili. Bu değer, pencerenin için nitelikler sınıfı tarafından sağlanan stil ile birleştirilir. Varsayılan değer nitelikler sınıfı stili üzerinde tam denetim verir. Olası değerler listesi için bkz. [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK.  
  
 *dwExStyle*  
 [in] Genişletilmiş pencere stili. Bu değer, pencerenin için nitelikler sınıfı tarafından sağlanan stil ile birleştirilir. Varsayılan değer nitelikler sınıfı stili üzerinde tam denetim verir. Olası değerler listesi için bkz. [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK.  
  
 *MenuOrID*  
 [in] Alt pencere için pencere tanımlayıcısı. Bir üst düzey pencere için bir pencere için menü tanıtıcısı. Varsayılan değer **0U**.  
  
 *lpCreateParam*  
 [in] Pencere oluşturma veri işaretçisi. Tam açıklama için son parametresi açıklamasına bakın [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, yeni oluşturulan penceresine tanıtıcısı. Aksi takdirde NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 `Create` henüz kayıtlı değilse, öncelikle pencere sınıfını kaydeder. Yeni oluşturulan penceresi otomatik olarak bağlı `CWindowImpl` nesne.  
  
> [!NOTE]
>  Çağırmayın `Create` zaten çağrılırsa [SubclassWindow](#subclasswindow).  
  
 Mevcut bir pencere sınıfı temel alan bir pencere sınıfını kullanmak için sınıfından türetilen `CWindowImpl` ve [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu. Var olan pencereyi sınıfın pencere yordamını kaydedilir [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Daha fazla bilgi için [Cwindowımpl](../../atl/reference/cwindowimpl-class.md) genel bakış.  
  
> [!NOTE]
>  0 değeri olarak kullanılıyorsa *MenuOrID* parametresi 0U belirtilmelidir (Derleyici Hatası kaçınmak için varsayılan değer).  
  
##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc  
 Çağıran [WindowProc](#windowproc) ileti eşlemesi tarafından işlenmemiş iletilerini işlemek için.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
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
  
 İşlev parametre olmadan, otomatik olarak geçerli ileti gerekli parametreleri alır.  
  
##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage  
 İçinde paketlenmiş geçerli bir ileti döndürür `MSG` yapısı.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ileti.  
  
##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc  
 Döndürür `WindowProc`, geçerli pencere yordamını.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli pencere yordamını.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere yordamını sizinkiyle değiştirmek için bu yöntemi yok sayın.  
  
##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo  
 Çağıran [Oluştur](#create) pencere sınıf bilgilerine erişmek için.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Statik bir örneğini [Cwndclassınfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CWindowImpl` bu yöntemle alır [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu olarak yeni bir pencere sınıfını belirtir.  
  
 Sizin sınıfınızdan sınıfın var olan bir pencere sınıfı için türetilen `CWindowImpl` ve [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) geçersiz kılmak için makro `GetWndClassInfo`. Daha fazla bilgi için [Cwindowımpl](../../atl/reference/cwindowimpl-class.md) genel bakış.  
  
 DECLARE_WND_CLASS ve DECLARE_WND_SUPERCLASS makroları kullanmanın yanı sıra, geçersiz kılabilirsiniz `GetWndClassInfo` kendi uygulaması.  
  
##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc  
 Pencerenin bağlı olarak aşağıdaki pencere yordamları birini işaret eder.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
|Pencere türü|Pencere yordamı|  
|--------------------|----------------------|  
|Bir pencere aracılığıyla belirtilen yeni bir pencere sınıfını esas [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu.|[DefWindowProc](https://msdn.microsoft.com/library/windows/desktop/ms633572) Win32 işlevi.|  
|Bir pencere aracılığıyla belirtilen varolan bir sınıf değiştiren bir pencere sınıfını esas [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu.|Var olan pencereyi sınıfın pencere yordamını.|  
|Sınıflandırılmış bir pencere.|Altsınıflanmış pencerenin özgün pencere yordamını.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) kaydedilmiş pencere yordamını bilgi iletisi gönderen `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage  
 (Genellikle WM_NCDESTROY) son ileti alındıktan sonra çağrılır.  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWnd*  
 [in] Yok ediliyor penceresi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması `OnFinalMessage` hiçbir şey yapmaz, ancak pencere yok etme öncesinde temizleme işlemek için bu işlevi geçersiz kılabilirsiniz. Pencere yok etme sırasında nesne otomatik olarak silmek istiyorsanız, çağırabilirsiniz **; bunu silin** Bu işlevde.  
  
##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow  
 Pencerenin tanımlanan alt sınıfları *hWnd* ve ekler `CWindowImpl` nesne.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *hWnd*  
 [in] Sınıflandırma penceresine tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencerenin başarıyla sınıflandırma TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Altsınıflanmış penceresi artık kullanan [CWindowImpl::WindowProc](#windowproc). Özgün pencere yordamını kaydedilir [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Çağırmayın `SubclassWindow` zaten çağrılırsa [Oluştur](#create).  
  
##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow  
 Altsınıflanmış penceresinden ayırır `CWindowImpl` nesne ve kaydedilmiş özgün pencere yordamını döndürür [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce sınıflandırma penceresine tanıtıcısı.  
  
##  <a name="windowproc"></a>  CWindowImpl::WindowProc  
 Bu statik işlev pencere yordamını uygular.  
  
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
 `WindowProc` Varsayılan ileti eşlemesi kullanır (ile bildirilen [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) uygun işleyicileri iletilerini yönlendirmek için. Gerekirse, `WindowProc` çağrıları [DefWindowProc](#defwindowproc) ek ileti işleme için. Son ileti işlenmezse `WindowProc` şunları yapar:  
  
-   Pencerenin unsubclassed olduysa unsubclassing gerçekleştirir.  
  
-   Temizler `m_hWnd`.  
  
-   Çağrıları [OnFinalMessage](#onfinalmessage) önce penceresi yok.  
  
 Geçersiz kılabilirsiniz `WindowProc` iletileri işlemek için farklı bir mekanizma sağlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
