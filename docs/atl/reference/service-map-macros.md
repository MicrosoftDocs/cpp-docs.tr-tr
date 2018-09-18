---
title: Hizmet eşleme makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc7b0ca9388de82d49927a7fe76694212b94246b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053719"
---
# <a name="service-map-macros"></a>Hizmet eşleme makroları

Hizmet eşlemeleri ve girişleri bu makroları tanımlar.

|||
|-|-|
|[BEGIN_SERVICE_MAP](#begin_service_map)|Bir ATL hizmet eşlemesi başlangıcını işaretler.|
|[END_SERVICE_MAP](#end_service_map)|Bir ATL hizmet eşlemesi sonunu işaretler.|
|[SERVICE_ENTRY](#service_entry)|Nesne belirli bir hizmet kimliği desteklediğini belirtir|
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Bildirir [IServiceProviderImpl::QueryService](#queryservice) belirtilen nesneye zinciri için.|  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="begin_service_map"></a>  BEGIN_SERVICE_MAP

Hizmet eşlemesi başlangıcını işaretler.

```
BEGIN_SERVICE_MAP(theClass)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
[in] Hizmet eşlemesini içeren sınıfın belirtir.

### <a name="remarks"></a>Açıklamalar

Hizmet eşlemesi, COM nesnesi üzerinde hizmet sağlayıcısı işlevselliği uygulamak için kullanın. İlk olarak, sizin sınıfınızdan türetilmelidir [Iserviceproviderımpl](../../atl/reference/iserviceproviderimpl-class.md). İki tür giriş vardır:

- [SERVICE_ENTRY](#service_entry) belirtilen hizmet kimliği (SID) için destek gösterir.

- [SERVICE_ENTRY_CHAIN](#service_entry_chain) bildirir [IServiceProviderImpl::QueryService](#queryservice) zincirdeki başka bir, belirtilen bir nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]

##  <a name="end_service_map"></a>  END_SERVICE_MAP

Hizmet eşlemesi sonunu işaretler.

```
END_SERVICE_MAP()
```

### <a name="example"></a>Örnek

Örneğin bakın [BEGIN_SERVICE_MAP](#begin_service_map).

##  <a name="service_entry"></a>  SERVICE_ENTRY

Nesnesi tarafından belirtilen hizmet kimliği desteklediğini gösterir *SID*.

```
SERVICE_ENTRY( SID )
```

### <a name="parameters"></a>Parametreler

*SID*<br/>
Hizmet kimliği

### <a name="example"></a>Örnek

Örneğin bakın [BEGIN_SERVICE_MAP](#begin_service_map).

##  <a name="service_entry_chain"></a>  SERVICE_ENTRY_CHAIN

Bildirir [IServiceProviderImpl::QueryService](#queryservice) tarafından belirtilen nesnede zincirdeki *punk*.

```
SERVICE_ENTRY_CHAIN( punk )
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
Bir işaretçi **IUnknown** arabirimin zinciri için.

### <a name="example"></a>Örnek

Örneğin bakın [BEGIN_SERVICE_MAP](#begin_service_map).

##  <a name="queryservice"></a>  IServiceProviderImpl::QueryService

Oluşturur veya belirtilen hizmete erişen ve hizmet için belirtilen arabirim için bir arabirim işaretçisini döndürür.

```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametreler

*guidService*<br/>
[in] Hizmet tanımlayıcısı (SID) yönelik işaretçi.

*riid*<br/>
[in] Arayan erişim elde etmek için arabirim tanımlayıcısı.

*ppvObj*<br/>
[out] Dolaylı istenen arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Döndürülen HRESULT değerini aşağıdakilerden biridir:

|Dönüş değeri|Açıklama|
|------------------|-------------|
|S_OK|Hizmet başarıyla oluşturuldu veya alınır.|
|E_INVALIDARG|Bir veya daha fazla bağımsız değişken geçersiz.|
|E_OUTOFMEMORY|Bir hizmet oluşturmak bellek yetersiz.|
|E_UNEXPECTED|Bilinmeyen bir hata oluştu.|
|E_NOINTERFACE|İstenen arabirim bu hizmetin bir parçası değil veya bilinmeyen bir hizmettir.|

### <a name="remarks"></a>Açıklamalar

`QueryService` Belirtilen hizmet istenen arabiriminde dolaylı bir işaretçi döndürür. Artık gerekli olmadığında, bu işaretçi serbest bırakma için çağıran sorumludur.

Çağırdığınızda `QueryService`, geçirdiğiniz her iki hizmet tanımlayıcısı (*guidService*) ve bir arabirim tanımlayıcısı (*riid*). *GuidService* erişim, istediğiniz hizmet belirtir ve *riid* hizmetin bir parçası olan bir arabirim tanımlar. Buna karşılık, dolaylı bir arabirim işaretçisi alır.

Arabirimini uygulayan nesnenin ayrıca diğer hizmetleri arabirimleri uygulayabilir. Aşağıdakileri göz önünde bulundurun:

- Bu arabirimlerin bazıları, isteğe bağlı olabilir. Hizmet açıklamasında tanımlanan tüm arabirimleri mutlaka hizmetinin her bir uygulama ya da her döndürülen nesne yok.

- Çağrıları aksine `QueryInterface`, farklı hizmet tanımlayıcısı geçirme mutlaka gelmez farklı bir Bileşen Nesne Modeli (COM) nesne döndürülür.

- Döndürülen nesne hizmet tanımının bir parçası olmayan ek arabirimleri olabilir.

Hiçbir şey iki hizmet arasında ortak arabiriminin uygulamasını sahip olsanız bile SID_SMyService ve SID_SYourService, gibi iki farklı hizmet her ikisi de aynı arabirimi kullanımını belirtebilirsiniz. Bu, çalışır çünkü bir çağrı `QueryService` (SID_SMyService, IID_IDispatch) değerinden farklı bir nesne döndürebilir `QueryService` (SID_SYourService, IID_IDispatch). Farklı hizmet tanımlayıcısı belirttiğinizde nesne kimliğini kabul değil.

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
