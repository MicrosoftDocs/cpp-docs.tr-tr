---
description: 'Daha fazla bilgi edinin: IOleInPlaceActiveObjectImpl sınıfı'
title: IOleInPlaceActiveObjectImpl sınıfı
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
ms.openlocfilehash: 02f74e462dca2aac2749b8602281f40c8eacd0eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158198"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl sınıfı

Bu sınıf, yerinde denetim ve kapsayıcısı arasındaki iletişimi yardım etmek için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IOleInPlaceActiveObjectImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl:: ContextSensitiveHelp](#contextsensitivehelp)|Bağlama duyarlı yardımı etkinleştirilir. ATL uygulama E_NOTIMPL döndürür.|
|[IOleInPlaceActiveObjectImpl:: Enablemodsuz](#enablemodeless)|Kalıcı olmayan iletişim kutularını izin vermez. ATL uygulama S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl:: GetWindow](#getwindow)|Bir pencere tutamacı alır.|
|[IOleInPlaceActiveObjectImpl:: OnDocWindowActivate](#ondocwindowactivate)|Kapsayıcının belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi bilgilendirir. ATL uygulama S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl:: OnFrameWindowActivate](#onframewindowactivate)|Kapsayıcının en üst düzey çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi bilgilendirir. ATL uygulamasının döndürdüğü|
|[IOleInPlaceActiveObjectImpl:: ResizeBorder](#resizeborder)|Kenarlığını yeniden boyutlandırmak için gereken denetimi bilgilendirir. ATL uygulama S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl:: TranslateAccelerator](#translateaccelerator)|Kapsayıcıdan menü hızlandırıcının anahtar iletilerini işler. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) arabirimi bir yerinde denetim ve kapsayıcısı arasındaki iletişime yardımcı olur; Örneğin, denetimin ve kapsayıcının etkin durumunu iletişim kurmak ve denetimin kendisini yeniden boyutlandırmak için gereken denetimi bilgilendirmesi. Sınıfı, `IOleInPlaceActiveObjectImpl` `IOleInPlaceActiveObject` `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek varsayılan bir uygulamasını sağlar ve destekler.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a> IOleInPlaceActiveObjectImpl:: ContextSensitiveHelp

Bağlama duyarlı yardımı etkinleştirilir.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) .

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a> IOleInPlaceActiveObjectImpl:: Enablemodsuz

Kalıcı olmayan iletişim kutularını izin vermez.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleInPlaceActiveObject:: Enablemodsuz](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) .

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a> IOleInPlaceActiveObjectImpl:: GetWindow

Kapsayıcı, denetimin pencere tanıtıcısını almak için bu işlevi çağırır.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bazı kapsayıcılar, şu anda pencereli olsa bile, penceresiz olan bir denetimle çalışmayacaktır. ATL 'nin uygulamasında, `CComControl::m_bWasOnceWindowless` veri ÜYESI true ise işlev E_FAIL döndürür. Aksi takdirde, \* *PHWND* null değilse, `GetWindow` Denetim sınıfının veri üyesine *phwnd* atar `m_hWnd` ve s_ok döndürür.

Windows SDK için bkz. [IOleWindow:: GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) .

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a> IOleInPlaceActiveObjectImpl:: OnDocWindowActivate

Kapsayıcının belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi bilgilendirir.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) .

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a> IOleInPlaceActiveObjectImpl:: OnFrameWindowActivate

Kapsayıcının en üst düzey çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi bilgilendirir.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) .

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a> IOleInPlaceActiveObjectImpl:: ResizeBorder

Kenarlığını yeniden boyutlandırmak için gereken denetimi bilgilendirir.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleInPlaceActiveObject:: ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) .

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a> IOleInPlaceActiveObjectImpl:: TranslateAccelerator

Kapsayıcıdan menü hızlandırıcının anahtar iletilerini işler.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem aşağıdaki dönüş değerlerini destekler:

İleti başarıyla çevrilmişse S_OK.

İleti çevrilmişse S_FALSE.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) .

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX denetimleri arabirimleri](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
