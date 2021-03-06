---
description: 'Daha fazla bilgi edinin: CComControl sınıfı'
title: CComControl sınıfı
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
ms.openlocfilehash: 3fbd0f3483c61993a575b0817538f759b06c11d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146750"
---
# <a name="ccomcontrol-class"></a>CComControl sınıfı

Bu sınıf, ATL denetimleri oluşturmak ve yönetmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

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
Pencereleme işlevlerini uygulayan temel sınıf. Varsayılan olarak [CWindowImpl](../../atl/reference/cwindowimpl-class.md)olur.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComControl:: CComControl](#ccomcontrol)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComControl:: Controlqueryınterface](#controlqueryinterface)|İstenen arabirim için bir işaretçi alır.|
|[CComControl:: CreateControlWindow](#createcontrolwindow)|Denetim için bir pencere oluşturur.|
|[CComControl:: FireOnChanged](#fireonchanged)|Kapsayıcının havuzuna bir denetim özelliği değiştiğini bildirir.|
|[CComControl:: Fireonrequestedıt](#fireonrequestedit)|Kapsayıcının havuzuna bir denetim özelliğinin değiştirmek üzere olduğunu ve nesnenin havuza nasıl devam edeceğine ilişkin olduğunu bildirir.|
|[CComControl:: MessageBox](#messagebox)|İleti kutusu oluşturmak, göstermek ve çalıştırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CComControl` , ATL denetimleri için yararlı denetim Yardımcısı işlevleri ve temel veri üyeleri kümesidir. ATL Denetim Sihirbazı 'nı kullanarak standart bir denetim veya bir DHTML denetimi oluşturduğunuzda, sihirbaz sınıfınızı otomatik olarak türetecektir `CComControl` . `CComControl` yöntemlerinin çoğunu [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)'den türetir.

Denetim oluşturma hakkında daha fazla bilgi için bkz. [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md). ATL Proje Sihirbazı hakkında daha fazla bilgi için, [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)makalesine bakın.

`CComControl`Yöntemlerin ve veri üyelerinin bir gösterimi için bkz. [Circ](../../overview/visual-cpp-samples.md) örneği.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`WinBase`

[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)

`CComControl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ccomcontrolccomcontrol"></a><a name="ccomcontrol"></a> CComControl:: CComControl

Oluşturucu.

```
CComControl();
```

### <a name="remarks"></a>Açıklamalar

CWindowImpl aracılığıyla devralınmış veri üyesini geçirerek [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase) oluşturucusunu çağırır `m_hWnd` . [](../../atl/reference/cwindowimpl-class.md)

## <a name="ccomcontrolcontrolqueryinterface"></a><a name="controlqueryinterface"></a> CComControl:: Controlqueryınterface

İstenen arabirim için bir işaretçi alır.

```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```

### <a name="parameters"></a>Parametreler

*'si*<br/>
'ndaki İstenen arabirimin GUID 'SI.

*PPV*<br/>
dışı Arabirim bulunmazsa, *IID* tarafından tanımlanan arabirim işaretçisine yönelik bir işaretçi veya ARABIRIM bulunamazsa null.

### <a name="remarks"></a>Açıklamalar

Yalnızca COM Map tablosundaki arabirimleri işler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]

## <a name="ccomcontrolcreatecontrolwindow"></a><a name="createcontrolwindow"></a> CComControl:: CreateControlWindow

Varsayılan olarak, çağırarak Denetim için bir pencere oluşturur `CWindowImpl::Create` .

```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
'ndaki Üst veya sahip penceresine işleyin. Geçerli bir pencere tanıtıcısı sağlanmalıdır. Denetim penceresi, ana penceresinin alanıyla sınırlandırıyor.

*rcPos*<br/>
'ndaki Oluşturulacak pencerenin başlangıç boyutu ve konumu.

### <a name="remarks"></a>Açıklamalar

Tek bir pencere oluşturma dışında bir şey yapmak istiyorsanız bu yöntemi geçersiz kılın; Örneğin, iki pencere oluşturmak için, bunlardan biri denetiminiz için bir araç çubuğu haline gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]

## <a name="ccomcontrolfireonchanged"></a><a name="fireonchanged"></a> CComControl:: FireOnChanged

Kapsayıcının havuzuna bir denetim özelliği değiştiğini bildirir.

```
HRESULT FireOnChanged(DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*Dı*<br/>
'ndaki Değiştirilen özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim sınıfınız [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)öğesinden türetildiğinden, bu yöntem, belirtilen denetim özelliğinin değiştiği tüm bağlı arabirimlere bildirmek Için [CFirePropNotifyEvent:: FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged) öğesini çağırır `IPropertyNotifySink` . Denetim sınıfınız öğesinden türetilmezse `IPropertyNotifySink` , bu yöntem s_ok döndürür.

Denetiminiz bağlantı noktalarını desteklemeseler bile bu yöntemin çağrısı güvenlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]

## <a name="ccomcontrolfireonrequestedit"></a><a name="fireonrequestedit"></a> CComControl:: Fireonrequestedıt

Kapsayıcının havuzuna bir denetim özelliğinin değiştirmek üzere olduğunu ve nesnenin havuza nasıl devam edeceğine ilişkin olduğunu bildirir.

```
HRESULT FireOnRequestEdit(DISPID dispID);
```

### <a name="parameters"></a>Parametreler

*Dı*<br/>
'ndaki Değiştirilecek özelliğin tanımlayıcısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT değerlerinden biri.

### <a name="remarks"></a>Açıklamalar

Denetim sınıfınız [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink)öğesinden türetildiğinden, bu yöntem [CFirePropNotifyEvent:: Fireonrequestedıt](cfirepropnotifyevent-class.md#fireonrequestedit) ' i çağırarak, `IPropertyNotifySink` belirtilen denetim özelliğinin değiştirmek üzere olduğu tüm bağlı arabirimlere bildirir. Denetim sınıfınız öğesinden türetilmezse `IPropertyNotifySink` , bu yöntem s_ok döndürür.

Denetiminiz bağlantı noktalarını desteklemeseler bile bu yöntemin çağrısı güvenlidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]

## <a name="ccomcontrolmessagebox"></a><a name="messagebox"></a> CComControl:: MessageBox

İleti kutusu oluşturmak, göstermek ve çalıştırmak için bu yöntemi çağırın.

```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
İleti kutusunda görüntülenecek metin.

*lpszCaption*<br/>
İletişim kutusu başlığı. NULL ise (varsayılan), "Error" başlığı kullanılır.

*nTür*<br/>
İletişim kutusunun içeriğini ve davranışını belirtir. Kullanılabilir farklı ileti kutularının bir listesi için Windows SDK belgelerindeki [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) girdisine bakın. Varsayılan değer basit bir **Tamam** düğmesi sağlar.

### <a name="return-value"></a>Dönüş Değeri

Windows SDK belgelerinde [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) altında listelenen menü öğesi değerlerinden birini belirten bir tamsayı değeri döndürür.

### <a name="remarks"></a>Açıklamalar

`MessageBox` geliştirme sırasında ve kullanıcıya bir hata ya da uyarı iletisi görüntülemenin kolay bir yolu olarak yararlı olur.

## <a name="see-also"></a>Ayrıca bkz.

[CWindowImpl sınıfı](../../atl/reference/cwindowimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComControlBase sınıfı](../../atl/reference/ccomcontrolbase-class.md)<br/>
[CComCompositeControl sınıfı](../../atl/reference/ccomcompositecontrol-class.md)
