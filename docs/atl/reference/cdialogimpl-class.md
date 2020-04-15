---
title: CDialogImpl Sınıfı
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
ms.openlocfilehash: 900a312c97d7b83eac93a372be39a006b3c4344d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327059"
---
# <a name="cdialogimpl-class"></a>CDialogImpl Sınıfı

Bu sınıf, modal veya modeless iletişim kutusu oluşturmak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,
    class TBase = CWindow>
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CDialogImpl`türetilmiştir.

*TBase*<br/>
Yeni sınıfının taban sınıfı. Varsayılan taban sınıf [CWindow'dur.](../../atl/reference/cwindow-class.md)

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Oluştur](#create)|Modeless iletişim kutusu oluşturur.|
|[Destroywindow](#destroywindow)|Modeless iletişim kutusunu yok eder.|
|[Domodal](#domodal)|Modal iletişim kutusu oluşturur.|
|[Enddialog](#enddialog)|Bir modal iletişim kutusunu yok eder.|

### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT Yöntemleri

|||
|-|-|
|[GetDialogProc](#getdialogproc)|Geçerli iletişim kutusu yordamını döndürür.|
|[MapDialogRect](#mapdialogrect)|Belirtilen dikdörtgenin iletişim kutusu birimlerini ekran birimleriyle (pikseller) eşler.|
|[OnFinalMessage](#onfinalmessage)|Son iletiyi aldıktan sonra çağrılan, genellikle WM_NCDESTROY.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[Dialogproc](#dialogproc)|İletikutusuna gönderilen iletileri işler.|
|[BaşlangıçDialogProc](#startdialogproc)|İletişim kutusuna gönderilen iletileri işlemek için ilk ileti alındığı zaman çağrılır.|

## <a name="remarks"></a>Açıklamalar

Bir `CDialogImpl` modal veya modsuz iletişim kutusu oluşturabilirsiniz. `CDialogImpl`iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanan iletişim kutusu yordamını sağlar.

Taban sınıf yıkıcı nesneyi `~CWindowImplRoot` yok etmeden önce pencerenin gittiğinden emin olun.

`CDialogImpl`türetilmiştir `CDialogImplBaseT`, sırayla türetilmiştir `CWindowImplRoot`.

> [!NOTE]
> Sınıfınız iletişim `IDD` şablonu kaynak kimliğini belirten bir üye tanımlamalıdır. Örneğin, ATL Proje Sihirbazı sınıfınıza otomatik olarak aşağıdaki satırı ekler:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]

sihirbazın **Adları** sayfasına girilen **Kısa ad** nerededir. `MyDlg`

|Daha fazla bilgi|Bkz.|
|--------------------------------|---------|
|Denetim oluşturma|[ATL Öğretici](../../atl/active-template-library-atl-tutorial.md)|
|ATL'de iletişim kutularını kullanma|[ATL Pencere Sınıfları](../../atl/atl-window-classes.md)|
|ATL Proje Sihirbazı|[ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)|
|İletişim kutuları|Windows SDK'daki [iletişim kutuları](/windows/win32/dlgbox/dialog-boxes) ve sonraki konular|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="cdialogimplcreate"></a><a name="create"></a>CDialogImpl::Oluştur

Modeless iletişim kutusu oluşturur.

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
[içinde] Sahibi penceresine tutamak.

**RECT&** [in] İletişim kutusunun boyutunu ve konumunu belirten bir [RECT](/previous-versions/dd162897\(v=vs.85\)) yapısında. *rect*

*dwInitParam*<br/>
[içinde] WM_INITDIALOG iletisinin *lParam* parametresinde iletişim kutusuna geçecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iletişim kutusunun tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu `CDialogImpl` nesneye otomatik olarak eklenir. Modal iletişim kutusu oluşturmak için [DoModal'ı](#domodal)arayın. Yukarıdaki ikinci geçersiz kılma yalnızca [CComControl](../../atl/reference/ccomcontrol-class.md)ile kullanılır.

## <a name="cdialogimpldestroywindow"></a><a name="destroywindow"></a>CDialogImpl::DestroyWindow

Modeless iletişim kutusunu yok eder.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu başarıyla yok edildiyse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu başarıyla yok edildiyse TRUE döndürür; aksi takdirde YANLIŞ.

## <a name="cdialogimpldialogproc"></a><a name="dialogproc"></a>CDialogImpl::DialogProc

Bu statik işlev iletişim kutusu yordamını uygular.

```
static LRESULT CALLBACK DialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] İletişim kutusunun tutamacı.

