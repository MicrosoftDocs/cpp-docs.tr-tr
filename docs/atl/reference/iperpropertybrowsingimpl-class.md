---
description: 'Daha fazla bilgi edinin: ıperpropertybrowsingimpl sınıfı'
title: Iperpropertybrowsingimpl sınıfı
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
ms.openlocfilehash: eba17c0011343f50f586b13086dc76229f08ba3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139353"
---
# <a name="iperpropertybrowsingimpl-class"></a>Iperpropertybrowsingimpl sınıfı

Bu sınıf `IUnknown` , bir istemcinin bir nesnenin özellik sayfalarındaki bilgilere erişmesine izin verir ve uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPerPropertyBrowsingImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iperpropertybrowsingimpl:: GetDisplayString](#getdisplaystring)|Verilen bir özelliği açıklayan bir dize alır.|
|[Iperpropertybrowsingimpl:: GetPredefinedStrings](#getpredefinedstrings)|Verilen bir özelliğin kabul edebileceği değerlere karşılık gelen dizelerin dizisini alır.|
|[Iperpropertybrowsingimpl:: GetPredefinedValue](#getpredefinedvalue)|Verilen bir DISPID tarafından tanımlanan bir özelliğin değerini içeren bir DEĞIŞKEN alır. DISPID, öğesinden alınan dize adıyla ilişkilendirilir `GetPredefinedStrings` . ATL uygulama E_NOTIMPL döndürür.|
|[Iperpropertybrowsingimpl:: MapPropertyToPage](#mappropertytopage)|Belirli bir özellikle ilişkili özellik sayfasının CLSID değerini alır.|

## <a name="remarks"></a>Açıklamalar

[Iperpropertygözatma](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) arabirimi, bir istemcinin bir nesnenin özellik sayfalarındaki bilgilere erişmesine izin verir. Sınıfı, `IPerPropertyBrowsingImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

> [!NOTE]
> Kapsayıcı uygulama olarak Microsoft Access kullanıyorsanız, sınıfınızı ' den türetmeniz gerekir `IPerPropertyBrowsingImpl` . Aksi takdirde, erişim denetiminizi yüklemez.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a> Iperpropertybrowsingimpl:: GetDisplayString

Verilen bir özelliği açıklayan bir dize alır.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [ıperpropertygözatılıyor:: GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) .

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a> Iperpropertybrowsingimpl:: GetPredefinedStrings

Her diziyi sıfır öğe ile doldurur.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Dönüş Değeri

ATL 'nin [GetPredefinedValue](#getpredefinedvalue) uygulamasının uygulanması E_NOTIMPL döndürüyor.

### <a name="remarks"></a>Açıklamalar

Windows SDK [ıperpropertygözatımı:: GetPredefinedStrings](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) öğesine bakın.

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a> Iperpropertybrowsingimpl:: GetPredefinedValue

Verilen bir DISPID tarafından tanımlanan bir özelliğin değerini içeren bir DEĞIŞKEN alır. DISPID, öğesinden alınan dize adıyla ilişkilendirilir `GetPredefinedStrings` .

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

ATL 'nin [Getpredefineddizeler](#getpredefinedstrings) uygulamasına karşılık gelen dizeler alınmaz.

Windows SDK bkz. [ıperpropertygözatımı:: GetPredefinedValue](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) .

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a> Iperpropertybrowsingimpl:: MapPropertyToPage

Belirtilen özellikle ilişkili özellik sayfasının CLSID değerini alır.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri almak için nesnenin özellik eşlemesini kullanır.

Windows SDK, bkz. [ıperpropertygözatımı:: MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) .

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPageImpl sınıfı](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Idiifyıpropertypagesimpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
