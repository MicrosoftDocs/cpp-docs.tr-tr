---
description: 'Daha fazla bilgi edinin: IObjectSafetyImpl sınıfı'
title: IObjectSafetyImpl sınıfı
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
ms.openlocfilehash: ac19fe24d12d7d09968b3e2d76f77741e83e1f81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139470"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl sınıfı

Bu sınıf, `IObjectSafety` bir istemcinin bir nesnenin güvenlik düzeylerini almasına ve ayarlamaya olanak tanımak için arabirimin varsayılan bir uygulamasını sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IObjectSafetyImpl` .

*dwSupportedSafety*<br/>
Denetim için desteklenen güvenlik seçeneklerini belirtir. Aşağıdaki değerlerden biri olabilir:

- INTERFACESAFE_FOR_UNTRUSTED_CALLER [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) parametresi tarafından tanımlanan arabirimin `riid` betik oluşturma için güvenli hale getirilmeleri gerekir.

- INTERFACESAFE_FOR_UNTRUSTED_DATA parametresi tarafından tanımlanan arabirim, `SetInterfaceSafetyOptions` `riid` başlatma sırasında güvenilmeyen veriler için güvenli hale getirilmelidir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IObjectSafetyImpl:: Getınterfacesafetyoptions](#getinterfacesafetyoptions)|Nesnesi tarafından desteklenen güvenlik seçeneklerini ve nesne için şu anda ayarlanmış olan güvenlik seçeneklerini alır.|
|[IObjectSafetyImpl:: SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Nesneyi başlatma veya komut dosyası oluşturma için güvenli hale getirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[IObjectSafetyImpl:: m_dwCurrentSafety](#m_dwcurrentsafety)|Nesnenin geçerli güvenlik düzeyini depolar.|

## <a name="remarks"></a>Açıklamalar

Sınıfı `IObjectSafetyImpl` , varsayılan bir uygulamasını sağlar `IObjectSafety` . `IObjectSafety`Arabirim, bir istemcinin bir nesnenin güvenlik düzeylerini almasına ve ayarlamasına olanak tanır. Örneğin, bir Web tarayıcısı, `IObjectSafety::SetInterfaceSafetyOptions` bir denetimi başlatma veya güvenli hale getirme için güvenli hale getirmek üzere çağırabilir.

[IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) makrosunu CATID_SafeForScripting ve CATID_SafeForInitializing bileşen kategorilerine kullanmanın, bir bileşenin güvenli olduğunu belirtmenin alternatif bir yolunu sağladığını unutmayın.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a> IObjectSafetyImpl:: Getınterfacesafetyoptions

Nesnesi tarafından desteklenen güvenlik seçeneklerini ve nesne için şu anda ayarlanmış olan güvenlik seçeneklerini alır.

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>Açıklamalar

Uygulama, nesnesinin uygulamasının tarafından desteklenen herhangi bir arabirim için uygun değerleri döndürür `IUnknown::QueryInterface` .

> [!IMPORTANT]
> Tarafından desteklenen herhangi bir nesne `IObjectSafety` kendi güveninden ve temsilci yaptığı herhangi bir nesneden sorumludur. Programcı, kullanıcının bağlamında kod çalıştırmanın, siteler arası komut dosyası oluşturma ve uygun bölge denetimi gerçekleştirmeye kaynaklanan sorunları dikkate almalıdır.

Windows SDK bkz. ' de [IObjectSafety:: Getınterfacesafetyoptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) .

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a> IObjectSafetyImpl:: m_dwCurrentSafety

Nesnenin geçerli güvenlik düzeyini depolar.

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a> IObjectSafetyImpl:: SetInterfaceSafetyOptions

[M_dwCurrentSafety](#m_dwcurrentsafety) üyesini uygun değere ayarlayarak, nesneyi başlatma veya komut dosyası oluşturma için güvenli hale getirir.

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>Açıklamalar

Uygulama, nesnesinin uygulamasının tarafından desteklenmeyen herhangi bir arabirim için E_NOINTERFACE döndürür `IUnknown::QueryInterface` .

> [!IMPORTANT]
> Tarafından desteklenen herhangi bir nesne `IObjectSafety` kendi güveninden ve temsilci yaptığı herhangi bir nesneden sorumludur. Programcı, kullanıcının bağlamında kod çalıştırmanın, siteler arası komut dosyası oluşturma ve uygun bölge denetimi gerçekleştirmeye kaynaklanan sorunları dikkate almalıdır.

Windows SDK bkz. ' de [IObjectSafety:: SetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) .

## <a name="see-also"></a>Ayrıca bkz.

[IObjectSafety arabirimi](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
