---
title: Hizmet Eşlemesi makrolar
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
ms.openlocfilehash: ab130b2401dc9885f82fd5668a2d722a96dd289b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78862521"
---
# <a name="service-map-macros"></a>Hizmet Eşlemesi makrolar

Bu makrolar hizmet haritaları ve girdilerini tanımlar.

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL hizmeti eşlemesinin başlangıcını işaretler.|
|[END_SERVICE_MAP](#end_service_map)|ATL hizmeti eşlemesinin sonunu işaretler.|
|[SERVICE_ENTRY](#service_entry)|Nesnenin belirli bir hizmet KIMLIĞINI desteklediğini gösterir.|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|[IServiceProviderImpl:: QueryService](#queryservice) ' i belirtilen nesneye zincirye yönlendirir.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP

Hizmet haritasının başlangıcını işaretler.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
'ndaki Hizmet eşlemesini içeren sınıfı belirtir.

### <a name="remarks"></a>Açıklamalar

COM nesneniz üzerinde hizmet sağlayıcısı işlevselliği uygulamak için hizmet haritasını kullanın. İlk olarak, sınıfınızı [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)konumundan türemelisiniz. İki tür giriş vardır:

- [SERVICE_ENTRY](#service_entry)   Belirtilen hizmet KIMLIĞI (SID) için desteği belirtir.

- [SERVICE_ENTRY_CHAIN](#service_entry_chain)   [IServiceProviderImpl:: QueryService](#queryservice) ' i başka, belirtilen bir nesneye zincirine yönlendirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

##  <a name="end_service_map"></a>END_SERVICE_MAP

Hizmet haritasının sonunu işaretler.

```
END_SERVICE_MAP()
```

### <a name="example"></a>Örnek

[BEGIN_SERVICE_MAP](#begin_service_map)için örneğe bakın.

##  <a name="service_entry"></a>SERVICE_ENTRY

Nesnenin *SID*tarafından belirtilen hizmet kimliğini desteklediğini belirtir.

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
Hizmet KIMLIĞI.

### <a name="example"></a>Örnek

[BEGIN_SERVICE_MAP](#begin_service_map)için örneğe bakın.

##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN

[Ivıceproviderımpl:: QueryService](#queryservice) , *punk*tarafından belirtilen nesneye zincirde yönlendirir.

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>Parametreler

*punk dili*<br/>
Zincirlenen **IUnknown** arabirimine yönelik bir işaretçi.

### <a name="example"></a>Örnek

[BEGIN_SERVICE_MAP](#begin_service_map)için örneğe bakın.

##  <a name="queryservice"></a>IServiceProviderImpl:: QueryService

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

|Dönüş değeri|Anlamı|
|------------------|-------------|
|S_OK|Hizmet başarıyla oluşturuldu veya alındı.|
|E_INVALIDARG|Bağımsız değişkenlerden biri veya birkaçı geçersiz.|
|E_OUTOFMEMORY|Bellek, hizmeti oluşturmak için yeterli değil.|
|E_UNEXPECTED|Bilinmeyen bir hata oluştu.|
|E_NOINTERFACE|İstenen arabirim bu hizmetin bir parçası değil veya hizmet bilinmiyor.|

### <a name="remarks"></a>Açıklamalar

`QueryService`, belirtilen hizmette istenen arabirime dolaylı bir işaretçi döndürür. Çağıran, Bu işaretçinin artık gerekli olmadığı durumlarda serbest bırakılmasından sorumludur.

`QueryService`çağırdığınızda, hem bir hizmet tanımlayıcısı (*guidService*) hem de arabirim tanımlayıcısı (*riıd*) iletirsiniz. *GuidService* , erişmek istediğiniz hizmeti belirtir ve *riıd* hizmetin bir parçası olan bir arabirimi tanımlar. Sonuç olarak, arabirime dolaylı bir işaretçi alırsınız.

Arabirimi uygulayan nesne, diğer hizmetlerin parçası olan arabirimleri de uygulayabilir. Aşağıdaki topluluklara bir göz atın:

- Bu arabirimlerin bazıları isteğe bağlı olabilir. Hizmet açıklamasında tanımlanmış arabirimlerin hepsi hizmetin her uygulamasında veya döndürülen tüm nesneler üzerinde bulunmalıdır.

- `QueryInterface`çağrılarından farklı olarak, farklı bir hizmet tanımlayıcısının geçirilmesi farklı bir bileşen nesne modeli (COM) nesnesinin döndürüldüğü anlamına gelmez.

- Döndürülen nesne, hizmet tanımının bir parçası olmayan ek arabirimlere sahip olabilir.

SID_SMyService ve SID_SYourService gibi iki farklı hizmet, her ikisi de aynı arabirimin kullanımını belirtebilir, ancak bu, arabirimin uygulanması iki hizmet arasında ortak hiçbir şey yapmayabilir. Bu, `QueryService` (SID_SMyService, IID_IDispatch) çağrısı `QueryService` (SID_SYourService, IID_IDispatch) farklı bir nesne döndürebildiğinden bu işe yarar. Farklı bir hizmet tanımlayıcısı belirttiğinizde nesne kimliği kabul edilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Larının](../../atl/reference/atl-macros.md)
