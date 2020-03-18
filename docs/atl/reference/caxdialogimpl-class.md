---
title: CAxDialogImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: 548d2aed0644187b4b8dee1e472b581f1f92d6a1
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418015"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl sınıfı

Bu sınıf, ActiveX denetimlerini barındıran bir iletişim kutusu (kalıcı veya kalıcı) uygular.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `CAxDialogImpl`türetilir.

*TBase*<br/>
`CDialogImplBaseT`için temel pencere sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAxDialogImpl:: Advisesınkmap](#advisesinkmap)|Nesnenin havuz eşleme olay eşlemesindeki tüm girişlerin önerisi için bu yöntemi çağırın.|
|[CAxDialogImpl:: Create](#create)|Kalıcı olmayan bir iletişim kutusu oluşturmak için bu yöntemi çağırın.|
|[CAxDialogImpl::D estroyWindow](#destroywindow)|Kalıcı olmayan bir iletişim kutusunu yok etmek için bu yöntemi çağırın.|
|[CAxDialogImpl::D oModal](#domodal)|Kalıcı bir iletişim kutusu oluşturmak için bu yöntemi çağırın.|
|[CAxDialogImpl:: EndDialog](#enddialog)|Kalıcı iletişim kutusunu yok etmek için bu yöntemi çağırın.|
|[CAxDialogImpl:: GetDialogProc](#getdialogproc)|`DialogProc` geri çağırma işlevine yönelik bir işaretçi almak için bu yöntemi çağırın.|
|[CAxDialogImpl:: Getıdd](#getidd)|İletişim kutusu şablonu kaynak KIMLIĞINI almak için bu yöntemi çağırın|
|[CAxDialogImpl:: IsDialogMessage](#isdialogmessage)|Bu iletişim kutusu için bir iletinin istenip istenmediğini ve eğer ise iletiyi işlemesini öğrenmek için bu yöntemi çağırın.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAxDialogImpl:: m_bModal](#m_bmodal)|Yalnızca hata ayıklama yapılarında bulunan ve iletişim kutusu kalıcı ise true olarak ayarlanmış bir değişken.|

## <a name="remarks"></a>Açıklamalar

`CAxDialogImpl` kalıcı veya kalıcı olmayan bir iletişim kutusu oluşturmanıza olanak sağlar. `CAxDialogImpl`, iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanan iletişim kutusu yordamını sağlar.

`CAxDialogImpl` `CDialogImplBaseT`türetilir, bu, sırasıyla *TBase* 'den türetilir (varsayılan olarak, `CWindow`) ve `CMessageMap`.

Sınıfınız, iletişim kutusu şablonu kaynak KIMLIĞINI belirten bir ıDD üyesini tanımlamalıdır. Örneğin, **Sınıf Ekle** iletişim kutusunu kullanarak atl iletişim nesnesi eklemek, sınıfınıza aşağıdaki satırı otomatik olarak ekler:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

Burada `MyDialog`, ATL Iletişim Sihirbazı 'nda girilen **kısa addır** .

Daha fazla bilgi için bkz. [Iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) .

`CAxDialogImpl` ile oluşturulan kalıcı iletişim kutusundaki ActiveX denetiminin Hızlandırıcı tuşlarını desteklemediğini unutmayın. `CAxDialogImpl`ile oluşturulan bir iletişim kutusunda Hızlandırıcı tuşlarını desteklemek için, modsuz bir iletişim kutusu oluşturun ve kendi ileti döngünüzü kullanarak, bir Hızlandırıcı tuşunu işlemek üzere kuyruktan bir ileti aldıktan sonra [Caxdialogimpl:: IsDialogMessage](#isdialogmessage) ' ı kullanın.

`CAxDialogImpl`hakkında daha fazla bilgi için bkz. [atl Denetim KAPSAMı SSS](../../atl/atl-control-containment-faq.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

##  <a name="advisesinkmap"></a>CAxDialogImpl:: Advisesınkmap

Nesnenin havuz eşleme olay eşlemesindeki tüm girişlerin önerisi için bu yöntemi çağırın.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*Rozzden*<br/>
Tüm havuz girişlerinin önergetirilmesi gerekiyorsa, true olarak ayarlayın; Tüm havuz girişlerinin önerilemedi durumunda false.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

##  <a name="create"></a>CAxDialogImpl:: Create

Kalıcı olmayan bir iletişim kutusu oluşturmak için bu yöntemi çağırın.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
'ndaki Sahip penceresi için tanıtıcı.

*dwInitParam*<br/>
'ndaki WM_INITDIALOG iletisinin *lParam* parametresindeki iletişim kutusuna geçirilecek değeri belirtir.

*RECT &*<br/>
Bu parametre kullanılmaz. Bu parametre `CComControl`tarafından geçirilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iletişim kutusunun tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu, `CAxDialogImpl` nesnesine otomatik olarak eklenir. Kalıcı bir iletişim kutusu oluşturmak için [DoModal](#domodal)' ı çağırın.

İkinci geçersiz kılma yalnızca, iletişim kutularının [CComControl](../../atl/reference/ccomcontrol-class.md)ile kullanılabilmesi için sağlanır.

##  <a name="destroywindow"></a>CAxDialogImpl::D estroyWindow

Kalıcı olmayan bir iletişim kutusunu yok etmek için bu yöntemi çağırın.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla iptal edildiğinde doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Kalıcı iletişim kutusunu yok etmek için `DestroyWindow` çağırmayın. Bunun yerine [EndDialog](#enddialog) çağırın.

##  <a name="domodal"></a>CAxDialogImpl::D oModal

Kalıcı bir iletişim kutusu oluşturmak için bu yöntemi çağırın.

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

Başarılı olursa, [EndDialog](#enddialog)çağrısında belirtilen *nekcode* parametresinin değeri; Aksi takdirde,-1.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu, `CAxDialogImpl` nesnesine otomatik olarak eklenir.

Kalıcı olmayan bir iletişim kutusu oluşturmak için [Oluştur](#create)' u çağırın.

##  <a name="enddialog"></a>CAxDialogImpl:: EndDialog

Kalıcı iletişim kutusunu yok etmek için bu yöntemi çağırın.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parametreler

*Nekcode*<br/>
'ndaki [DoModal](#domodal)tarafından döndürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu yok edildiğinde doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

`EndDialog` iletişim kutusu yordamı ile çağrılmalıdır. İletişim kutusu yok edildiğinde, Windows, iletişim kutusunu oluşturan `DoModal`için dönüş değeri olarak *Nekcode* değerini kullanır.

> [!NOTE]
>  Kalıcı olmayan iletişim kutusunu yok etmek için `EndDialog` çağırmayın. Bunun yerine [Destroyıwindow](#destroywindow) çağrısı yapın.

##  <a name="getdialogproc"></a>CAxDialogImpl:: GetDialogProc

`DialogProc` geri çağırma işlevine yönelik bir işaretçi almak için bu yöntemi çağırın.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>Dönüş Değeri

`DialogProc` geri çağırma işlevine bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`DialogProc` işlevi uygulama tanımlı bir geri çağırma işlevidir.

##  <a name="getidd"></a>CAxDialogImpl:: Getıdd

İletişim kutusu şablonu kaynak KIMLIĞINI almak için bu yöntemi çağırın.

```
int GetIDD();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu şablonu kaynak KIMLIĞINI döndürür.

##  <a name="isdialogmessage"></a>CAxDialogImpl:: IsDialogMessage

Bu iletişim kutusu için bir iletinin istenip istenmediğini ve eğer ise iletiyi işlemesini öğrenmek için bu yöntemi çağırın.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Denetlenecek iletiyi içeren bir [msg](/windows/win32/api/winuser/ns-winuser-msg) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlendiyse TRUE, aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin bir ileti döngüsü içinden çağrılması amaçlanmıştır.

##  <a name="m_bmodal"></a>CAxDialogImpl:: m_bModal

Yalnızca hata ayıklama yapılarında bulunan ve iletişim kutusu kalıcı ise true olarak ayarlanmış bir değişken.

```
bool m_bModal;
```

## <a name="see-also"></a>Ayrıca bkz.

[CDialogImpl Sınıfı](../../atl/reference/cdialogimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
