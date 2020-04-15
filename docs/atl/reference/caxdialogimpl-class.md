---
title: CAxDialogImpl Sınıfı
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
ms.openlocfilehash: d8e60a817d197f67c14318a7d50ddf796e570142
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318735"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl Sınıfı

Bu sınıf, ActiveX denetimlerini barındıran bir iletişim kutusu (modal veya modeless) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CAxDialogImpl`türetilmiştir.

*TBase*<br/>
Temel pencere sınıfı `CDialogImplBaseT`için .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|Nesnenin lavabo haritası olay haritasındaki tüm girişleri bildirmek veya tavsiye etmemek için bu yöntemi arayın.|
|[CAxDialogImpl::Oluştur](#create)|Modeless iletişim kutusu oluşturmak için bu yöntemi arayın.|
|[CAxDialogImpl::DestroyWindow](#destroywindow)|Modeless iletişim kutusunu yok etmek için bu yöntemi arayın.|
|[CAxDialogImpl::DoModal](#domodal)|Modal iletişim kutusu oluşturmak için bu yöntemi arayın.|
|[CAxDialogImpl::EndDialog](#enddialog)|Bir modal iletişim kutusunu yok etmek için bu yöntemi arayın.|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|`DialogProc` Geri arama işlevine işaretçi almak için bu yöntemi arayın.|
|[CAxDialogImpl::GetIDD](#getidd)|İletişim şablonu kaynak kimliğini almak için bu yöntemi arayın|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|İletinin bu iletişim kutusu için tasarlanıp tasarlanmadığını belirlemek ve buysa iletiyi işlemek için bu yöntemi arayın.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CAxDialogImpl::m_bModal](#m_bmodal)|Yalnızca hata ayıklama da var olan bir değişken oluşturur ve iletişim kutusu modal ise doğru olarak ayarlanır.|

## <a name="remarks"></a>Açıklamalar

`CAxDialogImpl`modal veya modeless iletişim kutusu oluşturmanıza olanak tanır. `CAxDialogImpl`iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanan iletişim kutusu yordamını sağlar.

`CAxDialogImpl`türetilmiştir `CDialogImplBaseT`, sırayla *TBase* türetilmiştir (varsayılan `CWindow`olarak, ) ve `CMessageMap`.

Sınıfınız iletişim şablonu kaynak kimliğini belirten bir IDD üyesi tanımlamalıdır. Örneğin, **Sınıf Ekle** iletişim kutusunu kullanarak Bir ATL İletişim nesnesi eklemek sınıfınıza otomatik olarak aşağıdaki satırı ekler:

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

ATL İletişim Sihirbazı'na girilen Kısa `MyDialog` **ad** nerededir.

Bkz. Daha fazla bilgi için [Bir İletişim Kutusu Uygulama.](../../atl/implementing-a-dialog-box.md)

Oluşturulan modal iletişim kutusundaki ActiveX denetiminin `CAxDialogImpl` hızlandırıcı tuşlarını desteklemeyeceğini unutmayın. Bir iletişim kutusunda hızlandırıcı anahtarlarını `CAxDialogImpl`desteklemek için, modeless iletişim kutusu oluşturun ve kendi ileti döngünüzu kullanarak, hızlandırıcı anahtarını işlemek için kuyruktan bir ileti aldıktan sonra [CAxDialogImpl::IsDialogMessage'ı](#isdialogmessage) kullanın.

Daha fazla `CAxDialogImpl`bilgi [için, Bkz. ATL Control Containment SSS.](../../atl/atl-control-containment-faq.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmessagemap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap

Nesnenin lavabo haritası olay haritasındaki tüm girişleri bildirmek veya tavsiye etmemek için bu yöntemi arayın.

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>Parametreler

*bAdvise*<br/>
Tüm lavabo girişleri tavsiye edilecekse doğru ayarlayın; tüm lavabo girişleri tavsiye edilmezse yanlış.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

## <a name="caxdialogimplcreate"></a><a name="create"></a>CAxDialogImpl::Oluştur

Modeless iletişim kutusu oluşturmak için bu yöntemi arayın.

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
[içinde] Sahibi penceresine tutamak.

*dwInitParam*<br/>
[içinde] WM_INITDIALOG iletisinin *lParam* parametresinde iletişim kutusuna geçecek değeri belirtir.

*REKT&*<br/>
Bu parametre kullanılmaz. Bu parametre tarafından `CComControl`geçirilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni oluşturulan iletişim kutusunun tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu `CAxDialogImpl` nesneye otomatik olarak eklenir. Modal iletişim kutusu oluşturmak için [DoModal'ı](#domodal)arayın.

İkinci geçersiz kılma yalnızca [ccomControl](../../atl/reference/ccomcontrol-class.md)ile iletişim kutuları nın kullanılabilmesi için sağlanır.

## <a name="caxdialogimpldestroywindow"></a><a name="destroywindow"></a>CAxDialogImpl::DestroyWindow

Modeless iletişim kutusunu yok etmek için bu yöntemi arayın.

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>Dönüş Değeri

Pencere başarıyla yok edilirse DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Modal `DestroyWindow` iletişim kutusunu yok etmek için aramayın. Bunun yerine [EndDialog'u](#enddialog) arayın.

## <a name="caxdialogimpldomodal"></a><a name="domodal"></a>CAxDialogImpl::DoModal

Modal iletişim kutusu oluşturmak için bu yöntemi arayın.

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

Başarılı olursa, [EndDialog](#enddialog)çağrısında belirtilen *nRetCode* parametresinin değeri; aksi takdirde, -1.

### <a name="remarks"></a>Açıklamalar

Bu iletişim kutusu `CAxDialogImpl` nesneye otomatik olarak eklenir.

Modeless iletişim kutusu oluşturmak için [Oluştur'u](#create)arayın.

## <a name="caxdialogimplenddialog"></a><a name="enddialog"></a>CAxDialogImpl::EndDialog

Bir modal iletişim kutusunu yok etmek için bu yöntemi arayın.

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
[içinde] [DoModal](#domodal)tarafından döndürülecek değer.

### <a name="return-value"></a>Dönüş Değeri

İletişim kutusu yok edilirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`EndDialog`iletişim kutusu yordamı ile çağrılmalıdır. İletişim kutusu yok edildikten sonra, Windows iletişim kutusunu oluşturan `DoModal` *nRetCode* değerini return value olarak kullanır.

> [!NOTE]
> Modeless `EndDialog` iletişim kutusunu yok etmek için aramayın. Bunun yerine [DestroyWindow'u](#destroywindow) arayın.

## <a name="caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc

`DialogProc` Geri arama işlevine işaretçi almak için bu yöntemi arayın.

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>Dönüş Değeri

Geri `DialogProc` arama işlevine bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

İşlev uygulama `DialogProc` tanımlı bir geri arama işlevidir.

## <a name="caxdialogimplgetidd"></a><a name="getidd"></a>CAxDialogImpl::GetIDD

İletişim şablonu kaynak kimliğini almak için bu yöntemi arayın.

```
int GetIDD();
```

### <a name="return-value"></a>Dönüş Değeri

İletişim şablonu kaynak kimliğini verir.

## <a name="caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage

İletinin bu iletişim kutusu için tasarlanıp tasarlanmadığını belirlemek ve buysa iletiyi işlemek için bu yöntemi arayın.

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>Parametreler

*pMsg*<br/>
Denetlenecek iletiyi içeren bir [MSG](/windows/win32/api/winuser/ns-winuser-msg) yapısına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İleti işlenmişse TRUE döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, ileti döngüsü içinden çağrılması amaçlanmıştır.

## <a name="caxdialogimplm_bmodal"></a><a name="m_bmodal"></a>CAxDialogImpl::m_bModal

Yalnızca hata ayıklama da var olan bir değişken oluşturur ve iletişim kutusu modal ise doğru olarak ayarlanır.

```
bool m_bModal;
```

## <a name="see-also"></a>Ayrıca bkz.

[CDialogImpl Sınıfı](../../atl/reference/cdialogimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
