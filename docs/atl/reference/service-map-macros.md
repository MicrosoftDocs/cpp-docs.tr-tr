---
title: Hizmet Eşleme Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: eb2fe41c79135a7ac2ced9bc3242b070170716b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325937"
---
# <a name="service-map-macros"></a>Hizmet Eşleme Makroları

Bu makrolar hizmet eşlemlerini ve girişleri tanımlar.

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|Bir ATL hizmet haritasının başlangıcını işaretler.|
|[END_SERVICE_MAP](#end_service_map)|ATL hizmet haritasının sonunu işaretler.|
|[SERVICE_ENTRY](#service_entry)|Nesnenin belirli bir hizmet kimliğini desteklediğini gösterir.|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|[IServiceProviderImpl::QueryService'i](#queryservice) belirtilen nesneye zincirleme olarak bildirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="begin_service_map"></a><a name="begin_service_map"></a>BEGIN_SERVICE_MAP

Hizmet haritasının başlangıcını işaretler.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*theClass*<br/>
[içinde] Hizmet eşlemi içeren sınıfı belirtir.

### <a name="remarks"></a>Açıklamalar

COM nesnenizde servis sağlayıcı işlevini uygulamak için hizmet eşlemi'ni kullanın. İlk olarak, [iServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)sınıf türetmek gerekir. İki tür giriş vardır:

- [SERVICE_ENTRY](#service_entry)   Belirtilen hizmet kimliği (SID) desteğini gösterir.

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)   [IServiceProviderImpl'e bildirir::QueryService'i](#queryservice) başka bir nesneye zincirlemek için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

## <a name="end_service_map"></a><a name="end_service_map"></a>END_SERVICE_MAP

Hizmet haritasının sonunu işaretler.

```
END_SERVICE_MAP()
```

### <a name="example"></a>Örnek

[BEGIN_SERVICE_MAP](#begin_service_map)için örneğe bakın.

## <a name="service_entry"></a><a name="service_entry"></a>SERVICE_ENTRY

Nesnenin *SID*tarafından belirtilen hizmet id'ini desteklediğini gösterir.

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
Servis kimliği.

### <a name="example"></a>Örnek

[BEGIN_SERVICE_MAP](#begin_service_map)için örneğe bakın.

## <a name="service_entry_chain"></a><a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN

[IServiceProviderImpl talimatlar::QueryService](#queryservice) *punk*tarafından belirtilen nesneye zincir .

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
Zincirleme için **IUnknown** arabirimi için bir işaretçi.

### <a name="example"></a>Örnek

[BEGIN_SERVICE_MAP](#begin_service_map)için örneğe bakın.

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

[Makrolar](../../atl/reference/atl-macros.md)
