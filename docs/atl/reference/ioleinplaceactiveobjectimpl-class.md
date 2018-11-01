---
title: Ioleınplaceactiveobjectımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: 785972af55cdf594bb45b0257e626aa5344af60a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447469"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>Ioleınplaceactiveobjectımpl sınıfı

Bu sınıf, bir yerinde denetim kapsayıcısı arasındaki iletişimi uygulayıcılarına yardımcı yöntemleri sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IOleInPlaceActiveObjectImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Bağlama duyarlı Yardım sağlar. ATL uygulamasını E_NOTIMPL döndürür.|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Kalıcı olmayan iletişim kutuları sağlar. ATL uygulamasını S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Bir pencere tutucu alır.|
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Kapsayıcının belge penceresi etkin veya devre dışı olduğunda denetim bildirir. ATL uygulamasını S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Kapsayıcının en üst düzey çerçeve penceresini etkinleştirmek veya denetim bildirir. ATL uygulamasını döndürür|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Kenarlıkları yeniden boyutlandırmak ihtiyaç duyduğu denetim bildirir. ATL uygulamasını S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Kapsayıcısından menü kısayol tuşu iletileri işler. ATL uygulamasını E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IOleInPlaceActiveObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceactiveobject) arabirimi yerinde denetim kapsayıcısı arasındaki iletişimi destekler; Örneğin, Denetim ve kapsayıcı etkin duruma satıcılarla iletişim kurmayı ve denetim bildiren, yeniden boyutlandırmak için gerekli kendisi. Sınıf `IOleInPlaceActiveObjectImpl` bir varsayılan uygulamayı sağlar `IOleInPlaceActiveObject` destekler `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

Bağlama duyarlı Yardım sağlar.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) Windows SDK içinde.

##  <a name="enablemodeless"></a>  IOleInPlaceActiveObjectImpl::EnableModeless

Kalıcı olmayan iletişim kutuları sağlar.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) Windows SDK içinde.

##  <a name="getwindow"></a>  IOleInPlaceActiveObjectImpl::GetWindow

Kapsayıcı denetim pencere tanıtıcısı almak için bu işlevi çağırır.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bazı kapsayıcıları, şu anda pencereli olsa bile penceresiz, bir denetim ile çalışmaz. ATL'nin uygulamasında, `CComControl::m_bWasOnceWindowless` veri üyesi ise TRUE, E_FAIL işlevi döndürür. Aksi takdirde \* *phwnd* NULL değil `GetWindow` atar *phwnd* denetim sınıfın veri üyesinin `m_hWnd` ve S_OK döndürür.

Bkz: [IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) Windows SDK içinde.

##  <a name="ondocwindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnDocWindowActivate

Kapsayıcının belge penceresi etkin veya devre dışı olduğunda denetim bildirir.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) Windows SDK içinde.

##  <a name="onframewindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnFrameWindowActivate

Kapsayıcının en üst düzey çerçeve penceresini etkinleştirmek veya denetim bildirir.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) Windows SDK içinde.

##  <a name="resizeborder"></a>  IOleInPlaceActiveObjectImpl::ResizeBorder

Kenarlıkları yeniden boyutlandırmak ihtiyaç duyduğu denetim bildirir.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) Windows SDK içinde.

##  <a name="translateaccelerator"></a>  IOleInPlaceActiveObjectImpl::TranslateAccelerator

Kapsayıcısından menü kısayol tuşu iletileri işler.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem, aşağıdaki dönüş değerlerini destekler:

İletinin başarıyla çevrilmiş S_OK.

İleti değil çevrilmiş S_FALSE.

### <a name="remarks"></a>Açıklamalar

Bkz: [IOleInPlaceActiveObject::TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Arabirimleri ActiveX denetimleri](/windows/desktop/com/activex-controls-interfaces)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
