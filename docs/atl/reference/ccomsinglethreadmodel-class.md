---
title: CComSingleThreadModel sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 0a29e7da1c4f1662d7342a507bed786fcbf82bc4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765066"
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel sınıfı

Bu sınıf bir değişkenin değerini artırma ve azaltma için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComSingleThreadModel
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Sınıf başvuruları [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Sınıf başvuruları `CComFakeCriticalSection`.|
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Başvuruları `CComSingleThreadModel`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComSingleThreadModel::Decrement](#decrement)|Azaltır belirtilen değişkeninin değeri. Bu uygulama, iş parçacığı açısından güvenli değildir.|
|[CComSingleThreadModel::Increment](#increment)|Belirtilen değişkenin değerini artırır. Bu uygulama, iş parçacığı açısından güvenli değildir.|

## <a name="remarks"></a>Açıklamalar

`CComSingleThreadModel` yöntemler, bir değişkenin değerini artırma ve azaltma için sağlar. Farklı [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), bu yöntemler, iş parçacığı açısından güvenli değildir.  

Genellikle, kullandığınız `CComSingleThreadModel` iki biri aracılığıyla **typedef** adları, ya da [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Her tarafından başvurulan sınıfın **typedef** iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:  

|typedef|Çoklu iş parçacığı modeli|Grup iş parçacığı modeli|Ücretsiz iş parçacığı modeli|
|-------------|----------------------------|-------------------------------|--------------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

`CComSingleThreadModel` kendisini tanımlayan üç **typedef** adları. `ThreadModelNoCS` başvuruları `CComSingleThreadModel`. `AutoCriticalSection` ve `CriticalSection` reference sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), alma ve kritik bölüm sahipliğini serbest ilişkili boş yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="autocriticalsection"></a>  CComSingleThreadModel::AutoCriticalSection

Kullanırken `CComSingleThreadModel`, **typedef** adı `AutoCriticalSection` başvuran sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Çünkü `CComFakeCriticalSection` kritik bir bölüm sağlamaz metotlarını hiçbir şey yapma.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) tanımlarını içeren `AutoCriticalSection`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan kritik bölüm sınıfı arasındaki ilişkiyi gösterir `AutoCriticalSection`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Ek olarak `AutoCriticalSection`, kullanabileceğiniz **typedef** adı [CriticalSection](#criticalsection). Değil belirtmelidir `AutoCriticalSection` genel nesnelerin veya statik sınıf üyeleri CRT başlatma kodunu ortadan kaldırmak istiyorsanız.

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>  CComSingleThreadModel::CriticalSection

Kullanırken `CComSingleThreadModel`, **typedef** adı `CriticalSection` başvuran sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Çünkü `CComFakeCriticalSection` kritik bir bölüm sağlamaz metotlarını hiçbir şey yapma.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) tanımlarını içeren `CriticalSection`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan kritik bölüm sınıfı arasındaki ilişkiyi gösterir `CriticalSection`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Ek olarak `CriticalSection`, kullanabileceğiniz **typedef** adı [AutoCriticalSection](#autocriticalsection). Değil belirtmelidir `AutoCriticalSection` genel nesnelerin veya statik sınıf üyeleri CRT başlatma kodunu ortadan kaldırmak istiyorsanız.

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>  CComSingleThreadModel::Decrement

Bu statik işlev azaltır değişkenin değeri olarak işaret ettiği *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
[in] Azaltılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Azaltma sonucu.

##  <a name="increment"></a>  CComSingleThreadModel::Increment

Bu statik işlev azaltır değişkenin değeri olarak işaret ettiği *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*p*  
[in] Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Artırma sonucu.

##  <a name="threadmodelnocs"></a>  CComSingleThreadModel::ThreadModelNoCS

Kullanırken `CComSingleThreadModel`, **typedef** adı `ThreadModelNoCS` yalnızca başvuran `CComSingleThreadModel`.

```
typedef CComSingleThreadModel ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) tanımlarını içeren `ThreadModelNoCS`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan sınıfı arasındaki ilişkiyi gösterir `ThreadModelNoCS`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
