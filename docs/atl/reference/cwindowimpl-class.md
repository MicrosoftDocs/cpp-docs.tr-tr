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
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496194"
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

*ŞI*<br/>
Yeni sınıfınız, öğesinden `CWindowImpl`türetilir.

*TBase*<br/>
Sınıfınızın temel sınıfı. Varsayılan olarak, temel sınıf [CWindow](../../atl/reference/cwindow-class.md)olur.

*TWinTraits*<br/>
Pencerenize yönelik stilleri tanımlayan bir [nitelikler sınıfı](../../atl/understanding-window-traits.md) . Varsayılan, `CControlWinTraits` değeridir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
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

Bir pencere oluşturmak `CWindowImpl` veya var olan bir pencerenin alt sınıfını oluşturmak için kullanabilirsiniz. pencere `CWindowImpl` yordamı, iletileri uygun işleyicilere yönlendirmek için bir ileti eşlemesi kullanır.

`CWindowImpl::Create`[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)tarafından yönetilen pencere sınıfı bilgilerine dayalı bir pencere oluşturur. `CWindowImpl`[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosunu içerir, bu da yeni `CWndClassInfo` bir pencere sınıfını kaydeder anlamına gelir. Varolan bir pencere sınıfını üst sınıfa eklemek istiyorsanız, sınıfınızı `CWindowImpl` sınıfından türetebilir ve [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu ekleyin. Bu durumda, var `CWndClassInfo` olan bir sınıfı temel alan, ancak kullanan `CWindowImpl::WindowProc`bir pencere sınıfını kaydeder. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
>  Yalnızca bir pencere sınıfının bilgilerini `CWindowImpl` yönettiğiiçin,birörneğiaracılığıylaoluşturulanherpencereaynıpenceresınıfınadayalıdır.`CWndClassInfo`

`CWindowImpl`Ayrıca Window altsınıflama 'ı destekler. Yöntemi, `CWindowImpl` nesnesine varolan bir pencere iliştirir ve pencere yordamını olarak `CWindowImpl::WindowProc`değiştirir. `SubclassWindow` Her bir örneği `CWindowImpl` farklı bir pencerenin alt sınıfını oluşturabilir.

> [!NOTE]
>  Verilen `CWindowImpl` herhangi bir nesne için ya da `Create` veya `SubclassWindow`' ı çağırın. Aynı nesne üzerinde her iki yöntemi çağırmayın.

Ayrıca `CWindowImpl`, ATL, başka bir nesnede bulunan bir pencere oluşturmak için [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) sağlar.

Temel sınıf yıkıcısı (~ `CWindowImplRoot`), nesne yok etmeden önce pencerenin kaybolmasını sağlar.

`CWindowImpl`, ve CMessageMap öğesinden türetilen öğesinden türetilir. [](../../atl/reference/cmessagemap-class.md) `CWindowImplBaseT` `CWindowImplRoot` `TBase`

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
'ndaki Pencerenin konumunu belirten bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısı. , `RECT` İşaretçi veya başvuru ile geçirilebilir.

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

`Create`İlk olarak, henüz kayıtlı değilse pencere sınıfını kaydeder. Yeni oluşturulan pencere, `CWindowImpl` nesnesine otomatik olarak eklenir.

> [!NOTE]
>  Zaten SubclassWindow olarak `Create` adlandırdıysanız çağırmayın. [](#subclasswindow)

Varolan bir pencere sınıfını temel alan bir pencere sınıfını kullanmak için, sınıfınızı `CWindowImpl` sınıfından türetebilir ve [declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosunu ekleyin. Mevcut pencere sınıfının pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)' ye kaydedilir. Daha fazla bilgi için bkz. [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 'ye genel bakış.

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

Varsayılan olarak, `DefWindowProc` ileti bilgilerini [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)içinde belirtilen pencere yordamına göndermek için [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 işlevini çağırır.

Parametresi olmayan işlevi, geçerli iletiden gerekli parametreleri otomatik olarak alır.

##  <a name="getcurrentmessage"></a>CWindowImpl:: GetCurrentMessage

`MSG` Yapıda paketlenmiş geçerli iletiyi döndürür.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ileti.

##  <a name="getwindowproc"></a>CWindowImpl:: GetWindowProc

Geçerli `WindowProc`pencere yordamını döndürür.

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

Varsayılan olarak, `CWindowImpl` bu yöntemi yeni bir pencere sınıfını belirten [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu aracılığıyla edinir.

Varolan bir pencere sınıfını üst sınıfa eklemek için, sınıfınızı öğesinden `CWindowImpl` türetirsiniz ve [](window-class-macros.md#declare_wnd_superclass) geçersiz kılmak `GetWndClassInfo`için declare_wnd_superclass makrosunu ekleyin. Daha fazla bilgi için bkz. [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 'ye genel bakış.

Declare_wnd_class ve declare_wnd_superclass makrolarını kullanmanın yanı sıra, kendi uygulamanız ile `GetWndClassInfo` geçersiz kılabilirsiniz.

##  <a name="m_pfnsuperwindowproc"></a>CWindowImpl:: m_pfnSuperWindowProc

Pencereye bağlı olarak, aşağıdaki pencere yordamlarından birini işaret eder.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Açıklamalar

|Pencere türü|Pencere yordamı|
|--------------------|----------------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu aracılığıyla belirtilen yeni bir pencere sınıfına dayalı bir pencere.|[DefWindowProc](/windows/win32/api/winuser/nf-winuser-defwindowprocw) Win32 işlevi.|
|[Declare_wnd_superclass](window-class-macros.md#declare_wnd_superclass) makrosu aracılığıyla belirtilen varolan bir sınıfı değiştiren pencere sınıfına dayalı bir pencere.|Varolan pencere sınıfının pencere yordamı.|
|Alt sınıflı pencere.|Alt sınıflı pencerenin özgün pencere yordamı.|

[CWindowImpl::D efWindowProc](#defwindowproc) , ileti bilgilerini kaydedilen `m_pfnSuperWindowProc`pencere yordamına gönderir.

##  <a name="onfinalmessage"></a>CWindowImpl:: OnFinalMessage

Son iletiyi aldıktan sonra çağırılır (genellikle WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Yok edilecek pencere için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulamasının `OnFinalMessage` hiçbir şey yapmaz, ancak pencereyi yok etmeden önce temizlemeyi işlemek için bu işlevi geçersiz kılabilirsiniz. Nesneyi pencere yok etme sonrasında otomatik olarak silmek istiyorsanız, bu işlevde **Sil** ' i çağırabilirsiniz.

##  <a name="subclasswindow"></a>CWindowImpl:: SubclassWindow

*HWND* tarafından tanımlanan pencerenin alt sınıfları ve `CWindowImpl` nesneye iliştirir.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Alt sınıflandırılacak pencerenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla alt sınıflandırdıysanız doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Alt sınıflı pencere artık [CWindowImpl:: WindowProc](#windowproc)kullanır. Özgün pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)' ye kaydedilir.

> [!NOTE]
>  Zaten oluştur olarak `SubclassWindow` adlandırdıysanız çağırmayın. [](#create)

##  <a name="unsubclasswindow"></a>CWindowImpl:: UnsubclassWindow

Alt sınıflı pencereyi `CWindowImpl` nesneden ayırır ve özgün pencere yordamını [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)' ye kaydedilir.

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

`WindowProc`, iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini ( [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile belirtilen) kullanır. Gerekirse, `WindowProc` ek ileti işleme için [DefWindowProc](#defwindowproc) çağırır. Son ileti işlenmezse, `WindowProc` şunları yapar:

- Pencere alt sınıflandırdıysa unsubclassing gerçekleştirir.

- Temizler `m_hWnd`.

- Pencere yok edildiğinde [OnFinalMessage](#onfinalmessage) çağırır.

İletileri işlemeye yönelik `WindowProc` farklı bir mekanizma sağlamak için geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
