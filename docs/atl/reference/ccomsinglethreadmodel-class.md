---
title: CComSingleThreadModel sınıfı
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
ms.openlocfilehash: 9b111e06ba475a5077ba36b2235e8bd530302189
ms.sourcegitcommit: ab8d7b47b63b62892a1256a09b1324a9a136eccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78215457"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel sınıfı

Bu sınıf, bir değişkenin değerini artırma ve azaltma için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComSingleThreadModel
```

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Ortak tür tanımları

|Adı|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel:: oto Kritiksection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.|
|[CComSingleThreadModel:: Kritiksection](#criticalsection)|`CComFakeCriticalSection`sınıfı başvuruyor.|
|[CComSingleThreadModel:: ThreadModelNoCS](#threadmodelnocs)|`CComSingleThreadModel`başvurular.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel::D ecrement](#decrement)|Belirtilen değişkenin değerini azaltır. Bu uygulama, iş parçacığı açısından güvenli değildir.|
|[CComSingleThreadModel:: Increment](#increment)|Belirtilen değişkenin değerini artırır. Bu uygulama, iş parçacığı açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

`CComSingleThreadModel` bir değişkenin değerini artırma ve azaltma için yöntemler sağlar. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)'den farklı olarak, bu yöntemler iş parçacığı açısından güvenli değildir.

Genellikle, `CComSingleThreadModel` [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)olmak üzere iki **typedef** adından birini kullanarak kullanırsınız. Her **typedef** tarafından başvurulan sınıf, aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

|typedef|Tek iş parçacığı modeli|Apartman iş parçacığı modeli|Ücretsiz iş parçacığı modeli|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; A = `CComMultiThreadModel`

`CComSingleThreadModel` kendisi üç **typedef** adını tanımlar. `CComSingleThreadModel`başvuruları `ThreadModelNoCS`. `AutoCriticalSection` ve `CriticalSection` başvuru sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), kritik bir bölümün sahipliğini alma ve serbest bırakma ile ilişkili boş yöntemler sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="autocriticalsection"></a>CComSingleThreadModel:: oto Kritiksection

`CComSingleThreadModel`kullanırken, **typedef** Name `AutoCriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection` kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) `AutoCriticalSection`için tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve `AutoCriticalSection`tarafından başvurulan kritik bölüm sınıfı arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

`AutoCriticalSection`buna ek olarak, **typedef** Name [CriticalHandle bölümünü](#criticalsection)de kullanabilirsiniz. CRT başlangıç kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde `AutoCriticalSection` belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>CComSingleThreadModel:: Kritiksection

`CComSingleThreadModel`kullanırken, **typedef** Name `CriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection` kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) `CriticalSection`için tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve `CriticalSection`tarafından başvurulan kritik bölüm sınıfı arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

`CriticalSection`ek olarak, **typedef** Name, [oto CriticalHandle bölümünü](#autocriticalsection)kullanabilirsiniz. CRT başlangıç kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde `AutoCriticalSection` belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>CComSingleThreadModel::D ecrement

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini azaltır.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Azaltılangirecek değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Azalış sonucu.

##  <a name="increment"></a>CComSingleThreadModel:: Increment

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini artırır.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Artışın sonucu.

##  <a name="threadmodelnocs"></a>CComSingleThreadModel:: ThreadModelNoCS

`CComSingleThreadModel`kullanırken, `ThreadModelNoCS` **typedef** adı yalnızca `CComSingleThreadModel`başvuruda bulunuyor.

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) `ThreadModelNoCS`için tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve `ThreadModelNoCS`tarafından başvurulan sınıf arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
