---
title: IPersistPropertyBagImpl Sınıfı
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
ms.openlocfilehash: f656ecc76b175eae523059c60bb8a3efc6f0b312
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326482"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl Sınıfı

Bu sınıf, `IUnknown` bir nesnenin özelliklerini istemci tarafından sağlanan özellik çantasına kaydetmesine olanak tanır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPersistPropertyBagImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Nesnenin CLSID'sini alır.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|Yeni oluşturulan bir nesneyi başharfe ait hale leştirir. ATL uygulaması S_OK döndürür.|
|[IPersistPropertyBagImpl::Yük](#load)|Nesnenin özelliklerini istemci tarafından sağlanan bir özellik çantasından yükler.|
|[IPersistPropertyBagImpl::Kaydet](#save)|Nesnenin özelliklerini istemci tarafından sağlanan bir özellik çantasına kaydeder.|

## <a name="remarks"></a>Açıklamalar

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) arabirimi, bir nesnenin özelliklerini istemci tarafından sağlanan özellik çantasına kaydetmesine olanak tanır. Sınıf `IPersistPropertyBagImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

`IPersistPropertyBag`[IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) ve [iErrorLog](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\))ile birlikte çalışır. Bu son iki arabirim istemci tarafından uygulanmalıdır. Bu `IPropertyBag`nedenle, istemci nesnenin tek tek özelliklerini kaydeder ve yükler. Aracılığıyla, `IErrorLog`hem nesne hem de istemci karşılaşılan hataları bildirebilir.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ipersistpropertybagimplgetclassid"></a><a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID

Nesnenin CLSID'sini alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IPersist::Windows SDK'da [ClassID'yi alın.](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid)

## <a name="ipersistpropertybagimplinitnew"></a><a name="initnew"></a>IPersistPropertyBagImpl::InitNew

Yeni oluşturulan bir nesneyi başharfe ait hale leştirir.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPersistPropertyBag::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) SDK'da Yeni.

## <a name="ipersistpropertybagimplload"></a><a name="load"></a>IPersistPropertyBagImpl::Yük

Nesnenin özelliklerini istemci tarafından sağlanan bir özellik çantasından yükler.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Açıklamalar

ATL bu bilgileri almak için nesnenin özellik eşlemi kullanır.

Bkz. [IPersistPropertyBag::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) SDK'da yükleyin.

## <a name="ipersistpropertybagimplsave"></a><a name="save"></a>IPersistPropertyBagImpl::Kaydet

Nesnenin özelliklerini istemci tarafından sağlanan bir özellik çantasına kaydeder.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri depolamak için nesnenin özellik eşlesini kullanır. Varsayılan olarak, bu *yöntem, fSaveAllProperties*değeri ne olursa olsun tüm özellikleri kaydeder.

Bkz. [IPersistPropertyBag::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) SDK'da kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
