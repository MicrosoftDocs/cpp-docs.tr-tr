---
title: CWindowImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::CWindowImpl::DefWindowProc
- ATLWIN/ATL::CWindowImpl::GetCurrentMessage
- ATLWIN/ATL::CWindowImpl::GetWindowProc
- ATLWIN/ATL::CWindowImpl::OnFinalMessage
- ATLWIN/ATL::CWindowImpl::SubclassWindow
- ATLWIN/ATL::CWindowImpl::UnsubclassWindow
- ATLWIN/ATL::CWindowImpl::GetWndClassInfo
- ATLWIN/ATL::CWindowImpl::WindowProc
- ATLWIN/ATL::CWindowImpl::m_pfnSuperWindowProc
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
ms.openlocfilehash: b8b633dcf4ea14e899ee00552b553476cf697689
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417770"
---
# <a name="cwindowimpl-class"></a>CWindowImpl sınıfı

Pencere oluşturmak veya altsınıflama için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Yeni sınıfınız `CWindowImpl`türetilir.

*TBase*<br/>
Sınıfınızın temel sınıfı. Varsayılan olarak, temel sınıf [CWindow](../../atl/reference/cwindow-class.md)olur.

*TWinTraits*<br/>
Pencerenize yönelik stilleri tanımlayan bir [nitelikler sınıfı](../../atl/understanding-window-traits.md) . Varsayılan değer: `CControlWinTraits`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWindowImpl:: Create](#create)|Bir pencere oluşturur.|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT yöntemleri

|||
|-|-|
|[DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|
|[GetCurrentMessage](#getcurrentmessage)|Geçerli iletiyi döndürür.|
|[GetWindowProc](#getwindowproc)|Geçerli pencere yordamını döndürür.|
|[OnFinalMessage](#onfinalmessage)|Son İleti alındıktan sonra çağırılır (genellikle WM_NCDESTROY).|
|[SubclassWindow](#subclasswindow)|Bir pencerenin alt sınıfları.|
|[UnsubclassWindow](#unsubclasswindow)|Daha önce bir alt sınıflı pencereyi geri yükler.|

### <a name="static-methods"></a>Statik yöntemler

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|Pencere sınıfı bilgilerini yöneten bir [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)statik örneğini döndürür.|
|[Wimdowproc](#windowproc)|Pencereye gönderilen iletileri işler.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfının özgün pencere yordamını işaret eder.|

## <a name="remarks"></a>Açıklamalar

`CWindowImpl` kullanarak bir pencere oluşturabilir veya varolan bir pencereyi alt sınıfa ekleyebilirsiniz. `CWindowImpl` pencere yordamı, iletileri uygun işleyicilere yönlendirmek için bir ileti eşlemesi kullanır.

`CWindowImpl::Create`, [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)tarafından yönetilen pencere sınıfı bilgilerine dayalı bir pencere oluşturur. `CWindowImpl`, yeni bir pencere sınıfı `CWndClassInfo` kaydeden anlamına gelen [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosunu içerir. Varolan bir pencere sınıfını üst sınıfa eklemek istiyorsanız, `CWindowImpl` sınıftan türetirsiniz ve [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu ekleyin. Bu durumda `CWndClassInfo`, var olan bir sınıfa bağlı olan ancak `CWindowImpl::WindowProc`kullanan bir pencere sınıfını kaydeder. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  `CWndClassInfo` yalnızca bir pencere sınıfının bilgilerini yönettiği için, bir `CWindowImpl` örneği aracılığıyla oluşturulan her pencere aynı pencere sınıfını temel alır.

`CWindowImpl` Ayrıca Window altsınıflama 'ı destekler. `SubclassWindow` yöntemi, var olan bir pencereyi `CWindowImpl` nesnesine iliştirir ve pencere yordamını `CWindowImpl::WindowProc`olarak değiştirir. Her `CWindowImpl` örneği, farklı bir pencerenin alt sınıfını oluşturabilir.

> [!NOTE]
>  Verilen herhangi bir `CWindowImpl` nesnesi için `Create` veya `SubclassWindow`çağırın. Aynı nesne üzerinde her iki yöntemi çağırmayın.

`CWindowImpl`Ayrıca, ATL, başka bir nesnede bulunan bir pencere oluşturmak için [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) sağlar.

Temel sınıf yıkıcısı (~ `CWindowImplRoot`), nesne yok edilmadan önce pencerenin kaybolmasını sağlar.

`CWindowImpl`, `TBase` ve [CMessageMap](../../atl/reference/cmessagemap-class.md)'ten türetilen `CWindowImplRoot`türetilen `CWindowImplBaseT`türetilir.

|Daha fazla bilgi|Bkz.|
|--------------------------------|---------|
|Denetimler oluşturma|[ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md)|
|ATL 'de Windows kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="create"></a>CWindowImpl:: Create

Yeni bir pencere sınıfını temel alan bir pencere oluşturur.

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

*hWndParent*<br/>
'ndaki Üst veya sahip penceresi için tanıtıcı.

*Rect*<br/>
'ndaki Pencerenin konumunu belirten bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısı. `RECT`, işaretçi veya başvuru ile geçirilebilir.

*szWindowName*<br/>
'ndaki Pencerenin adını belirtir. Varsayılan değer NULL.

*dwStyle*<br/>
'ndaki Pencerenin stili. Bu değer, pencerenin nitelikler sınıfı tarafından sunulan stille birleştirilir. Varsayılan değer, biçim üzerinde nitelikler sınıfına tam denetim sağlar. Olası değerlerin bir listesi için Windows SDK, bkz. [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) .

*dwExStyle*<br/>
'ndaki Genişletilmiş pencere stili. Bu değer, pencerenin nitelikler sınıfı tarafından sunulan stille birleştirilir. Varsayılan değer, biçim üzerinde nitelikler sınıfına tam denetim sağlar. Olası değerler listesi için Windows SDK [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) bölümüne bakın.

*MenuOrID*<br/>
'ndaki Bir alt pencere için pencere tanımlayıcısı. Üst düzey bir pencere için, pencerenin menü tutamacı. Varsayılan değer **0u**'dir.

*lpCreateParam*<br/>
'ndaki Pencere oluşturma verilerine yönelik bir işaretçi. Tam açıklama için, [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)için son parametrenin açıklamasına bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yeni oluşturulan pencerenin tanıtıcısı. Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

`Create` ilk olarak, henüz kaydedilmediyse pencere sınıfını kaydeder. Yeni oluşturulan pencere, `CWindowImpl` nesnesine otomatik olarak eklenir.

> [!NOTE]
>  Zaten [SubclassWindow](#subclasswindow)olarak adlandırdıysanız `Create` çağırmayın.

Varolan bir pencere sınıfına dayalı bir pencere sınıfını kullanmak için, `CWindowImpl` sınıftan türetirsiniz ve [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu ekleyin. Mevcut pencere sınıfının pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir. Daha fazla bilgi için bkz. [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 'ye genel bakış.

> [!NOTE]
>  Eğer, *MenuOrID* parametresinin değeri olarak kullanılırsa, bir derleyici hatasından kaçınmak Için 0u (varsayılan değer) olarak belirtilmelidir.

##  <a name="defwindowproc"></a>CWindowImpl::D efWindowProc

İleti eşlemesi tarafından işlenmeyen iletileri işlemek için [WindowProc](#windowproc) tarafından çağırılır.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>Parametreler

*uMsg*<br/>
'ndaki Pencereye gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `DefWindowProc` ileti bilgilerini [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)belirtilen pencere yordamına göndermek Için [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 işlevini çağırır.

Parametresi olmayan işlevi, geçerli iletiden gerekli parametreleri otomatik olarak alır.

##  <a name="getcurrentmessage"></a>CWindowImpl:: GetCurrentMessage

`MSG` yapısında paketlenmiş geçerli iletiyi döndürür.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ileti.

##  <a name="getwindowproc"></a>CWindowImpl:: GetWindowProc

Geçerli pencere yordamını `WindowProc`döndürür.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli pencere yordamı.

### <a name="remarks"></a>Açıklamalar

Pencere yordamını kendi ile değiştirmek için bu yöntemi geçersiz kılın.

##  <a name="getwndclassinfo"></a>CWindowImpl:: GetWndClassInfo

Pencere sınıfı bilgilerine erişmek için [Create](#create) tarafından çağırılır.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Dönüş Değeri

[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)statik örneği.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak `CWindowImpl`, bu yöntemi yeni bir pencere sınıfını belirten [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu aracılığıyla edinir.

Varolan bir pencere sınıfını üst sınıfa eklemek için, `CWindowImpl` sınıftan türetirsiniz ve `GetWndClassInfo`geçersiz kılmak için [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu ekleyin. Daha fazla bilgi için bkz. [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 'ye genel bakış.

DECLARE_WND_CLASS ve DECLARE_WND_SUPERCLASS makrolarını kullanmanın yanı sıra, `GetWndClassInfo` kendi uygulamanız ile geçersiz kılabilirsiniz.

##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl:: m_pfnSuperWindowProc

Pencereye bağlı olarak, aşağıdaki pencere yordamlarından birini işaret eder.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Açıklamalar

|Pencere türü|Pencere yordamı|
|--------------------|----------------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu aracılığıyla belirtilen yeni bir pencere sınıfına dayalı bir pencere.|[DefWindowProc](/windows/win32/api/winuser/nf-winuser-defwindowprocw) Win32 işlevi.|
|[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosu aracılığıyla belirtilen mevcut bir sınıfı değiştiren pencere sınıfına dayalı bir pencere.|Varolan pencere sınıfının pencere yordamı.|
|Alt sınıflı pencere.|Alt sınıflı pencerenin özgün pencere yordamı.|

[CWindowImpl::D efWindowProc](#defwindowproc) , `m_pfnSuperWindowProc`kayıtlı pencere yordamına ileti bilgilerini gönderir.

##  <a name="onfinalmessage"></a>CWindowImpl:: OnFinalMessage

Son iletiyi aldıktan sonra çağırılır (genellikle WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Yok edilecek pencere için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

`OnFinalMessage` varsayılan uygulanması hiçbir şey yapmaz, ancak pencereyi yok etmeden önce temizlemeyi işlemek için bu işlevi geçersiz kılabilirsiniz. Nesneyi pencere yok etme sonrasında otomatik olarak silmek istiyorsanız, bu işlevde **Sil** ' i çağırabilirsiniz.

##  <a name="subclasswindow"></a>CWindowImpl:: SubclassWindow

*HWND* tarafından tanımlanan pencerenin alt sınıfları ve `CWindowImpl` nesnesine iliştirir.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Alt sınıflandırılacak pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla alt sınıflandırdıysanız doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Alt sınıflı pencere artık [CWindowImpl:: WindowProc](#windowproc)kullanır. Özgün pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir.

> [!NOTE]
>  Zaten [Oluştur](#create)olarak adlandırdıysanız `SubclassWindow` çağırmayın.

##  <a name="unsubclasswindow"></a>CWindowImpl:: UnsubclassWindow

`CWindowImpl` nesnesinden alt sınıflı pencereyi ayırır ve özgün pencere yordamını [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir ve geri yükler.

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Pencerenin daha önce alt sınıflandırılacak olan işleyici.

##  <a name="windowproc"></a>CWindowImpl:: WindowProc

Bu statik işlev pencere yordamını uygular.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Pencerenin tutamacı.

*uMsg*<br/>
'ndaki Pencereye gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu.

### <a name="remarks"></a>Açıklamalar

`WindowProc`, iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini ( [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen) kullanır. Gerekirse, ek ileti işleme için `WindowProc` [DefWindowProc](#defwindowproc) çağırır. Son ileti işlenmezse, aşağıdakileri `WindowProc`:

- Pencere alt sınıflandırdıysa unsubclassing gerçekleştirir.

- `m_hWnd`temizler.

- Pencere yok edildiğinde [OnFinalMessage](#onfinalmessage) çağırır.

İletileri işlemeye yönelik farklı bir mekanizma sağlamak için `WindowProc` geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
