---
title: IServiceProviderImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: ef0ee4f77441cb8d19ea2d6dcada1fed9faf2782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329424"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl Sınıfı

Bu `IServiceProvider` sınıf, arabirimin varsayılan bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IServiceProviderImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IServiceProviderImpl::QueryService](#queryservice)|Belirtilen hizmeti oluşturur veya erişir ve bir arabirim işaretçisini hizmet için belirtilen arabirime döndürür.|

## <a name="remarks"></a>Açıklamalar

Arabirim, `IServiceProvider` GUID tarafından belirtilen bir hizmeti bulur ve hizmette istenen arabirim için arabirim işaretçisini döndürür. Sınıf `IServiceProviderImpl` bu arabirimin varsayılan uygulamasını sağlar.

`IServiceProviderImpl`bir yöntem belirtir: [QueryService](#queryservice), belirtilen hizmeti oluşturur veya erişir ve hizmet için belirtilen arabirime bir arabirim işaretçisi döndürür.

`IServiceProviderImpl`[BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) başlayıp [END_SERVICE_MAP](service-map-macros.md#end_service_map)ile biten bir hizmet haritası kullanır.

Hizmet eşlemi iki giriş içerir: nesne tarafından desteklenen belirli bir hizmet id'sini `QueryService` (SID) gösteren [SERVICE_ENTRY](service-map-macros.md#service_entry)ve başka bir nesneye zincirleme çağıran [SERVICE_ENTRY_CHAIN.](service-map-macros.md#service_entry_chain)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a>IServiceProviderImpl::QueryService

Belirtilen hizmeti oluşturur veya erişir ve bir arabirim işaretçisini hizmet için belirtilen arabirime döndürür.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*guidService*<br/>
[içinde] Bir hizmet tanımlayıcısı (SID) için işaretçi.

*Riid*<br/>
[içinde] Arayanın erişilen arabirimin tanımlayıcısı.

*ppvObj*<br/>
[çıkış] İstenen arabirime dolaylı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Döndürülen HRESULT değeri aşağıdakilerden biridir:

|Döndürülen değer|Anlamı|
|------------------|-------------|
|S_OK|Hizmet başarıyla oluşturuldu veya alındı.|
|E_ınvalıdarg|Bağımsız değişkenlerden biri veya birkaçı geçersizdir.|
|E_outofmemory|Bellek hizmeti oluşturmak için yetersizdir.|
|E_unexpected|Bilinmeyen bir hata oluştu.|
|E_noınterface|İstenen arabirim bu hizmetin bir parçası değildir veya hizmet bilinmiyor.|

### <a name="remarks"></a>Açıklamalar

`QueryService`belirtilen hizmette istenen arabirime dolaylı bir işaretçi döndürür. Arayan, artık gerekli olmadığında bu işaretçiyi serbest bırakmakla yükümlüdür.

`QueryService`Aradığınızda, hem bir hizmet tanımlayıcısı *(guidService)* hem de bir arayüz tanımlayıcısını *(riid)* geçersiniz. *GuidService,* erişmek istediğiniz hizmeti belirtir ve *riid* hizmetin bir parçası olan bir arabirimi tanımlar. Karşılığında, arabirime dolaylı bir işaretçi alırsınız.

Arabirimi uygulayan nesne, diğer hizmetlerin parçası olan arabirimleri de uygulayabilir. Aşağıdaki topluluklara bir göz atın:

- Bu arabirimlerden bazıları isteğe bağlı olabilir. Hizmet açıklamasında tanımlanan tüm arabirimler, hizmetin her uygulamasında veya döndürülen her nesnede mutlaka bulunmaz.

- Farklı bir `QueryInterface`hizmet tanımlayıcısı geçen aramalar aksine mutlaka farklı bir Bileşen Nesne Modeli (COM) nesne döndürülür anlamına gelmez.

- Döndürülen nesne, hizmet tanımının bir parçası olmayan ek arabirimlere sahip olabilir.

arabirimin uygulanması iki hizmet arasında ortak bir şey olmayabilir olsa da, SID_SMyService ve SID_SYourService gibi iki farklı hizmet, her ikisi de aynı arabirimin kullanımını belirtebilir. (SID_SMyService, IID_IDispatch) `QueryService` için yapılan bir çağrı (SID_SYourService, `QueryService` IID_IDispatch) farklı bir nesne döndürebileceğinden, bu işe yarar. Farklı bir hizmet tanımlayıcısı belirttiğinizde nesne kimliği kabul edilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
