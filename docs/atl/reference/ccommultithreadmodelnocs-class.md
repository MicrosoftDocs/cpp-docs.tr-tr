---
title: CComMultiThreadModelNoCS Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
ms.openlocfilehash: 4d41ffcfccbd7ef65ed86df79bffec1209a88cd3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327660"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS Sınıfı

`CComMultiThreadModelNoCS`kritik bölüm kilitleme veya işlevselliği kilidini açma olmadan bir değişkenin değerini artım ve atfetmek için iş parçacığı için güvenli yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CcomMultiThreadmodelnocs::Otokritikbölüm](#autocriticalsection)|Referanslar sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CcomMultiThreadModelnocs::kritik bölüm](#criticalsection)|Referanslar `CComFakeCriticalSection`sınıfı .|
|[CcomMultiThreadModelnocs::ThreadModelnocs](#threadmodelnocs)|Referanslar `CComMultiThreadModelNoCS`sınıfı .|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statik) Belirtilen değişkenin değerini iş parçacığı güvenli bir şekilde erteler.|
|[CComMultiThreadModelNoCS::Artış](#increment)|(Statik) Belirtilen değişkenin değerini iş parçacığı güvenli bir şekilde artışlar.|

## <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS`bir değişkeni artıştırma ve verme için iş parçacığı nauygun yöntemler sağlaması [CComMultiThreadModel'e](../../atl/reference/ccommultithreadmodel-class.md) benzer. Ancak, kritik bir bölüm sınıfına `CComMultiThreadModelNoCS`başvururken, gibi yöntemler `Lock` ve `Unlock` hiçbir şey yapmaz.

Genellikle, `CComMultiThreadModelNoCS` `ThreadModelNoCS` **typedef** adı ile kullanın. Bu **typedef** , `CComMultiThreadModelNoCS` `CComMultiThreadModel`ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)tanımlanır.

> [!NOTE]
> Küresel **typedef** isimleri [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ve [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) başvuru `CComMultiThreadModelNoCS`yok.

Buna ek `ThreadModelNoCS` `CComMultiThreadModelNoCS` olarak `AutoCriticalSection` , `CriticalSection`tanımlar ve . Bu son iki **typedef** isimleri referans [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), hangi alma ve kritik bir bölüm serbest ile ilişkili boş yöntemler sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a>CcomMultiThreadmodelnocs::Otokritikbölüm

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `AutoCriticalSection` referanslar sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Kritik `CComFakeCriticalSection` bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) için `AutoCriticalSection`tanımlar da içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan kritik `AutoCriticalSection`bölüm sınıfı arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Buna ek `AutoCriticalSection`olarak, **typedef** adı [CriticalSection](#criticalsection)kullanabilirsiniz. CRT başlangıç `AutoCriticalSection` kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerine belirtmemelisiniz.

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a>CcomMultiThreadModelnocs::kritik bölüm

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `CriticalSection` referanslar sınıf [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Kritik `CComFakeCriticalSection` bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) için `CriticalSection`tanımlar da içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan kritik `CriticalSection`bölüm sınıfı arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Buna ek `CriticalSection`olarak , **typedef** `AutoCriticalSection`adını kullanabilirsiniz. CRT başlangıç `AutoCriticalSection` kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerine belirtmemelisiniz.

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a>CComMultiThreadModelNoCS::Decrement

Bu statik fonksiyon Win32 fonksiyonu [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)çağırır , *hangi p*tarafından işaret değişkenin değerini decrements .

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Değişkenin verilecek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Kararnamenin sonucu 0 ise, 0 `Decrement` döndürür. Decrement sonucu sıfırsız ise, iade değeri de sıfırsız, ancak decrement sonucu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

**Birbirine kenetlenmiş Decrement,** birden fazla iş parçacığının aynı anda bu değişkeni kullanmasını önler.

## <a name="ccommultithreadmodelnocsincrement"></a><a name="increment"></a>CComMultiThreadModelNoCS::Artış

Bu statik fonksiyon Win32 fonksiyonu [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)çağırır , *hangi p*tarafından işaret değişkenin değerini artımlar .

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Değişkenin artımlı olmasını işareteder.

### <a name="return-value"></a>Dönüş Değeri

Artış sonucu 0 ise, **Artış** 0 döndürür. Artış sonucu sıfır değilse, iade değeri de sıfır sızdır, ancak artış sonucuna eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

**Birbirine kenetlenmiş Artış,** birden fazla iş parçacığının aynı anda bu değişkeni kullanmasını önler.

## <a name="ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a>CcomMultiThreadModelnocs::ThreadModelnocs

Kullanırken `CComMultiThreadModelNoCS`, **typedef** `ThreadModelNoCS` adı `CComMultiThreadModelNoCS`sadece başvurur .

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) için `ThreadModelNoCS`tanımlar da içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan `ThreadModelNoCS`sınıf arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Bu `ThreadModelNoCS` tanımı `CComMultiThreadModelNoCS` ile simetri sağlar `CComMultiThreadModel` ve `CComSingleThreadModel`unutmayın. Örneğin, aşağıdaki **typedef** `CComMultiThreadModel::AutoCriticalSection` bildirilen örnek kodu varsayalım:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

Ne olursa olsun sınıf `ThreadModel` için `CComMultiThreadModelNoCS`belirtilen `_ThreadModel` (gibi), buna göre çözer.

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
