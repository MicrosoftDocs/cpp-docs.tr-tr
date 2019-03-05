---
title: Idochostuıhandlerdispatch arabirimi
ms.date: 11/04/2016
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: 0652801d7ad80ba53716299e3919f5b432de855a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293153"
---
# <a name="idochostuihandlerdispatch-interface"></a>Idochostuıhandlerdispatch arabirimi

Bir arabirim Microsoft HTML Ayrıştırma ve işleme altyapısı.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

> [!NOTE]
>  Aşağıdaki tabloda bağlantıları üyelerinin INet SDK başvuru konusundan üzeresiniz [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx) arabirimi. `IDocHostUIHandlerDispatch` aynı işlevlere sahip `IDocUIHostHandler`, olan farkla `IDocHostUIHandlerDispatch` bir dispinterface takvimidir `IDocUIHostHandler` özel bir arabirimdir.

|||
|-|-|
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Kalıcı kullanıcı Arabirimi MSHTML görüntüler de çağrılır.|
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|Konak MSHTML'ın veri nesnesi değiştirmeye izin vermek için MSHTML konağıyla üzerinde çağrılır.|
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|Bir bırakma hedefi alternatif sağlamak konak izin vermek için kullanılan MSHTML tarafından çağırılır [ıdroptarget'ı](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|Ana bilgisayarın IDispatch almak için MSHTML tarafından çağrılır.|
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|MSHTML konak kullanıcı Arabirimi özelliklerini alır.|
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|Kullanıcı tercihleri depolayan MSHTML altında kayıt defteri anahtarını döndürür.|
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|MSHTML, menüleri ve araç çubuklarını kaldırdığında çağrılır.|
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|Bir bağlam menüsünü görüntülemek için MSHTML çağrılır.|
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|MSHTML menüleri ve araç çubuklarını değiştirmek konak sağlar.|
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|MSHTML tarafından çağrılır, [IOleInPlaceActiveObject::TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) veya [IOleControlSite::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) çağrılır.|
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|Konak yüklenecek URL'sini değiştirmek için bir fırsat izin vermek için MSHTML tarafından çağrılır.|
|[UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)|Konak, komut durumu değiştirildiğinde bildirir.|

## <a name="remarks"></a>Açıklamalar

Bir konak, menüleri, araç çubukları ve bu arabirimi uygulayan Microsoft HTML Ayrıştırma ve işleme altyapısı (MSHTML) tarafından kullanılan bağlam menüleri değiştirebilirsiniz.

## <a name="requirements"></a>Gereksinimler

Bu arabirim tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|ATLIFace.h (ATLBase.h içinde de dahil)|

## <a name="see-also"></a>Ayrıca bkz.

[IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)
