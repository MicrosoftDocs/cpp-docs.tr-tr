---
title: CcomsingleThreadModel Sınıfı
ms.date: 2/29/2020
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
ms.openlocfilehash: 3d8169c999ba96049bc711033f7ba2ef53989663
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327327"
---
# <a name="ccomsinglethreadmodel-class"></a>CcomsingleThreadModel Sınıfı

Bu sınıf, bir değişkenin değerini artım ve alma yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComSingleThreadModel
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[KcomsingleThreadModel::Otokritikbölüm](#autocriticalsection)|Referanslar sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[KcomsingleThreadModel::kritik bölüm](#criticalsection)|Referanslar `CComFakeCriticalSection`sınıfı .|
|[CcomsingleThreadModel::ThreadModelnocs](#threadmodelnocs)|Referanslar `CComSingleThreadModel`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel::Decrement](#decrement)|Belirtilen değişkenin değerini eriter. Bu uygulama iş parçacığı güvenli değildir.|
|[CComSingleThreadModel::Artış](#increment)|Belirtilen değişkenin değerini artışlar. Bu uygulama iş parçacığı güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

`CComSingleThreadModel`bir değişkenin değerini artım ve düşürme yöntemleri sağlar. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)aksine, bu yöntemler iş parçacığı güvenli değildir.

Tipik olarak, `CComSingleThreadModel` [ccomobjectthreadmodel veya CComGlobalsThreadModel](atl-typedefs.md#ccomobjectthreadmodel) [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)olmak üzere iki **typedef** adlarından birini kullanırsınız. Her **typedef** tarafından başvurulan sınıf, aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı modeli|Daire iş parçacığı modeli|Ücretsiz iş parçacığı modeli|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`; M=`CComMultiThreadModel`

`CComSingleThreadModel`kendisi üç **typedef** adtanımlar. `ThreadModelNoCS`referanslar `CComSingleThreadModel`. `AutoCriticalSection`ve `CriticalSection` referans sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), kritik bir bölümün sahipliğini elde etmek ve serbest bırakmak ile ilgili boş yöntemler sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>KcomsingleThreadModel::Otokritikbölüm

Kullanırken `CComSingleThreadModel`, **typedef** adı `AutoCriticalSection` referanslar sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Kritik `CComFakeCriticalSection` bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) için `AutoCriticalSection`tanımlar içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan kritik `AutoCriticalSection`bölüm sınıfı arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek `AutoCriticalSection`olarak, **typedef** adı [CriticalSection](#criticalsection)kullanabilirsiniz. CRT başlangıç `AutoCriticalSection` kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerine belirtmemelisiniz.

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>KcomsingleThreadModel::kritik bölüm

Kullanırken `CComSingleThreadModel`, **typedef** adı `CriticalSection` referanslar sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Kritik `CComFakeCriticalSection` bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) için `CriticalSection`tanımlar içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan kritik `CriticalSection`bölüm sınıfı arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek `CriticalSection`olarak, **typedef** adı [AutoCriticalSection](#autocriticalsection)kullanabilirsiniz. CRT başlangıç `AutoCriticalSection` kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerine belirtmemelisiniz.

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::Decrement

Bu statik fonksiyon *p.* ile işaret edilen değişkenin değerini azalır.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Değişkenin verilecek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Kararnamenin sonucu.

## <a name="ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel::Artış

Bu statik fonksiyon *p*tarafından işaret edilen değişkenin değerini artmıştır.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Değişkenin artımlı olmasını işareteder.

### <a name="return-value"></a>Dönüş Değeri

Artış sonucu.

## <a name="ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CcomsingleThreadModel::ThreadModelnocs

Kullanırken `CComSingleThreadModel`, **typedef** `ThreadModelNoCS` adı `CComSingleThreadModel`sadece başvurur .

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) için `ThreadModelNoCS`tanımlar içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan `ThreadModelNoCS`sınıf arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
