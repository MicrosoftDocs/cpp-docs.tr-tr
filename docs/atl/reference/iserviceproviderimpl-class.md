---
description: 'Şu konuda daha fazla bilgi edinin: Iservıceproviderımpl sınıfı'
title: IServiceProviderImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: 0cd9fab784fe8bffe420123129aa51c80c187890
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139158"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl sınıfı

Bu sınıf, arabirimin varsayılan bir uygulamasını sağlar `IServiceProvider` .

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IServiceProviderImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IServiceProviderImpl:: QueryService](#queryservice)|Belirtilen hizmeti oluşturur veya erişir ve hizmet için belirtilen arabirime bir arabirim işaretçisi döndürür.|

## <a name="remarks"></a>Açıklamalar

`IServiceProvider`Arabirim, GUID 'si tarafından belirtilen bir hizmeti bulur ve hizmette istenen arabirim için arabirim işaretçisini döndürür. Sınıfı `IServiceProviderImpl` , bu arabirimin varsayılan bir uygulamasını sağlar.

`IServiceProviderImpl` belirtilen hizmeti oluşturan veya erişen ve hizmet için belirtilen arabirime bir arabirim işaretçisi döndüren bir yöntemi belirtir: [QueryService](#queryservice).

`IServiceProviderImpl`[BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) başlayıp [END_SERVICE_MAP](service-map-macros.md#end_service_map)ile biten bir hizmet eşlemesi kullanır.

Hizmet eşlemesi iki girdi içerir: [SERVICE_ENTRY](service-map-macros.md#service_entry), nesne tarafından desteklenen belirtilen hizmet KIMLIĞINI (SID) ve [](service-map-macros.md#service_entry_chain) `QueryService` başka bir nesneye zincirye çağıran SERVICE_ENTRY_CHAIN.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a> IServiceProviderImpl:: QueryService

Belirtilen hizmeti oluşturur veya erişir ve hizmet için belirtilen arabirime bir arabirim işaretçisi döndürür.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*guidService*<br/>
'ndaki Hizmet tanımlayıcısına (SID) yönelik işaretçi.

*riıd*<br/>
'ndaki Çağıranın erişim kazanabileceği arabirimin tanımlayıcısı.

*ppvObj*<br/>
dışı İstenen arabirime dolaylı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürülen HRESULT değeri aşağıdakilerden biridir:

|Döndürülen değer|Anlamı|
|------------------|-------------|
|S_OK|Hizmet başarıyla oluşturuldu veya alındı.|
|E_INVALIDARG|Bağımsız değişkenlerden biri veya birkaçı geçersiz.|
|E_OUTOFMEMORY|Bellek, hizmeti oluşturmak için yeterli değil.|
|E_UNEXPECTED|Bilinmeyen bir hata oluştu.|
|E_NOINTERFACE|İstenen arabirim bu hizmetin bir parçası değil veya hizmet bilinmiyor.|

### <a name="remarks"></a>Açıklamalar

`QueryService` belirtilen hizmette istenen arabirime dolaylı bir işaretçi döndürür. Çağıran, Bu işaretçinin artık gerekli olmadığı durumlarda serbest bırakılmasından sorumludur.

`QueryService`' İ çağırdığınızda, hem bir hizmet tanımlayıcısı (*guidService*) hem de arabirim tanımlayıcısı (*riıd*) iletirsiniz. *GuidService* , erişmek istediğiniz hizmeti belirtir ve *riıd* hizmetin bir parçası olan bir arabirimi tanımlar. Sonuç olarak, arabirime dolaylı bir işaretçi alırsınız.

Arabirimi uygulayan nesne, diğer hizmetlerin parçası olan arabirimleri de uygulayabilir. Aşağıdaki topluluklara bir göz atın:

- Bu arabirimlerin bazıları isteğe bağlı olabilir. Hizmet açıklamasında tanımlanmış arabirimlerin hepsi hizmetin her uygulamasında veya döndürülen tüm nesneler üzerinde bulunmalıdır.

- ' A yapılan çağrıların aksine `QueryInterface` , farklı bir hizmet tanımlayıcısının geçirilmesi farklı bir bileşen nesne modeli (com) nesnesinin döndürüldüğü anlamına gelmez.

- Döndürülen nesne, hizmet tanımının bir parçası olmayan ek arabirimlere sahip olabilir.

SID_SMyService ve SID_SYourService gibi iki farklı hizmet, her ikisi de aynı arabirimin kullanımını belirtebilir, ancak bu, arabirimin uygulanması iki hizmet arasında ortak hiçbir şey yapmayabilir. Bu, `QueryService` (SID_SMyService, IID_IDispatch) öğesine yapılan bir çağrı ( `QueryService` SID_SYourService, IID_IDispatch) öğesinden farklı bir nesne döndürebileceğinden, bu işe yarar. Farklı bir hizmet tanımlayıcısı belirttiğinizde nesne kimliği kabul edilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
