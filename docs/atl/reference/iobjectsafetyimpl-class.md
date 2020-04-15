---
title: IObjectSafetyImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: 6eee7585bc3c5587e106ab6b0cefb4b7129df59f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329658"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl Sınıfı

Bu sınıf, istemcinin `IObjectSafety` nesnenin güvenlik düzeylerini alıp ayarlamasına izin vermek için arabirimin varsayılan uygulamasını sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IObjectSafetyImpl`türetilmiştir.

*dwDestekliGüvenlik*<br/>
Kontrol için desteklenen güvenlik seçeneklerini belirtir. Aşağıdaki değerlerden biri olabilir:

- INTERFACESAFE_FOR_UNTRUSTED_CALLER [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) parametresi `riid` tarafından tanımlanan arabirim komut dosyası için güvenli hale getirilmelidir.

- INTERFACESAFE_FOR_UNTRUSTED_DATA `SetInterfaceSafetyOptions` Parametre `riid` tarafından tanımlanan arabirim, başlatma sırasında güvenilmeyen veriler için güvenli hale getirilmelidir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Nesne tarafından desteklenen güvenlik seçeneklerinin yanı sıra nesne için şu anda ayarlanan güvenlik seçeneklerini de alır.|
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Nesneyi başlatma veya komut dosyası için güvenli hale getirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Nesnenin geçerli güvenlik düzeyini depolar.|

## <a name="remarks"></a>Açıklamalar

Sınıf `IObjectSafetyImpl` varsayılan bir `IObjectSafety`uygulama sağlar. Arabirim, `IObjectSafety` istemcinin nesnenin güvenlik düzeylerini almasına ve ayarlamasına olanak tanır. Örneğin, bir web tarayıcısı, bir denetimi başlatma için güvenli veya komut dosyası için güvenli hale getirmek için arayabilir. `IObjectSafety::SetInterfaceSafetyOptions`

[IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) makroyu CATID_SafeForScripting ve CATID_SafeForInitializing bileşen kategorileriyle kullanmanın, bileşenin güvenli olduğunu belirtmenin alternatif bir yolu olduğunu unutmayın.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions

Nesne tarafından desteklenen güvenlik seçeneklerinin yanı sıra nesne için şu anda ayarlanan güvenlik seçeneklerini de alır.

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>Açıklamalar

Uygulama, nesnenin uygulanması tarafından desteklenen herhangi bir arabirim `IUnknown::QueryInterface`için uygun değerleri döndürür.

> [!IMPORTANT]
> Destekleyen `IObjectSafety` herhangi bir nesne kendi güvenliğinden ve devrettiği herhangi bir nesneden sorumludur. Programcı, kullanıcı bağlamında kod çalıştıran, site arası komut dosyası oluşturma dan kaynaklanan sorunları dikkate almak ve uygun bölge denetimi gerçekleştirmek gerekir.

Bkz. [IObjectSafety::Windows](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) SDK'da GetInterfaceSafetyOptions.

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety

Nesnenin geçerli güvenlik düzeyini depolar.

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions

[m_dwCurrentSafety](#m_dwcurrentsafety) üyeyi uygun değere ayarlayarak nesneyi başlatma veya komut dosyası oluşturma için güvenli hale getirir.

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>Açıklamalar

Uygulama, nesnenin uygulanması tarafından desteklenmeyen herhangi bir `IUnknown::QueryInterface`arabirim için E_NOINTERFACE döndürür.

> [!IMPORTANT]
> Destekleyen `IObjectSafety` herhangi bir nesne kendi güvenliğinden ve devrettiği herhangi bir nesneden sorumludur. Programcı, kullanıcı bağlamında kod çalıştıran, site arası komut dosyası oluşturma dan kaynaklanan sorunları dikkate almak ve uygun bölge denetimi gerçekleştirmek gerekir.

Bkz. [IObjectSafety::SetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[IObjectSafety Arayüzü](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
