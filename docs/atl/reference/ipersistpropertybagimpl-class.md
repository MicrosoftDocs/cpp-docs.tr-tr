---
title: Ipersistpropertybagımpl sınıfı
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
ms.openlocfilehash: 569a24fd08801de952e998f772afbc3478096628
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503140"
---
# <a name="ipersistpropertybagimpl-class"></a>Ipersistpropertybagımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve bir nesne için bir istemci tarafından sağlanan özellik paketi özelliklerini kaydetmek sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IPersistPropertyBagImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Nesnenin CLSID alır.|
|[IPersistPropertyBagImpl::InitNew](#initnew)|Yeni oluşturulan nesneyi başlatır. ATL uygulamasını S_OK döndürür.|
|[IPersistPropertyBagImpl::Load](#load)|Bir istemci tarafından sağlanan özellik paketinden nesnenin özelliklerini yükler.|
|[IPersistPropertyBagImpl::Save](#save)|Nesnenin özelliklerini bir istemci tarafından sağlanan özellik paketi kaydeder.|

## <a name="remarks"></a>Açıklamalar

[IPersistPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768205\(v=vs.85\)) bir nesne için bir istemci tarafından sağlanan özellik paketi özelliklerini kaydetmek arabirim sağlar. Sınıf `IPersistPropertyBagImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

`IPersistPropertyBag` ile birlikte çalışır [IPropertyBag](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768196\(v=vs.85\)) ve [IErrorLog](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768231\(v=vs.85\)). Bu ikinci iki arabirim istemci tarafından uygulanmalıdır. Aracılığıyla `IPropertyBag`, istemci kaydeder ve tek nesnenin özelliklerini yükler. Aracılığıyla `IErrorLog`, hem nesnenin hem de istemci karşılaşılan hataları rapor edebilirsiniz.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID

Nesnenin CLSID alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK içinde.

##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew

Yeni oluşturulan nesneyi başlatır.

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IPersistPropertyBag::InitNew](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768204\(v=vs.85\)) Windows SDK içinde.

##  <a name="load"></a>  IPersistPropertyBagImpl::Load

Bir istemci tarafından sağlanan özellik paketinden nesnenin özelliklerini yükler.

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri almak için nesnenin özellik eşlemesi kullanır.

Bkz: [IPersistPropertyBag::Load](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768206\(v=vs.85\)) Windows SDK içinde.

##  <a name="save"></a>  IPersistPropertyBagImpl::Save

Nesnenin özelliklerini bir istemci tarafından sağlanan özellik paketi kaydeder.

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>Açıklamalar

ATL nesnenin özellik eşlemesi bu bilgileri depolamak için kullanır. Varsayılan olarak, bu yöntem değerinden bağımsız olarak tüm özellikleri kaydeder *fSaveAllProperties*.

Bkz: [IPersistPropertyBag::Save](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768207\(v=vs.85\)) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
