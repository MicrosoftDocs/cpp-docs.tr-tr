---
title: CDialogImpl sınıfı
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
ms.openlocfilehash: bc39a5deeb270b0426a4b199fc9ba01917c292bc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496808"
---
# <a name="cdialogimpl-class"></a>CDialogImpl sınıfı

Bu sınıf, kalıcı veya kalıcı olmayan iletişim kutusu oluşturmak için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `CDialogImpl`türetilir.

*TBase*<br/>
Yeni sınıfınızın temel sınıfı. Varsayılan temel sınıf [CWindow](../../atl/reference/cwindow-class.md)' dır.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Oluşturma](#create)|Kalıcı olmayan iletişim kutusu oluşturur.|
|[DestroyWindow](#destroywindow)|Kalıcı olmayan iletişim kutusunu yok eder.|
|[DoModal](#domodal)|Kalıcı bir iletişim kutusu oluşturur.|
|[EndDialog](#enddialog)|Kalıcı iletişim kutusunu yok eder.|

### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT yöntemleri

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Geçerli iletişim kutusu yordamını döndürür.|
|[MapDialogRect](#mapdialogrect)|Belirtilen dikdörtgenin iletişim kutusu birimlerini ekran birimlerine (piksel) eşler.|
|[OnFinalMessage](#onfinalmessage)|Son iletiyi aldıktan sonra çağırılır, genellikle WM_NCDESTROY.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[DialogProc](#dialogproc)|İletişim kutusuna gönderilen iletileri işler.|
|[StartDialogProc](#startdialogproc)|İletişim kutusuna gönderilen iletileri işlemek için ilk ileti alındığında çağırılır.|

## <a name="remarks"></a>Açıklamalar

İle `CDialogImpl` , kalıcı veya kalıcı olmayan bir iletişim kutusu oluşturabilirsiniz. `CDialogImpl`iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanan iletişim kutusu yordamını sağlar.

Taban sınıf yok edicisi `~CWindowImplRoot` , bir nesneyi yok etmeden önce pencerenin kaybolmasını sağlar.

`CDialogImpl`öğesinden türetilir `CWindowImplRoot`ve ' den türetilir. `CDialogImplBaseT`

> [!NOTE]
>  Sınıfınız, iletişim kutusu şablonu `IDD` kaynak kimliğini belirten bir üye tanımlamalıdır. Örneğin, ATL Proje Sihirbazı, sınıfınıza aşağıdaki satırı otomatik olarak ekler:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

Burada `MyDlg` sihirbazın **adlar** sayfasına girilen **kısa addır** .

|Daha fazla bilgi|Bkz.|
|--------------------------------|---------|
|Denetimler oluşturma|[ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md)|
|ATL 'de iletişim kutularını kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|
|İletişim kutuları|Windows SDK [Iletişim kutuları](/windows/win32/dlgbox/dialog-boxes) ve sonraki konular|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="create"></a>CDialogImpl:: Create

Kalıcı olmayan iletişim kutusu oluşturur.

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
'ndaki Sahip penceresi için tanıtıcı.

**RECT &** *Rect* 'ndaki İletişim kutusunun boyutunu ve konumunu belirten bir [Rect](/previous-versions/dd162897\(v=vs.85\)) yapısı.

*dwInitParam*<br/>
'ndaki WM_INITDIALOG iletisinin *lParam* parametresindeki iletişim kutusuna geçirilecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iletişim kutusunun tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu `CDialogImpl` nesneye otomatik olarak eklenir. Kalıcı bir iletişim kutusu oluşturmak için [DoModal](#domodal)' ı çağırın. Yukarıdaki ikinci geçersiz kılma yalnızca [CComControl](../../atl/reference/ccomcontrol-class.md)ile kullanılır.

##  <a name="destroywindow"></a>CDialogImpl::D estroyWindow

Kalıcı olmayan iletişim kutusunu yok eder.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu başarıyla iptal edildiğinde doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu başarıyla iptal edildiğinde doğru döndürür; Aksi halde yanlış.

##  <a name="dialogproc"></a>CDialogImpl::D ıalogproc

Bu statik işlev iletişim kutusu yordamını uygular.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki İletişim kutusunun tutamacı.

*uMsg*<br/>
'ndaki İletişim kutusuna gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işlendiyse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

`DialogProc`, iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanır.

İletileri işlemeye yönelik `DialogProc` farklı bir mekanizma sağlamak için geçersiz kılabilirsiniz.

##  <a name="domodal"></a>CDialogImpl::D oModal

Kalıcı bir iletişim kutusu oluşturur.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
'ndaki Sahip penceresi için tanıtıcı. Varsayılan değer, [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) Win32 işlevinin dönüş değeridir.

*dwInitParam*<br/>
'ndaki WM_INITDIALOG iletisinin *lParam* parametresindeki iletişim kutusuna geçirilecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, [EndDialog](#enddialog)çağrısında belirtilen *nekcode* parametresinin değeri. Aksi takdirde,-1.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu `CDialogImpl` nesneye otomatik olarak eklenir.

Kalıcı olmayan bir iletişim kutusu oluşturmak için [Oluştur](#create)' u çağırın.

##  <a name="enddialog"></a>CDialogImpl:: EndDialog

Kalıcı iletişim kutusunu yok eder.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parametreler

*Nekcode*<br/>
'ndaki [Cdialogimpl::D oModal](#domodal)tarafından döndürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu yok edildiğinde doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

`EndDialog`iletişim kutusu yordamı aracılığıyla çağrılmalıdır. İletişim kutusu yok edildikten sonra, Windows, iletişim kutusunu oluşturan için `DoModal`dönüş değeri olarak *nekcode* değerini kullanır.

> [!NOTE]
>  Kalıcı olmayan iletişim `EndDialog` kutusunu yok etme çağrısı yapın. Bunu çağırın: bunun yerine [estroyWindow:D](../../atl/reference/cwindow-class.md#destroywindow) .

##  <a name="getdialogproc"></a>CDialogImpl:: GetDialogProc

Geçerli `DialogProc`iletişim kutusu yordamını döndürür.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli iletişim kutusu yordamı.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu yordamını kendi kendinize değiştirmek için bu yöntemi geçersiz kılın.

##  <a name="mapdialogrect"></a>CDialogImpl:: MapDialogRect

Belirtilen dikdörtgenin iletişim kutusu birimlerini ekran birimlerine (piksel) dönüştürür (eşler).

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
Güncelleştirme bölgesini kapsayan `CRect` güncelleştirmenin istemci koordinatlarını alacak bir nesne veya [Rect](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirme başarılı olursa sıfır dışı; güncelleştirme başarısız olursa 0. Genişletilmiş hata bilgilerini almak için çağrısı `GetLastError`yapın.

### <a name="remarks"></a>Açıklamalar

İşlevi, belirtilen `RECT` yapıda koordinatları, bir iletişim kutusu oluşturmak veya bir denetimi iletişim kutusu içinde konumlandırmak için kullanılmasına izin veren dönüştürülmüş koordinatlarla değiştirir.

##  <a name="onfinalmessage"></a>CDialogImpl:: OnFinalMessage

Son iletiyi aldıktan sonra çağırılır (genellikle `WM_NCDESTROY`).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki Yok edilecek pencere için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Nesneyi pencere yok etme sonrasında otomatik olarak silmek istiyorsanız, **bunu Sil** ' i çağırabilirsiniz.

##  <a name="startdialogproc"></a>CDialogImpl:: StartDialogProc

İlk ileti alındığında, iletişim kutusuna gönderilen iletileri işlemek için yalnızca bir kez çağırılır.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*lendiği*<br/>
'ndaki İletişim kutusunun tutamacı.

*uMsg*<br/>
'ndaki İletişim kutusuna gönderilen ileti.

*wParam*<br/>
'ndaki İletiye özgü ek bilgiler.

*lParam*<br/>
'ndaki İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

Pencere yordamı.

### <a name="remarks"></a>Açıklamalar

İlk çağrısından `StartDialogProc`sonra, `DialogProc` bir iletişim kutusu yordamı olarak ayarlanır ve daha fazla çağrı buraya gider.

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
