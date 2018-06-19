---
title: CWindowImpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: 4884bbacd03675d00cb1a49b937265ab5faa2835
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366162"
---
# <a name="cwindowimpl-class"></a>CWindowImpl sınıfı
Oluşturmak veya bir pencereyi alt sınıf yapma için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Yeni sınıfınıza türetilen `CWindowImpl`.  
  
 *TBase*  
 Sınıfınızın temel sınıf. Varsayılan olarak, temel sınıftır [CWindow](../../atl/reference/cwindow-class.md).  
  
 `TWinTraits`  
 A [nitelikler sınıfı](../../atl/understanding-window-traits.md) pencerenizi için stiller tanımlar. Varsayılan, `CControlWinTraits` değeridir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|Bir pencere oluşturur.|  
  
### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT yöntemleri  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|  
|[GetCurrentMessage](#getcurrentmessage)|Geçerli iletisi döndürür.|  
|[GetWindowProc](#getwindowproc)|Geçerli pencere yordamı döndürür.|  
|[OnFinalMessage](#onfinalmessage)|Sıradaki son iletiyi aldıktan sonra adlı (genellikle `WM_NCDESTROY`).|  
|[SubclassWindow](#subclasswindow)|Alt sınıfların bir pencere.|  
|[UnsubclassWindow](#unsubclasswindow)|Daha önce altsınıflanmış bir pencere getirir.|  
  
### <a name="static-methods"></a>Statik yöntemler  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|Statik bir örneğini döndüren [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md), pencere sınıfı bilgileri yönetir.|  
|[WindowProc](#windowproc)|Pencereyi gönderilen iletileri işler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfının özgün pencere yordamı noktalarına.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `CWindowImpl` varolan pencerede penceresi veya bir alt kümesi oluşturmak için. `CWindowImpl` pencere yordamı uygun işleyicileri iletilerini yönlendirmek için ileti eşlemesi kullanır.  
  
 `CWindowImpl::Create` tarafından yönetilen pencere sınıfı bilgilere dayanarak bir pencere oluşturur [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md). `CWindowImpl` içeren [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) anlamına gelir makrosu `CWndClassInfo` yeni bir pencere sınıfı kaydeder. Varolan bir pencere sınıfı için sınıf istiyorsanız, sınıfından türetilen `CWindowImpl` ve dahil [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu. Bu durumda, `CWndClassInfo` varolan bir sınıfa bağlı, ancak kullanan bir pencere sınıfı kaydeder `CWindowImpl::WindowProc`. Örneğin:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  Çünkü `CWndClassInfo` yalnızca bir pencere sınıfı, bir örneği üzerinden oluşturulan her pencere bilgilerini yöneten `CWindowImpl` aynı penceresi sınıfına dayalıdır.  
  
 `CWindowImpl` Ayrıca penceresi sınıflara destekler. `SubclassWindow` Yöntemi iliştirir varolan penceresine `CWindowImpl` nesne ve pencere yordamı değişiklikleri `CWindowImpl::WindowProc`. Her örneği `CWindowImpl` farklı bir pencere bir alt kümesi olabilir.  
  
> [!NOTE]
>  Verilen herhangi için `CWindowImpl` nesne, ya da çağrısı **oluşturma** veya `SubclassWindow`. Aynı nesne üzerinde her iki yöntem çağırma yok.  
  
 Ek olarak `CWindowImpl`, ATL sağlar [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) başka bir nesnenin bulunan bir pencere oluşturulamadı.  
  
 Taban sınıf yıkıcı (~ **CWindowImplRoot**) nesne yok önce pencereyi kayboluyor sağlar.  
  
 `CWindowImpl` türetilen **CWindowImplBaseT**, den türetilen **CWindowImplRoot**, den türetilen **TBase** ve [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
|Daha fazla bilgi|Bkz. |  
|--------------------------------|---------|  
|Denetimler oluşturma|[ATL öğretici](../../atl/active-template-library-atl-tutorial.md)|  
|ATL Windows'da kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|  
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="create"></a>  CWindowImpl::Create  
 Yeni bir pencere sınıfına dayalı bir pencere oluşturur.  
  
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
 `hWndParent`  
 [in] Üst veya sahibi penceresine işleci.  
  
 `rect`  
 [in] A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı penceresinin konumunu belirtme. `RECT` Veya başvuruya göre işaretçi geçirilebilir.  
  
 `szWindowName`  
 [in] Pencerenin adını belirtir. Varsayılan değer **NULL**.  
  
 `dwStyle`  
 [in] Pencere stili. Bu değer için pencere nitelikler sınıfı tarafından sağlanan stili ile birleştirilir. Varsayılan değer olarak nitelikler sınıfı stili üzerinde tam denetim verir. Olası değerler listesi için bkz: [CreateWindow'u](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK'sındaki.  
  
 `dwExStyle`  
 [in] Genişletilmiş pencere stili. Bu değer için pencere nitelikler sınıfı tarafından sağlanan stili ile birleştirilir. Varsayılan değer olarak nitelikler sınıfı stili üzerinde tam denetim verir. Olası değerler listesi için bkz: [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `MenuOrID`  
 [in] Alt pencere için pencere tanımlayıcısı. Üst düzey bir pencere için bir menü işlemek için pencere. Varsayılan değer **0U**.  
  
 `lpCreateParam`  
 [in] Pencere oluşturma verileri için bir işaretçi. Tam açıklama için son parametre açıklamasına bakın [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, yeni oluşturulan penceresine tanıtıcısı. Aksi takdirde, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 **Oluşturma** henüz kayıtlı pencere sınıfı ilk kaydeder. Yeni oluşturulan penceresi otomatik olarak bağlı `CWindowImpl` nesnesi.  
  
> [!NOTE]
>  Çağırmayın **oluşturma** adlı durumunda [SubclassWindow](#subclasswindow).  
  
 Varolan bir pencere sınıfına dayalı bir pencere sınıfı kullanmak için sınıfından türetilen `CWindowImpl` ve dahil [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu. Varolan penceresi sınıfının pencere yordamı kaydedilir [m_pfnSuperWindowProc](#m_pfnsuperwindowproc). Daha fazla bilgi için bkz: [CWindowImpl](../../atl/reference/cwindowimpl-class.md) genel bakış.  
  
> [!NOTE]
>  0 değeri olarak kullanılıyorsa, `MenuOrID` parametresi 0U belirtilmelidir (Derleyici Hatası önlemek için varsayılan değer).  
  
##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc  
 Tarafından çağrılır [WindowProc](#windowproc) ileti eşlemesi tarafından işlenmemiş iletilerini işlemek için.  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
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
  
 Hiçbir parametre işlevi, geçerli iletiden gerekli parametreleri otomatik olarak alır.  
  
##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage  
 İçinde paketlenmiş geçerli iletiyi döndürür `MSG` yapısı.  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ileti.  
  
##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc  
 Döndürür `WindowProc`, geçerli pencere yordamı.  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli pencere yordamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Pencere yordamı kendi değiştirmek için bu yöntemi geçersiz kılın.  
  
##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo  
 Tarafından çağrılır [oluşturma](#create) pencere sınıfı bilgilere erişmek için.  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Statik bir örneğini [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `CWindowImpl` bu yöntemle edinir [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makro yeni bir pencere sınıfı belirtir.  
  
 Sınıfın var olan bir pencere sınıfı için sınıfından türetilen `CWindowImpl` ve dahil [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) geçersiz kılmak için makrosu `GetWndClassInfo`. Daha fazla bilgi için bkz: [CWindowImpl](../../atl/reference/cwindowimpl-class.md) genel bakış.  
  
 Kullanarak yanı sıra `DECLARE_WND_CLASS` ve `DECLARE_WND_SUPERCLASS` makroları kılabilirsiniz `GetWndClassInfo` kendi uygulaması.  
  
##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc  
 Pencerenin bağlı olarak aşağıdaki pencere yordamlardan birini işaret eder.  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Açıklamalar  
  
|Pencere türü|Pencere yordamı|  
|--------------------|----------------------|  
|Bir pencere aracılığıyla belirtilen yeni bir pencere sınıfı temelinde [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu.|[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) Win32 işlevi.|  
|Bir pencere aracılığıyla belirtilen mevcut bir sınıfın değiştiren bir pencere sınıfı temelinde [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu.|Varolan penceresi sınıfının pencere yordamı.|  
|Altsınıflanmış penceresini açın.|Pencere yordamı özgün altsınıflanmış pencerenin.|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc) kaydedilen pencere yordamı için bilgi iletisi `m_pfnSuperWindowProc`.  
  
##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage  
 Sıradaki son iletiyi aldıktan sonra adlı (genellikle `WM_NCDESTROY`).  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] Pencerenin yok için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulaması `OnFinalMessage` hiçbir şey yapmaz, ancak bir pencere yok etme önce temizleme işlemek için bu işlev geçersiz kılabilirsiniz. Otomatik olarak nesnenizin pencere yok etme bağlı silmek istiyorsanız, çağırabilirsiniz `delete this;` Bu işlevde.  
  
##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow  
 Pencerenin tanımlanan alt sınıfların `hWnd` ve ekleninceye `CWindowImpl` nesnesi.  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] Sınıflandırma penceresine işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** pencere başarıyla altsınıflanmış; Aksi takdirde ise **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Altsınıflanmış penceresi artık kullanır [CWindowImpl::WindowProc](#windowproc). Özgün pencere yordamı kaydedilir [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
> [!NOTE]
>  Çağırmayın `SubclassWindow` adlı durumunda [oluşturma](#create).  
  
##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow  
 Altsınıflanmış penceresinden ayırır `CWindowImpl` nesne ve kaydedilen özgün pencere yordamı yükler [m_pfnSuperWindowProc](#m_pfnsuperwindowproc).  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce sınıflandırma penceresine işleci.  
  
##  <a name="windowproc"></a>  CWindowImpl::WindowProc  
 Bu statik işlev pencere yordamı uygular.  
  
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
 `WindowProc` Varsayılan ileti eşlemesi kullanır (ile bildirilen [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)) uygun işleyicileri iletilerini yönlendirmek için. Gerekirse, `WindowProc` çağrıları [DefWindowProc](#defwindowproc) ek ileti işleme. Son ileti işlenmedi, `WindowProc` şunları yapar:  
  
-   Pencerenin unsubclassed ise unsubclassing gerçekleştirir.  
  
-   Temizler `m_hWnd`.  
  
-   Çağrıları [OnFinalMessage](#onfinalmessage) önce penceresi yok.  
  
 Geçersiz kılabilirsiniz `WindowProc` iletileri işlemek için farklı bir mekanizma sağlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
