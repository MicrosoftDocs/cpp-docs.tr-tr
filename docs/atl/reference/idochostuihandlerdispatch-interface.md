---
description: 'Şu konuda daha fazla bilgi edinin: ıdochostuihandlerdispatch Interface'
title: Idochostuihandlerdispatch arabirimi
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: 59f9975f48a7ae63d5820a9c05f9baa49b8a5f25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158380"
---
# <a name="idochostuihandlerdispatch-interface"></a>Idochostuihandlerdispatch arabirimi

Microsoft HTML ayrıştırma ve işleme motoruna bir arabirim.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

> [!NOTE]
> Aşağıdaki tablodaki bağlantılar, [ıdocuihosthandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) arabiriminin üyeleri Için INet sdk başvuru konularına yöneliktir. `IDocHostUIHandlerDispatch``IDocUIHostHandler`, bir dispınterface olan farkla aynı işlevselliğe sahiptir, `IDocHostUIHandlerDispatch` ancak `IDocUIHostHandler` özel bir arabirimdir.

|Ad|Açıklama|
|-|-|
|[Enablemodsuz](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|[IOleInPlaceActiveObject:: Enablemodin](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)MSHTML uygulamasından çağırılır. Ayrıca, MSHTML kalıcı Kullanıcı arabirimini görüntülediğinde de çağrılır.|
|[Filtredataobject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Ana bilgisayarın MSHTML 'nin veri nesnesini değiştirmesine izin vermek için MSHTML tarafından konakta çağırılır.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Ana bilgisayarın alternatif bir [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)sağlaması için bırakma hedefi olarak kullanıldığında MSHTML tarafından çağırılır.|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Konağın IDispatch arabirimini almak için MSHTML tarafından çağırılır.|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML konağının Kullanıcı arabirimi yeteneklerini alır.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|MSHTML 'nin Kullanıcı tercihlerini sakladığı kayıt defteri anahtarını döndürür.|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|MSHTML, menülerini ve araç çubuklarını kaldırdığında çağırılır.|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|[IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate)'ın MSHTML uygulamasından çağırılır.|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|[IOleInPlaceActiveObject:: OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate)MSHTML uygulamasından çağırılır.|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|[IOleInPlaceActiveObject:: ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder)'in MSHTML uygulamasından çağırılır.|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Bir bağlam menüsünü göstermek için MSHTML 'den çağırılır.|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|Konağın MSHTML menülerini ve araç çubuklarını değiştirmesine izin verir.|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|[IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) veya [IOleControlSite:: TRANSLATEACCELERATOR](/windows/win32/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) çağrıldığında, MSHTML tarafından çağırılır.|
|[TranslateUrl 'Si](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|Konağa yüklenecek URL 'YI değiştirme olanağı sağlamak için MSHTML tarafından çağırılır.|
|[UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Ana bilgisayara komut durumunun değiştiğini bildirir.|

## <a name="remarks"></a>Açıklamalar

Bir ana bilgisayar, bu arabirimi uygulayarak Microsoft HTML ayrıştırma ve işleme altyapısı (MSHTML) tarafından kullanılan menülerin, araç çubuklarının ve bağlam menülerinin yerini alabilir.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|IDL|Atlıyüz. IDL|
|C++|Atlıyüz. h (ATLBase. h 'ye de dahildir)|

## <a name="see-also"></a>Ayrıca bkz.

[Idocuihosthandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