*uMsg*<br/>
[içinde] İletişim kutusuna gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`DialogProc`iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemi kullanır.

İletileri işlemek `DialogProc` için farklı bir mekanizma sağlamak için geçersiz kılabilirsiniz.

## <a name="cdialogimpldomodal"></a><a name="domodal"></a>CDialogImpl::DoModal

Modal iletişim kutusu oluşturur.

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
[içinde] Sahibi penceresine tutamak. Varsayılan değer [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) Win32 işlevinin iade değeridir.

*dwInitParam*<br/>
[içinde] WM_INITDIALOG iletisinin *lParam* parametresinde iletişim kutusuna geçecek değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, [EndDialog](#enddialog)çağrısında belirtilen *nRetCode* parametresinin değeri. Aksi takdirde, -1.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu `CDialogImpl` nesneye otomatik olarak eklenir.

Modeless iletişim kutusu oluşturmak için [Oluştur'u](#create)arayın.

## <a name="cdialogimplenddialog"></a><a name="enddialog"></a>CDialogImpl::EndDialog

Bir modal iletişim kutusunu yok eder.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
[içinde] [Değeri CDialogImpl tarafından döndürülecek::DoModal](#domodal).

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu yok edilirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`EndDialog`iletişim yordamı aracılığıyla çağrılmalıdır. İletişim kutusu yok edildikten sonra, Windows iletişim kutusunu oluşturan `DoModal` *nRetCode* değerini return value olarak kullanır.

> [!NOTE]
> Modeless `EndDialog` iletişim kutusunu yok etmek için aramayın. [CWindow::DestroyWindow'u](../../atl/reference/cwindow-class.md#destroywindow) arayın.

## <a name="cdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CDialogImpl::GetDialogProc

Geçerli `DialogProc`iletişim kutusu yordamını döndürür.

```
virtual WNDPROC GetDialogProc();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli iletişim kutusu yordamı.

### <a name="remarks"></a>Açıklamalar

İletişim yordamını kendi yönteminizle değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cdialogimplmapdialogrect"></a><a name="mapdialogrect"></a>CDialogImpl::MapDialogRect

Belirtilen dikdörtgenin iletişim kutusu birimlerini ekran birimlerine (pikseller) dönüştürür (eşler).

```
BOOL MapDialogRect(LPRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Güncelleştirme bölgesini içine alan güncelleştirmenin istemci koordinatlarını almak için bir `CRect` nesneye veya [RECT](/windows/win32/api/windef/ns-windef-rect) yapısına işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirme başarılı olursa sıfırolmayan; Güncelleştirme başarısız olursa 0. Genişletilmiş hata bilgilerini almak `GetLastError`için .

### <a name="remarks"></a>Açıklamalar

İşlev, belirtilen `RECT` yapıdaki koordinatları dönüştürülmüş koordinatlarla değiştirir ve bu da yapının iletişim kutusu oluşturmak veya bir iletişim kutusu içinde denetim konumlandırmak için kullanılmasını sağlar.

## <a name="cdialogimplonfinalmessage"></a><a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage

Son iletiyi aldıktan sonra `WM_NCDESTROY`çağrılır (genellikle).

```
virtual void OnFinalMessage(HWND hWnd);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] Yıkılan pencerenin sapı.

### <a name="remarks"></a>Açıklamalar

Pencere imhası üzerine nesnenizi otomatik olarak silmek istiyorsanız, **bunu sil'** i arayabilirsiniz;

## <a name="cdialogimplstartdialogproc"></a><a name="startdialogproc"></a>CDialogImpl::StartDialogProc

İletişim kutusuna gönderilen iletileri işlemek için ilk ileti alındığı zaman yalnızca bir kez çağrılır.

```
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parametreler

*Hwnd*<br/>
[içinde] İletişim kutusunun tutamacı.

*uMsg*<br/>
[içinde] İletişim kutusuna gönderilen ileti.

*Wparam*<br/>
[içinde] İletiye özgü ek bilgiler.

*Lparam*<br/>
[içinde] İletiye özgü ek bilgiler.

### <a name="return-value"></a>Dönüş Değeri

Pencere yordamı.

### <a name="remarks"></a>Açıklamalar

İlk çağrıdan `StartDialogProc`sonra `DialogProc` , bir iletişim yordamı olarak ayarlanır ve diğer aramalar oraya gidin.

## <a name="see-also"></a>Ayrıca bkz.

[Begın_msg_map](message-map-macros-atl.md#begin_msg_map)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
