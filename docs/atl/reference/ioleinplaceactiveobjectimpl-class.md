---
title: IOleInPlaceActiveObjectImpl Sınıfı
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
ms.openlocfilehash: b39ba2845a5483444dac53d1616654e902969c77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326593"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl Sınıfı

Bu sınıf, yerinde denetim ve kapsayıcı arasındaki iletişimi yardımcı olmak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IOleInPlaceActiveObjectImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|İçeriğe duyarlı yardımı sağlar. ATL uygulaması E_NOTIMPL döndürür.|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Modeless iletişim kutularını etkinleştirin. ATL uygulaması S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Pencere kolu alır.|
|[IOleInPlaceActiveObjectImpl::OnDocWindowEtkinleştir](#ondocwindowactivate)|Kapsayıcının belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi haberver. ATL uygulaması S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowEtkinleştir](#onframewindowactivate)|Kapsayıcının üst düzey çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi haberver. ATL uygulaması döndürür|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Sınırlarını yeniden boyutlandırmak için ihtiyaç duyduğu denetimi bildirir. ATL uygulaması S_OK döndürür.|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Kapsayıcıdan menü hızlandırıcı anahtar iletilerini işler. ATL uygulaması E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject) arabirimi yerinde denetim ve kapsayıcı arasındaki iletişimi yardımcı olur; örneğin, denetim ve kapsayıcının etkin durumunu iletmek ve kendisini yeniden boyutlandırmak için ihtiyaç duyduğu denetimi bildirmek. Sınıf `IOleInPlaceActiveObjectImpl` varsayılan bir `IOleInPlaceActiveObject` uygulama `IUnknown` sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek destekler.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

İçeriğe duyarlı yardımı sağlar.

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleWindow::ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) windows SDK içinde.

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a>IOleInPlaceActiveObjectImpl::EnableModeless

Modeless iletişim kutularını etkinleştirin.

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceActiveObject::Windows SDK'da Modemodless'ı etkinleştirin.](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a>IOleInPlaceActiveObjectImpl::GetWindow

Kapsayıcı, denetimin pencere tutamacını almak için bu işlevi çağırır.

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Açıklamalar

Bazı kapsayıcılar, şu anda pencereli olsa bile penceresiz olan bir denetimle çalışmaz. ATL'nin uygulamasında, `CComControl::m_bWasOnceWindowless` veri üyesi TRUE ise, işlev E_FAIL döndürür. Aksi \* takdirde, *phwnd* NULL `GetWindow` değilse, denetim sınıfının veri üyesine `m_hWnd` *phwnd* atar ve S_OK döndürür.

Bkz. [IOleWindow::Windows](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) SDK'daki GetWindow.

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a>IOleInPlaceActiveObjectImpl::OnDocWindowEtkinleştir

Kapsayıcının belge penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi haberver.

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceActiveObject::OnDocWindowWindows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) SDK'da etkinleştirin.

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a>IOleInPlaceActiveObjectImpl::OnFrameWindowEtkinleştir

Kapsayıcının üst düzey çerçeve penceresi etkinleştirildiğinde veya devre dışı bırakıldığında denetimi haberver.

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceActiveObject::OnFrameWindowWindows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) SDK'da etkinleştirin.

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a>IOleInPlaceActiveObjectImpl::ResizeBorder

Sınırlarını yeniden boyutlandırmak için ihtiyaç duyduğu denetimi bildirir.

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceActiveObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) SDK'da ResizeBorder.

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a>IOleInPlaceActiveObjectImpl::TranslateAccelerator

Kapsayıcıdan menü hızlandırıcı anahtar iletilerini işler.

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem aşağıdaki iade değerlerini destekler:

İleti başarılı bir şekilde tercüme edilip S_OK.

İleti çevrilmediyse S_FALSE.

### <a name="remarks"></a>Açıklamalar

Bkz. [IOleInPlaceActiveObject::Windows](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) SDK'da TranslateAccelerator.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX Arayüzleri Kontrol Eder](/windows/win32/com/activex-controls-interfaces)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
