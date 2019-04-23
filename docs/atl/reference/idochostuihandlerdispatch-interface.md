---
title: Idochostuıhandlerdispatch arabirimi
ms.date: 11/04/2016
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: 6ce3532e99dc1d0ff0151285766aa5d78c2b9e9d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421888"
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
|[EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless). Kalıcı kullanıcı Arabirimi MSHTML görüntüler de çağrılır.|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Konak MSHTML'ın veri nesnesi değiştirmeye izin vermek için MSHTML konağıyla üzerinde çağrılır.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Bir bırakma hedefi alternatif sağlamak konak izin vermek için kullanılan MSHTML tarafından çağırılır [ıdroptarget'ı](/windows/desktop/api/oleidl/nn-oleidl-idroptarget).|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Ana bilgisayarın IDispatch almak için MSHTML tarafından çağrılır.|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML konak kullanıcı Arabirimi özelliklerini alır.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|Kullanıcı tercihleri depolayan MSHTML altında kayıt defteri anahtarını döndürür.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|MSHTML, menüleri ve araç çubuklarını kaldırdığında çağrılır.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::OnDocWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::OnFrameWindowActivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|MSHTML uygulamasından adlı [IOleInPlaceActiveObject::ResizeBorder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder).|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Bir bağlam menüsünü görüntülemek için MSHTML çağrılır.|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|MSHTML menüleri ve araç çubuklarını değiştirmek konak sağlar.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|MSHTML tarafından çağrılır, [IOleInPlaceActiveObject::TranslateAccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) veya [IOleControlSite::TranslateAccelerator](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) çağrılır.|
|[TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|Konak yüklenecek URL'sini değiştirmek için bir fırsat izin vermek için MSHTML tarafından çağrılır.|
|[UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Konak, komut durumu değiştirildiğinde bildirir.|

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
