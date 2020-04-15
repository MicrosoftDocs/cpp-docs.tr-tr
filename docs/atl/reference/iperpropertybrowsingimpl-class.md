---
title: IPerPropertyBrowsingImpl Sınıfı
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
ms.openlocfilehash: f8fb80cc38e775b9b26afa033647faac694e968a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326510"
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl Sınıfı

Bu sınıf, `IUnknown` istemcinin nesnenin özellik sayfalarındaki bilgilere erişmesine izin verir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPerPropertyBrowsingImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Belirli bir özelliği açıklayan bir dize alır.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Belirli bir özelliğin kabul edebileceği değerlere karşılık gelen bir dizi dize alır.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Belirli bir DISPID tarafından tanımlanan bir özelliğin değerini içeren bir VARYANT alır. DISPID, 'den `GetPredefinedStrings`alınan dize adı ile ilişkilidir. ATL uygulaması E_NOTIMPL döndürür.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Belirli bir özellik ile ilişkili özellik sayfasının CLSID alır.|

## <a name="remarks"></a>Açıklamalar

[IPerPropertyBrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) arabirimi, istemcinin bir nesnenin özellik sayfalarındaki bilgilere erişmesine olanak tanır. Sınıf `IPerPropertyBrowsingImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

> [!NOTE]
> Kapsayıcı uygulaması olarak Microsoft Access kullanıyorsanız, sınıfınızı `IPerPropertyBrowsingImpl`. Aksi takdirde, Access denetiminizi yüklemez.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a>IPerPropertyBrowsingImpl::GetDisplayString

Belirli bir özelliği açıklayan bir dize alır.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPerPropertyBrowsing::Windows](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) SDK'da GetDisplayString.

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a>IPerPropertyBrowsingImpl::GetPredefinedStrings

Her diziyi sıfır öğeyle doldurur.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Dönüş Değeri

ATL'nin [GetPredefinedValue](#getpredefinedvalue) uygulaması E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPerPropertyBrowsing::Windows SDK'da GetPredefinedStrings.](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings)

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a>IPerPropertyBrowsingImpl::GetPredefinedValue

Belirli bir DISPID tarafından tanımlanan bir özelliğin değerini içeren bir VARYANT alır. DISPID, 'den `GetPredefinedStrings`alınan dize adı ile ilişkilidir.

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

ATL'nin [GetPredefinedStrings](#getpredefinedstrings) uygulaması karşılık gelen dizeleri almaz.

Bkz. [IPerPropertyBrowsing::GetPredefinedValue](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) Windows SDK içinde.

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a>IPerPropertyBrowsingImpl::MapPropertyToPage

Belirtilen özellik ile ilişkili özellik sayfasının CLSID alır.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri elde etmek için nesnenin özellik eşlemi kullanır.

Bkz. [IPerPropertyBrowsing::MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPageImpl Sınıfı](../../atl/reference/ipropertypageimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
