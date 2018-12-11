---
title: Cdialogımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
ms.openlocfilehash: b4844ed2246b5e700d9dc1895c3292cdde4efe8b
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178154"
---
# <a name="cdialogimpl-class"></a>Cdialogımpl sınıfı

Bu sınıf, kalıcı veya geçici bir iletişim kutusu oluşturmak için yöntemleri sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `CDialogImpl`.

*Ttemel*<br/>
Yeni sınıfın temel sınıf. Varsayılan temel sınıf [CWindow](../../atl/reference/cwindow-class.md).

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Oluşturma](#create)|Modsuz iletişim kutusu oluşturur.|
|[DestroyWindow](#destroywindow)|Kalıcı olmayan iletişim kutusunu yok eder.|
|[DoModal](#domodal)|Kalıcı bir iletişim kutusu oluşturur.|
|[EndDialog](#enddialog)|Kalıcı bir iletişim kutusu yok eder.|

### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT yöntemleri

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Geçerli iletişim kutusu yordamını döndürür.|
|[MapDialogRect](#mapdialogrect)|Belirtilen dikdörtgenin iletişim kutusu birimleri (piksel) ekran birimine eşler.|
|[OnFinalMessage](#onfinalmessage)|Genellikle WM_NCDESTROY son iletiyi aldıktan sonra çağrılır.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[DialogProc](#dialogproc)|İletişim kutusuna gönderilen iletileri işler.|
|[StartDialogProc](#startdialogproc)|İletişim kutusuna gönderilen iletileri işlemek için ilk ileti alındığında çağrılır.|

## <a name="remarks"></a>Açıklamalar

İle `CDialogImpl` kalıcı veya geçici bir iletişim kutusu oluşturabilirsiniz. `CDialogImpl` uygun işleyicileri iletilerini yönlendirmek için varsayılan ileti eşlemesi kullanan iletişim kutusu yordam sağlar.

Temel sınıf yok edicisini `~CWindowImplRoot` pencere nesnesi yok etme öncesinde gittiğini sağlar.

`CDialogImpl` öğesinden türetilen `CDialogImplBaseT`, hangi sırayla türetilir `CWindowImplRoot`.

> [!NOTE]
>  Sınıfınıza tanımlamalıdır bir `IDD` iletişim şablonu kaynak kimliğini belirtir. üye Örneğin, ATL Proje Sihirbazı otomatik olarak sınıfınıza aşağıdaki satırı ekler:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

Burada `MyDlg` olduğu **kısa ad** Sihirbazı'nda kişinin girilen **adları** sayfası.

|Daha fazla bilgi|Bkz. |
|--------------------------------|---------|
|Denetimler oluşturma|[ATL öğretici](../../atl/active-template-library-atl-tutorial.md)|
|ATL iletişim kutuları kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|
|ATL projesi Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|
|İletişim kutuları|[İletişim kutuları](/windows/desktop/dlgbox/dialog-boxes) ve sonraki konularda Windows SDK'sı|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="create"></a>  CDialogImpl::Create

Modsuz iletişim kutusu oluşturur.

```
HWND Create(
    HWND hWndParent,
    LPARAM dwInitParam = NULL );

HWND Create(
    HWND hWndParent,
    RECT&,
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
[in] İşleci sahip penceresine.

**RECT &** *rect* [in] A [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Yapısı iletişim kutusunun boyutunu ve konumunu belirtme.

*dwInitParam*<br/>
[in] İletişim kutusundaki geçirmek için bir değer belirtir *lParam* WM_INITDIALOG iletisinin parametresi.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan bir iletişim kutusu için tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu otomatik olarak bağlı `CDialogImpl` nesne. Kalıcı bir iletişim kutusu oluşturmak için arama [DoModal](#domodal). Yalnızca Yukarıdaki ikinci geçersiz kılma kullanılan [CComControl](../../atl/reference/ccomcontrol-class.md).

##  <a name="destroywindow"></a>  CDialogImpl::DestroyWindow

Kalıcı olmayan iletişim kutusunu yok eder.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu başarıyla silindi TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

İletişim kutusunu yok edildi başarıyla TRUE döndürür; Aksi durumda FALSE.

##  <a name="dialogproc"></a>  CDialogImpl::DialogProc

Bu statik işlev iletişim kutusu yordamını uygular.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
[in] İletişim kutusu için tanıtıcı.

*uMsg*<br/>
[in] İletişim kutusuna gönderilen ileti.

*wParam*<br/>
[in] İletiye özgü ek bilgiler.

*lParam*<br/>
[in] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işleme TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`DialogProc` uygun işleyicileri iletilerini yönlendirmek için varsayılan ileti eşlemesi kullanır.

Geçersiz kılabilirsiniz `DialogProc` iletileri işlemek için farklı bir mekanizma sağlamak için.

##  <a name="domodal"></a>  CDialogImpl::DoModal

Kalıcı bir iletişim kutusu oluşturur.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
[in] İşleci sahip penceresine. Varsayılan değer dönüş değeri [GetActiveWindow](/windows/desktop/api/winuser/nf-winuser-getactivewindow) Win32 işlevi.

*dwInitParam*<br/>
[in] İletişim kutusundaki geçirmek için bir değer belirtir *lParam* WM_INITDIALOG iletisinin parametresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, değerini *nRetCode* yapılan çağrıda belirtilen parametre [EndDialog](#enddialog). Aksi durumda, -1.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu otomatik olarak bağlı `CDialogImpl` nesne.

Modsuz iletişim kutusu oluşturmak için arama [Oluştur](#create).

##  <a name="enddialog"></a>  CDialogImpl::EndDialog

Kalıcı bir iletişim kutusu yok eder.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
[in] Tarafından döndürülen değer [CDialogImpl::DoModal](#domodal).

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusunu yok TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

`EndDialog` iletişim yordam boyunca çağrılmalıdır. İletişim kutusunu yok sonra Windows değerini kullanır. *nRetCode* dönüş değeri olarak `DoModal`, iletişim kutusu oluşturulur.

> [!NOTE]
>  Çağırmayın `EndDialog` modsuz iletişim kutusu yok edilemiyor. Çağrı [CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow) yerine.

##  <a name="getdialogproc"></a>  CDialogImpl::GetDialogProc

Döndürür `DialogProc`, geçerli iletişim kutusu yordamını.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli iletişim kutusunu yordam.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu yordamını sizinkiyle değiştirmek için bu yöntemi yok sayın.

##  <a name="mapdialogrect"></a>  CDialogImpl::MapDialogRect

(Maps) belirtilen dikdörtgen ekran için iletişim kutusu ölçü birimleri (piksel) dönüştürür.

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir `CRect` nesne veya [RECT](/windows/desktop/api/windef/ns-windef-tagrect) güncelleştirme bölgeyi kapsayan güncelleştirme istemci koordinatlarını almak için yapısı.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirme başarılı olursa sıfır dışı; güncelleştirme başarısız olursa 0. Genişletilmiş hata bilgilerini almak için arama `GetLastError`.

### <a name="remarks"></a>Açıklamalar

İşlev koordinatlarında belirtilen değiştirir `RECT` yapısı dönüştürülmüş koordinatlarıyla olanak sağlayan bir iletişim kutusu oluşturmak veya bir denetimi içinde bir iletişim kutusu konum için kullanılacak yapı.

##  <a name="onfinalmessage"></a>  CDialogImpl::OnFinalMessage

Son ileti alındıktan sonra çağırılır (genellikle `WM_NCDESTROY`).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
[in] Yok ediliyor penceresi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Pencere yok etme sırasında nesne otomatik olarak silmek istiyorsanız, çağırabilirsiniz unutmayın **; bunu silin** burada.

##  <a name="startdialogproc"></a>  CDialogImpl::StartDialogProc

İlk ileti alındığında iletişim kutusuna gönderilen iletileri işlemek için yalnızca bir kez çağrılır.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*hWnd*<br/>
[in] İletişim kutusu için tanıtıcı.

*uMsg*<br/>
[in] İletişim kutusuna gönderilen ileti.

*wParam*<br/>
[in] İletiye özgü ek bilgiler.

*lParam*<br/>
[in] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

Pencere yordamı.

### <a name="remarks"></a>Açıklamalar

İlk çağrısından sonra `StartDialogProc`, `DialogProc` iletişim yordamı ve ek çağrıları vardır kullandıkça ayarlanmış.

## <a name="see-also"></a>Ayrıca Bkz.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)