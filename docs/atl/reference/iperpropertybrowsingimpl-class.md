---
title: Iperpropertybrowsingımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: 54c475e736425718e954b0e954ea2b327d938556
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299467"
---
# <a name="iperpropertybrowsingimpl-class"></a>Iperpropertybrowsingımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve bir istemci bir nesnenin özellik sayfalarındaki bilgilere erişmesine izin verir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IPerPropertyBrowsingImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Belirli bir özelliğe açıklayan bir dize alır.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Belirli bir özelliğe kabul edebilen değerlere karşılık gelen bir dize dizisi alır.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Belirli bir DISPID tarafından tanımlanan bir özellik değerini içeren bir değişken alır. DISPID hizmetinden alınan dize adı ilişkilendirilmiş olan `GetPredefinedStrings`. ATL uygulamasını E_NOTIMPL döndürür.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Verilen bir özellik ile ilişkili özellik sayfası CLSID değeri alır.|

## <a name="remarks"></a>Açıklamalar

[IPerPropertyBrowsing](/windows/desktop/api/ocidl/nn-ocidl-iperpropertybrowsing) bir istemci, bir nesnenin özellik sayfalarındaki bilgilere erişmek arabirim sağlar. Sınıf `IPerPropertyBrowsingImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

> [!NOTE]
>  Kapsayıcı uygulaması Microsoft Access kullanıyorsanız, sizin sınıfınızdan türetilmelidir `IPerPropertyBrowsingImpl`. Aksi takdirde, erişim denetim yüklemez.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString

Belirli bir özelliğe açıklayan bir dize alır.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPerPropertyBrowsing::GetDisplayString](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) Windows SDK içinde.

##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings

Her dizi öğeleri sıfır ile doldurur.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Dönüş Değeri

ATL uygulamasını [GetPredefinedValue](#getpredefinedvalue) E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IPerPropertyBrowsing::GetPredefinedStrings öğesini](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) Windows SDK içinde.

##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue

Belirli bir DISPID tarafından tanımlanan bir özellik değerini içeren bir değişken alır. DISPID hizmetinden alınan dize adı ilişkilendirilmiş olan `GetPredefinedStrings`.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

ATL uygulamasını [GetPredefinedStrings](#getpredefinedstrings) karşılık gelen koşulsuz alır.

Bkz: [IPerPropertyBrowsing::GetPredefinedValue](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) Windows SDK içinde.

##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage

Belirtilen özellik ile ilişkili özellik sayfası CLSID değeri alır.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri almak için nesnenin özellik eşlemesi kullanır.

Bkz: [IPerPropertyBrowsing::MapPropertyToPage](/windows/desktop/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPageImpl Sınıfı](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
