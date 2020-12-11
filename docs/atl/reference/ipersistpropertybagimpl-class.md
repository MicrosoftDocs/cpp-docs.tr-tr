---
description: ': Ipersistpropertybagimpl sınıfı hakkında daha fazla bilgi'
title: Ipersistpropertybagimpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: 1e244c4349bd04a83d257280da3315f2c797003a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158172"
---
# <a name="ipersistpropertybagimpl-class"></a>Ipersistpropertybagimpl sınıfı

Bu sınıf `IUnknown` , bir nesnenin özelliklerini istemci tarafından sağlanan özellik paketine kaydetmesine izin verir ve uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPersistPropertyBagImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ipersistpropertybagimpl:: GetClassID](#getclassid)|Nesnenin CLSID 'sini alır.|
|[Ipersistpropertybagimpl:: InitNew](#initnew)|Yeni oluşturulan bir nesneyi başlatır. ATL uygulama S_OK döndürür.|
|[Ipersistpropertybagimpl:: Load](#load)|İstemcinin sağladığı Özellik çantasından nesnenin özelliklerini yükler.|
|[Ipersistpropertybagimpl:: Save](#save)|Nesnenin özelliklerini, istemci tarafından sağlanan bir özellik paketine kaydeder.|

## <a name="remarks"></a>Açıklamalar

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) arabirimi bir nesnenin özelliklerini istemci tarafından sağlanan bir özellik paketine kaydetmesine izin verir. Sınıfı, `IPersistPropertyBagImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

`IPersistPropertyBag`[IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) ve [Ihata günlüğü](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\))ile birlikte çalışarak. Bu ikinci iki arabirimin istemci tarafından uygulanması gerekir. Aracılığıyla `IPropertyBag` , istemci nesnenin ayrı özelliklerini kaydeder ve yükler. Aracılığıyla `IErrorLog` , hem nesne hem de istemci karşılaşılan hataları bildirebilir.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a> Ipersistpropertybagimpl:: GetClassID

Nesnenin CLSID 'sini alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IPersist:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) .

## <a name="ipersistpropertybagimplinitnew"></a><a name="initnew"></a> Ipersistpropertybagimpl:: InitNew

Yeni oluşturulan bir nesneyi başlatır.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IPersistPropertyBag:: InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) .

## <a name="ipersistpropertybagimplload"></a><a name="load"></a> Ipersistpropertybagimpl:: Load

İstemcinin sağladığı Özellik çantasından nesnenin özelliklerini yükler.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Açıklamalar

ATL bu bilgileri almak için nesnenin özellik eşlemesini kullanır.

Windows SDK [IPersistPropertyBag:: Load](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) öğesine bakın.

## <a name="ipersistpropertybagimplsave"></a><a name="save"></a> Ipersistpropertybagimpl:: Save

Nesnenin özelliklerini, istemci tarafından sağlanan bir özellik paketine kaydeder.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Açıklamalar

ATL bu bilgileri depolamak için nesnenin özellik eşlemesini kullanır. Varsayılan olarak, bu yöntem *fSaveAllProperties* değerinden bağımsız olarak tüm özellikleri kaydeder.

Windows SDK [IPersistPropertyBag:: Save](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
