---
title: CComControl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
ms.openlocfilehash: 3518de3596748fa284c1f898b69d1576903e9510
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320760"
---
# <a name="ccomcontrol-class"></a>CComControl Sınıfı

Bu sınıf, ATL denetimleri oluşturmak ve yönetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class WinBase = CWindowImpl<T>>
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Denetimi uygulayan sınıf.

*WinBase*<br/>
Pencere işlevlerini uygulayan taban sınıf. [Varsayılan cWindowImpl](../../atl/reference/cwindowimpl-class.md)için .

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CcomControl::ccomcontrol](#ccomcontrol)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CcomControl::ControlQueryInterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComControl::CreateControl Window](#createcontrolwindow)|Denetim için bir pencere oluşturur.|
|[CcomControl::fireonchanged](#fireonchanged)|Konteynerin lavabosuna bir denetim özelliğinin değiştiğini haber vetir.|
|[CComControl::FireOnRequestedit](#fireonrequestedit)|Kapsayıcının lavabosuna bir denetim özelliğinin değişmek üzere olduğunu ve nesnenin lavaboya nasıl devam edeceğini sorduğunu haber cisim.|
|[CComControl::MessageBox](#messagebox)|İleti kutusu oluşturmak, görüntülemek ve çalıştırmak için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

`CComControl`ATL denetimleri için yararlı denetim yardımcı işlevleri ve temel veri üyeleri kümesidir. ATL Denetim Sihirbazı'nı kullanarak standart bir denetim veya DHTML denetimi oluşturduğunuzda, sihirbaz sınıfınızı otomatik olarak .'den `CComControl`türetecektir. `CComControl`yöntemlerinin çoğunu [CComControlBase'den](../../atl/reference/ccomcontrolbase-class.md)türetilmiştir.

Denetim oluşturma hakkında daha fazla bilgi için [ATL Tutorial'a](../../atl/active-template-library-atl-tutorial.md)bakın. ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

Yöntem ve `CComControl` veri üyelerinin gösterimi için [CIRC](../../overview/visual-cpp-samples.md) örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WinBase`

[CcomControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ccomcontrolccomcontrol"></a><a name="ccomcontrol"></a>CcomControl::ccomcontrol

Oluşturucu.

```
CComControl();
```

### <a name="remarks"></a>Açıklamalar

[CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) oluşturucu çağırır, `m_hWnd` [CWindowImpl](../../atl/reference/cwindowimpl-class.md)üzerinden devralınan veri üyesi geçen.

## <a name="ccomcontrolcontrolqueryinterface"></a><a name="controlqueryinterface"></a>CcomControl::ControlQueryInterface

İstenen arabirim için bir işaretçi alır.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] İstenmekte olan arabirimin GUID'i.

*Ppv*<br/>
[çıkış] Arabirim bulunamazsa *iid*veya NULL tarafından tanımlanan arabirim işaretçisine işaretçi.

### <a name="remarks"></a>Açıklamalar

Yalnızca COM harita tablosundaki arabirimleri işler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

## <a name="ccomcontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a>CComControl::CreateControl Window

Varsayılan olarak, arayarak `CWindowImpl::Create`denetim için bir pencere oluşturur.

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
[içinde] Üst veya sahip penceresine işle. Geçerli bir pencere tutamacı sağlanmalıdır. Denetim penceresi ana penceresinin alanıyla sınırlıdır.

*rcPos*<br/>
[içinde] Oluşturulacak pencerenin başlangıç boyutu ve konumu.

### <a name="remarks"></a>Açıklamalar

Örneğin, biri denetiminiz için bir araç çubuğu haline gelen iki pencere oluşturmak için tek bir pencere oluşturmak tan başka bir şey yapmak istiyorsanız bu yöntemi geçersiz kılın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

## <a name="ccomcontrolfireonchanged"></a><a name="fireonchanged"></a>CcomControl::fireonchanged

Konteynerin lavabosuna bir denetim özelliğinin değiştiğini haber vetir.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
[içinde] Değiştirilen özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Kontrol sınıfınız [IPropertyNotifySink'den](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)türetilmişse, bu yöntem [CFirePropNotifyEvent'i çağırır::FireOnBelirtilen](cfirepropnotifyevent-class.md#fireonchanged) kontrol özelliğinin değiştiğini bağlı `IPropertyNotifySink` tüm arabirimlere bildirmek için değiştirildi. Denetim sınıfınız bu yöntemden `IPropertyNotifySink`kaynaklamazsa, bu yöntem S_OK döndürür.

Bu yöntem, denetiminiz bağlantı noktalarını desteklemese bile aramak güvenlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

## <a name="ccomcontrolfireonrequestedit"></a><a name="fireonrequestedit"></a>CComControl::FireOnRequestedit

Kapsayıcının lavabosuna bir denetim özelliğinin değişmek üzere olduğunu ve nesnenin lavaboya nasıl devam edeceğini sorduğunu haber cisim.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*Dıspıd*<br/>
[içinde] Değişmek üzere olan özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Kontrol sınıfınız [IPropertyNotifySink'den](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)türetilmişse, bu yöntem [CFirePropNotifyEvent'i çağırır::FireOnRequestEdit,](cfirepropnotifyevent-class.md#fireonrequestedit) belirtilen kontrol özelliğinin değişmek üzere olduğunu bağlı `IPropertyNotifySink` tüm arabirimlere bildirmek için çağırır. Denetim sınıfınız bu yöntemden `IPropertyNotifySink`kaynaklamazsa, bu yöntem S_OK döndürür.

Bu yöntem, denetiminiz bağlantı noktalarını desteklemese bile aramak güvenlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

## <a name="ccomcontrolmessagebox"></a><a name="messagebox"></a>CComControl::MessageBox

İleti kutusu oluşturmak, görüntülemek ve çalıştırmak için bu yöntemi arayın.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
İleti kutusunda görüntülenecek metin.

*lpszCaption*<br/>
İletişim kutusu başlığı. NULL (varsayılan) ise, "Hata" başlığı kullanılır.

*nTipi*<br/>
İletişim kutusunun içeriğini ve davranışını belirtir. Kullanılabilir farklı ileti kutularının listesi için Windows SDK belgelerindeki [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) girişine bakın. Varsayılan basit bir **Tamam** düğmesi sağlar.

### <a name="return-value"></a>Dönüş Değeri

Windows SDK belgelerinde [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) altında listelenen menü öğesi değerlerinden birini belirten bir bir sonda değeri döndürür.

### <a name="remarks"></a>Açıklamalar

`MessageBox`geliştirme sırasında ve kullanıcıya bir hata veya uyarı iletisi görüntülemek için kolay bir yol olarak yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[CWindowImpl Sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CcomControlBase Sınıfı](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl Sınıfı](../../atl/reference/ccomcompositecontrol-class.md)
