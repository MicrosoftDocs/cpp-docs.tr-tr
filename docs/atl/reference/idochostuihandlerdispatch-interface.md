---
title: IDocHostUIHandlerDispatch Arabirimi
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: b7072b80b738aa12635427a2604b38fb3585b452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329717"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch Arabirimi

Microsoft HTML ayrıştma ve işleme altyapısına bir arayüz.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

> [!NOTE]
> Aşağıdaki tablodaki bağlantılar [IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\)) arabiriminin üyeleri için INet SDK başvuru konularına yöneliktir. `IDocHostUIHandlerDispatch`ile aynı işlevsellik vardır `IDocUIHostHandler`, `IDocHostUIHandlerDispatch` bir dispinterface olan `IDocUIHostHandler` fark ile ise özel bir arayüzdür.

|||
|-|-|
|[EtkinModuz](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|[IOleInPlaceActiveObject](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)MSHTML uygulamasından çağrılan:EnableModeless . MSHTML modal UI görüntülediğinde de adlandırılır.|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|Ana bilgisayara MSHTML'nin veri nesnesini değiştirmesine izin vermek için MSHTML tarafından ana bilgisayara çağrılır.|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|Ana bilgisayar alternatif bir [IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)sağlamak için izin vermek için bir damla hedef olarak kullanılıyor mshtml tarafından çağrılır.|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|Ana bilgisayarI'nın IDispatch arabirimini elde etmek için MSHTML tarafından çağrılır.|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML ana bilgisayarlarının UI özelliklerini alır.|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|MSHTML'nin kullanıcı tercihlerini depoladığı kayıt defteri anahtarını döndürür.|
|[HideUi](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|MSHTML menülerini ve araç çubuklarını kaldırdığında çağrılır.|
|[OndocWindowEtkinleştir](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|[IOleInPlaceActiveObject MSHTML uygulamasından çağrılan::OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate).|
|[OnFrameWindowEtkinleştir](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|[IOleInPlaceActiveObject MSHTML uygulamasından çağrılan::OnFrameWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate).|
|[Yeniden BoyutlandırmaSınırı](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|[IOleInPlaceActiveObject](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder)MSHTML uygulamasından çağrılan:ResizeBorder .|
|[Showcontextmenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|Bağlam menüsünü görüntülemek için MSHTML'den çağrılır.|
|[Showuı](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|Ana bilgisayarA MSHTML menüleri ve araç çubukları değiştirmesini sağlar.|
|[Translateaccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|[IOleInPlaceActiveObject::TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) veya [IOleControlSite::TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator) denir.|
|[ÇeviriUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|MsHTML tarafından çağrılan ev sahibiyüklenecek URL'yi değiştirmek için bir fırsat.|
|[UpdateUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|Ana bilgisayara komut durumunun değiştiğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Ana bilgisayar, bu arabirimi uygulayarak Microsoft HTML ayrıştırma ve işleme altyapısı (MSHTML) tarafından kullanılan menüleri, araç çubuklarını ve bağlam menülerini değiştirebilir.

## <a name="requirements"></a>Gereksinimler

Bu arabirimin tanımı aşağıda gösterildiği gibi IDL veya C++ olarak kullanılabilir.

|Tanım türü|Dosya|
|---------------------|----------|
|ıdl|ATLIFace.idl|
|C++|ATLIFace.h (Ayrıca ATLBase.h dahil)|

## <a name="see-also"></a>Ayrıca bkz.

[IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
