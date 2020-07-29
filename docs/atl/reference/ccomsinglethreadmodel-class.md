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
ms.openlocfilehash: 05ef787764045ec7e17f5cdfdb0d4611cb2ac900
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229980"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel sınıfı

Bu sınıf, bir değişkenin değerini artırma ve azaltma için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComSingleThreadModel
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel:: oto Kritiksection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.|
|[CComSingleThreadModel:: Kritiksection](#criticalsection)|Başvuru sınıfı `CComFakeCriticalSection` .|
|[CComSingleThreadModel:: ThreadModelNoCS](#threadmodelnocs)|Başvurular `CComSingleThreadModel` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel::D ecrement](#decrement)|Belirtilen değişkenin değerini azaltır. Bu uygulama, iş parçacığı açısından güvenli değildir.|
|[CComSingleThreadModel:: Increment](#increment)|Belirtilen değişkenin değerini artırır. Bu uygulama, iş parçacığı açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

`CComSingleThreadModel`bir değişkenin değerini artırma ve azaltma için yöntemler sağlar. [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)'den farklı olarak, bu yöntemler iş parçacığı açısından güvenli değildir.

Genellikle, `CComSingleThreadModel` **`typedef`** [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)olmak üzere iki adlardan birini kullanırsınız. Tarafından başvurulan sınıf, **`typedef`** Aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı modeli|Apartman iş parçacığı modeli|Ücretsiz iş parçacığı modeli|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel` ; D =`CComMultiThreadModel`

`CComSingleThreadModel`, üç **`typedef`** ad tanımlar. `ThreadModelNoCS`başvurular `CComSingleThreadModel` . `AutoCriticalSection`ve `CriticalSection` önemli bir bölümün sahipliğini alma ve serbest bırakma ile ilişkili boş Yöntemler sağlayan [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)başvuru sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomsinglethreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CComSingleThreadModel:: oto Kritiksection

Kullanırken `CComSingleThreadModel` **`typedef`** ad, `AutoCriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection`Kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) , için tanımlar içerir `AutoCriticalSection` . Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu kritik bölüm sınıfı arasındaki ilişki gösterilmektedir `AutoCriticalSection` :

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek olarak `AutoCriticalSection` , **`typedef`** adı [kritikbölüm](#criticalsection)' i kullanabilirsiniz. `AutoCriticalSection`CRT başlangıç kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccomsinglethreadmodelcriticalsection"></a><a name="criticalsection"></a>CComSingleThreadModel:: Kritiksection

Kullanırken `CComSingleThreadModel` **`typedef`** ad, `CriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection`Kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) , için tanımlar içerir `CriticalSection` . Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu kritik bölüm sınıfı arasındaki ilişki gösterilmektedir `CriticalSection` :

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek olarak `CriticalSection` , **`typedef`** ad [oto](#autocriticalsection)adı ' nı kullanabilirsiniz. `AutoCriticalSection`CRT başlangıç kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="ccomsinglethreadmodeldecrement"></a><a name="decrement"></a>CComSingleThreadModel::D ecrement

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini azaltır.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Azaltılangirecek değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Azalış sonucu.

## <a name="ccomsinglethreadmodelincrement"></a><a name="increment"></a>CComSingleThreadModel:: Increment

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini artırır.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Artışın sonucu.

## <a name="ccomsinglethreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CComSingleThreadModel:: ThreadModelNoCS

Kullanırken `CComSingleThreadModel` , **`typedef`** ad `ThreadModelNoCS` yalnızca başvuru olur `CComSingleThreadModel` .

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) , için tanımlar içerir `ThreadModelNoCS` . Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu sınıf arasındaki ilişki gösterilmektedir `ThreadModelNoCS` :

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
