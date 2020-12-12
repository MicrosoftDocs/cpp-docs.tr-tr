---
description: 'Daha fazla bilgi edinin: CComMultiThreadModelNoCS sınıfı'
title: CComMultiThreadModelNoCS sınıfı
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
ms.openlocfilehash: 8b26c59564f9a7869bb3429ee31284925815e6ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152015"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS sınıfı

`CComMultiThreadModelNoCS` kritik bölüm kilitleme veya kilit açma işlevleri olmadan, bir değişkenin değerini artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS:: oto Kritiksection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.|
|[CComMultiThreadModelNoCS:: Kritiksection](#criticalsection)|Başvuru sınıfı `CComFakeCriticalSection` .|
|[CComMultiThreadModelNoCS:: ThreadModelNoCS](#threadmodelnocs)|Başvuru sınıfı `CComMultiThreadModelNoCS` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS::D ecrement](#decrement)|Se Belirtilen değişkenin değerini iş parçacığı açısından güvenli bir şekilde azaltır.|
|[CComMultiThreadModelNoCS:: Increment](#increment)|Se Belirtilen değişkenin değerini iş parçacığı açısından güvenli bir şekilde arttırır.|

## <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS` , bir değişkeni artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlayan, [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ile benzerdir. Ancak, bir kritik bölüm sınıfına aracılığıyla başvuru yaptığınızda `CComMultiThreadModelNoCS` ve gibi yöntemler `Lock` `Unlock` hiçbir şey yapmaz.

Genellikle, `CComMultiThreadModelNoCS` ad aracılığıyla kullanırsınız `ThreadModelNoCS` **`typedef`** . Bu **`typedef`** `CComMultiThreadModelNoCS` ,, `CComMultiThreadModel` ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)içinde tanımlanmıştır.

> [!NOTE]
> **`typedef`** [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ve [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) genel adları başvuru değildir `CComMultiThreadModelNoCS` .

Ayrıca `ThreadModelNoCS` , `CComMultiThreadModelNoCS` `AutoCriticalSection` ve tanımlar `CriticalSection` . Bu son iki **`typedef`** ad, kritik bir bölüm alma ve serbest bırakma ile ilişkili boş Yöntemler sağlayan [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)Reference.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccommultithreadmodelnocsautocriticalsection"></a><a name="autocriticalsection"></a> CComMultiThreadModelNoCS:: oto Kritiksection

Kullanırken `CComMultiThreadModelNoCS` **`typedef`** ad, `AutoCriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection`Kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) Ayrıca için tanımlar içerir `AutoCriticalSection` . Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu kritik bölüm sınıfı arasındaki ilişki gösterilmektedir `AutoCriticalSection` :

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Buna ek olarak `AutoCriticalSection` , **`typedef`** adı [kritikbölüm](#criticalsection)' i kullanabilirsiniz. `AutoCriticalSection`CRT başlangıç kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccommultithreadmodelnocscriticalsection"></a><a name="criticalsection"></a> CComMultiThreadModelNoCS:: Kritiksection

Kullanırken `CComMultiThreadModelNoCS` **`typedef`** ad, `CriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection`Kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) Ayrıca için tanımlar içerir `CriticalSection` . Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu kritik bölüm sınıfı arasındaki ilişki gösterilmektedir `CriticalSection` :

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Buna ek olarak `CriticalSection` , adını da kullanabilirsiniz **`typedef`** `AutoCriticalSection` . `AutoCriticalSection`CRT başlangıç kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccommultithreadmodelnocsdecrement"></a><a name="decrement"></a> CComMultiThreadModelNoCS::D ecrement

Bu statik işlev, *p* tarafından işaret edilen değişkenin değerini azaltan, [Stalockedazaltma](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)Win32 işlevini çağırır.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Azaltılangirecek değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Azalış sonucu 0 ise `Decrement` 0 değerini döndürür. Azalış sonucu sıfır değilse, dönüş değeri de sıfır dışında olur, ancak azalış sonucunu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

**Interlockedazaltma** , bu değişkeni aynı anda birden fazla iş parçacığının kullanmasını engelliyor.

## <a name="ccommultithreadmodelnocsincrement"></a><a name="increment"></a> CComMultiThreadModelNoCS:: Increment

Bu statik işlev, *p* tarafından işaret edilen değişkenin değerini artıran bir Win32 Işlevi [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)çağırır.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Artış sonucu 0 ise, **artış** 0 döndürür. Artışın sonucu sıfır değilse, dönüş değeri de sıfır dışında olur, ancak artış sonucunu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

**InterlockedIncrement** , bu değişkeni aynı anda birden fazla iş parçacığının kullanmasını engelliyor.

## <a name="ccommultithreadmodelnocsthreadmodelnocs"></a><a name="threadmodelnocs"></a> CComMultiThreadModelNoCS:: ThreadModelNoCS

Kullanırken `CComMultiThreadModelNoCS` , **`typedef`** ad `ThreadModelNoCS` yalnızca başvuru olur `CComMultiThreadModelNoCS` .

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) Ayrıca için tanımlar içerir `ThreadModelNoCS` . Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu sınıf arasındaki ilişki gösterilmektedir `ThreadModelNoCS` :

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

`ThreadModelNoCS`İçindeki tanımının `CComMultiThreadModelNoCS` ve ile simetri sağladığını unutmayın `CComMultiThreadModel` `CComSingleThreadModel` . Örneğin, örnek kodun `CComMultiThreadModel::AutoCriticalSection` aşağıdakileri bildirdiğini varsayalım **`typedef`** :

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

İçin belirtilen sınıftan bağımsız `ThreadModel` olarak, (gibi `CComMultiThreadModelNoCS` ), `_ThreadModel` buna göre çözümler.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
