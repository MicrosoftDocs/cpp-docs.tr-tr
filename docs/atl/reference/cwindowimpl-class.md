---
title: CWindowImpl Sınıfı
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
ms.openlocfilehash: d7f7f7363eb123181bd6e0389663810346094cba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330290"
---
# <a name="cwindowimpl-class"></a>CWindowImpl Sınıfı

Pencere oluşturma veya alt sınıflandırma yöntemleri sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yeni sınıfınızdan `CWindowImpl`türetilmiştir.

*TBase*<br/>
Sınıfının taban sınıfı. Varsayılan olarak, taban sınıf [CWindow'dur.](../../atl/reference/cwindow-class.md)

*TwinTraits*<br/>
Pencerenizin stillerini tanımlayan [özellikler sınıfı.](../../atl/understanding-window-traits.md) Varsayılan değer: `CControlWinTraits`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWindowImpl::Oluştur](#create)|Bir pencere oluşturur.|

### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT Yöntemleri

|||
|-|-|
|[DefWindowProc](#defwindowproc)|Varsayılan ileti işleme sağlar.|
|[Güncel Mesajı Alma](#getcurrentmessage)|Geçerli iletiyi döndürür.|
|[GetWindowProc](#getwindowproc)|Geçerli pencere yordamını döndürür.|
|[OnFinalMessage](#onfinalmessage)|Son ileti alındıktan sonra çağrılır (genellikle WM_NCDESTROY).|
|[Subclasswindow](#subclasswindow)|Alt sınıflar bir pencere.|
|[UnsubclassWindow](#unsubclasswindow)|Daha önce alt sınıflanmış bir pencereyi geri yükler.|

### <a name="static-methods"></a>Statik Yöntemler

|||
|-|-|
|[GetWndClassInfo](#getwndclassinfo)|Pencere sınıfı bilgilerini yöneten [CWndClassInfo'nun](../../atl/reference/cwndclassinfo-class.md)statik bir örneğini döndürür.|
|[Windowproc](#windowproc)|Pencereye gönderilen iletileri işler.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|Pencere sınıfının özgün pencere yordamını işaret eder.|

## <a name="remarks"></a>Açıklamalar

Bir pencere `CWindowImpl` oluşturmak veya varolan bir pencereyi alt sınıflamak için kullanabilirsiniz. pencere `CWindowImpl` yordamı, iletileri uygun işleyicilere yönlendirmek için bir ileti eşlemi kullanır.

`CWindowImpl::Create`[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)tarafından yönetilen pencere sınıfı bilgilerini temel alan bir pencere oluşturur. `CWindowImpl`[yeni](window-class-macros.md#declare_wnd_class) bir pencere sınıfı `CWndClassInfo` kaydeder anlamına gelir DECLARE_WND_CLASS makro içerir. Varolan bir pencere sınıfını üst sınıfa çıkarmak `CWindowImpl` istiyorsanız, sınıfınızı türetin ve [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makroyu ekleyin. Bu durumda, `CWndClassInfo` varolan bir sınıfa dayalı ancak kullanan `CWindowImpl::WindowProc`bir pencere sınıfı kaydeder. Örneğin:

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]

> [!NOTE]
> Bilgileri `CWndClassInfo` yalnızca bir pencere sınıfının yönettiğinden, bir örnek `CWindowImpl` üzerinden oluşturulan her pencere aynı pencere sınıfına dayanır.

`CWindowImpl`pencere alt sınıflandırmayı da destekler. Yöntem `SubclassWindow` nesneye `CWindowImpl` varolan bir pencere bağlar ve `CWindowImpl::WindowProc`pencere yordamını . Her örneği `CWindowImpl` farklı bir pencere alt sınıfolabilir.

> [!NOTE]
> Belirli bir `CWindowImpl` nesne için, `SubclassWindow`ya da `Create` . Her iki yöntemi de aynı nesne üzerinde çağırmayın.

Buna ek `CWindowImpl`olarak, ATL başka bir nesnede bulunan bir pencere oluşturmak için [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) sağlar.

Temel sınıf yıkıcı (~ `CWindowImplRoot`) nesne yok edilmeden önce pencerenin gittiğinden emin olur.

`CWindowImpl`türetilmiştir `CWindowImplBaseT`, hangi türetilmiştir `CWindowImplRoot`, hangi `TBase` türetilmiştir ve [CMessageMap](../../atl/reference/cmessagemap-class.md).

|Daha fazla bilgi|Bkz.|
|--------------------------------|---------|
|Denetim oluşturma|[ATL Öğretici](../../atl/active-template-library-atl-tutorial.md)|
|ATL'de pencereleri kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmessagemap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CWindowImplBaseT`

`CWindowImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cwindowimplcreate"></a><a name="create"></a>CWindowImpl::Oluştur

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

*hWndParent*<br/>
[içinde] Üst veya sahip penceresine tanıtıcı.

*Rect*<br/>
[içinde] Pencerenin konumunu belirten bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısı. İşaretçi `RECT` veya başvuru ile geçirilebilir.

*szWindowName*<br/>
[içinde] Pencerenin adını belirtir. Varsayılan değer NULL'dur.

*Dwstyle*<br/>
[içinde] Pencerenin stili. Bu değer, pencere nin özellikleri sınıfı tarafından sağlanan stil ile birleştirilir. Varsayılan değer, özellikler sınıfına stil üzerinde tam denetim sağlar. Olası değerlerin listesi için Windows SDK'daki [Create Window'a](/windows/win32/api/winuser/nf-winuser-createwindoww) bakın.

*dwExStyle*<br/>
[içinde] Genişletilmiş pencere stili. Bu değer, pencere nin özellikleri sınıfı tarafından sağlanan stil ile birleştirilir. Varsayılan değer, özellikler sınıfına stil üzerinde tam denetim sağlar. Olası değerlerin listesi için Windows SDK'daki [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) bölümüne bakın.

*MenuOrID*<br/>
[içinde] Bir alt pencere için, pencere tanımlayıcısı. Üst düzey bir pencere için, pencere için bir menü tutamacı. Varsayılan değer **0U'dur.**

*lpCreateParam*<br/>
[içinde] Pencere oluşturma verileri için bir işaretçi. Tam bir açıklama için [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)için son parametrenin açıklamasına bakın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, yeni oluşturulan pencerenin tutamacı. Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

`Create`henüz kaydedilmemişse, önce pencere sınıfını kaydeder. Yeni oluşturulan pencere nesneye `CWindowImpl` otomatik olarak eklenir.

> [!NOTE]
> `Create` [SubclassWindow'u](#subclasswindow)zaten aradıysanız aramayın.

Varolan bir pencere sınıfını temel alan bir pencere sınıfı `CWindowImpl` kullanmak için, sınıfınızı türetin ve [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makroyu ekleyin. Varolan pencere sınıfının pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir. Daha fazla bilgi için [CWindowImpl](../../atl/reference/cwindowimpl-class.md) genel bakış ına bakın.

> [!NOTE]
> *MenuOrID* parametresi için değer olarak 0 kullanılırsa, derleyici hatasını önlemek için 0U (varsayılan değer) olarak belirtilmelidir.

## <a name="cwindowimpldefwindowproc"></a><a name="defwindowproc"></a>CWindowImpl::DefWindowProc

İleti haritası tarafından işlenmemiş iletileri işlemek için [WindowProc](#windowproc) tarafından çağrılır.

```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```

### <a name="parameters"></a>Parametreler

*uMsg*<br/>
[içinde] Pencereye gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `DefWindowProc` [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)belirtilen pencere yordamına ileti bilgilerini göndermek için [CallWindowProc](/windows/win32/api/winuser/nf-winuser-callwindowprocw) Win32 işlevini çağırır.

Parametreleri olmayan işlev, gerekli parametreleri geçerli iletiden otomatik olarak alır.

## <a name="cwindowimplgetcurrentmessage"></a><a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage

`MSG` Yapıda paketlenmiş geçerli iletiyi döndürür.

```
const MSG* GetCurrentMessage();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli ileti.

## <a name="cwindowimplgetwindowproc"></a><a name="getwindowproc"></a>CWindowImpl::GetWindowProc

Döndürür `WindowProc`, geçerli pencere yordamı.

```
virtual WNDPROC GetWindowProc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli pencere yordamı.

### <a name="remarks"></a>Açıklamalar

Pencere yordamını kendi yordamınızla değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cwindowimplgetwndclassinfo"></a><a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo

Pencere sınıfı bilgilerine erişmek için [Create](#create) tarafından çağrılır.

```
static CWndClassInfo& GetWndClassInfo();
```

### <a name="return-value"></a>Dönüş Değeri

[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)statik bir örnek .

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `CWindowImpl` bu yöntemi yeni bir pencere sınıfı belirten [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makro suyla elde eder.

Varolan bir pencere sınıfını üst sınıfa sınıflamak için, `GetWndClassInfo`sınıfınızı türetin `CWindowImpl` ve geçersiz kılmak için [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makroyu ekleyin. Daha fazla bilgi için [CWindowImpl](../../atl/reference/cwindowimpl-class.md) genel bakış ına bakın.

DECLARE_WND_CLASS ve DECLARE_WND_SUPERCLASS makroları kullanmanın yanı `GetWndClassInfo` sıra, kendi uygulamanızla geçersiz kılınabilirsiniz.

## <a name="cwindowimplm_pfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc

Pencereye bağlı olarak, aşağıdaki pencere yordamlarından birini işaret eder.

```
WNDPROC m_pfnSuperWindowProc;
```

### <a name="remarks"></a>Açıklamalar

|Pencere türü|Pencere yordamı|
|--------------------|----------------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) makrosu ile belirtilen yeni bir pencere sınıfına dayalı bir pencere.|[DefWindowProc](/windows/win32/api/winuser/nf-winuser-defwindowprocw) Win32 işlevi.|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) makrosu ile belirtilen varolan bir sınıfı değiştiren bir pencere sınıfına dayalı bir pencere.|Varolan pencere sınıfının pencere yordamı.|
|Alt sınıflı bir pencere.|Alt sınıflı pencerenin özgün pencere yordamı.|

[CWindowImpl::DefWindowProc](#defwindowproc) kaydedilen pencere yordamına `m_pfnSuperWindowProc`ileti bilgileri gönderir.

## <a name="cwindowimplonfinalmessage"></a><a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage

Son iletiyi aldıktan sonra çağrılır (genellikle WM_NCDESTROY).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Yıkılan pencerenin sapı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama `OnFinalMessage` hiçbir şey yapmaz, ancak bir pencereyi yok etmeden önce temizleme işlemek için bu işlevi geçersiz kılabilirsiniz. Pencere imhası üzerine nesnenizi otomatik olarak silmek istiyorsanız, bu işlevde **sil'i** arayabilirsiniz.

## <a name="cwindowimplsubclasswindow"></a><a name="subclasswindow"></a>CWindowImpl::Alt SınıfPenceresi

*HWnd* tarafından tanımlanan pencereyi alt sınıflar `CWindowImpl` ve nesneye bağlar.

```
BOOL SubclassWindow(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Pencerenin tutamacı alt sınıflandı.

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla alt sınıflanmışsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Alt sınıflı pencere şimdi [CWindowImpl kullanır::WindowProc](#windowproc). Özgün pencere yordamı [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilir.

> [!NOTE]
> Oluştur'u `SubclassWindow` zaten aradıysanız [Create](#create)aramayın.

## <a name="cwindowimplunsubclasswindow"></a><a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow

Alt sınıflanmış pencereyi `CWindowImpl` nesneden ayırır ve [m_pfnSuperWindowProc](#m_pfnsuperwindowproc)kaydedilen özgün pencere yordamını geri yükler.

```
HWND UnsubclassWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Pencerenin tutamacı daha önce alt sınıflanmış.

## <a name="cwindowimplwindowproc"></a><a name="windowproc"></a>CWindowImpl::WindowProc

Bu statik işlev pencere yordamını uygular.

```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Pencerenin sapı.

*uMsg*<br/>
[içinde] Pencereye gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu.

### <a name="remarks"></a>Açıklamalar

`WindowProc`iletileri ilgili işleyicilere yönlendirmek için varsayılan ileti eşlemi [(BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)ile birlikte bildirilir) kullanır. Gerekirse, `WindowProc` ek ileti işleme için [DefWindowProc'u](#defwindowproc) arar. Son ileti işlenmezse, `WindowProc` aşağıdakileri yapar:

- Pencere alt sınıflanmamışsa alt sınıflandırma gerçekleştirir.

- Temizler. `m_hWnd`

- Pencere yok edilmeden önce [OnFinalMessage'ı](#onfinalmessage) çağırır.

İletileri işlemek `WindowProc` için farklı bir mekanizma sağlamak için geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Begın_msg_map](message-map-macros-atl.md#begin_msg_map)<br/>
[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
