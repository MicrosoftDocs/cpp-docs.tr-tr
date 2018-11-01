---
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
ms.openlocfilehash: 5bad9ead5cb25d8ca1078bbbb25a00af1ebfcaa3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550767"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS sınıfı

`CComMultiThreadModelNoCS` iş parçacığı açısından güvenli yöntemleri artırma ve azaltma için önemli bir bölümü kilitleme veya kilidini açma işlevselliği bir değişkenin değerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Sınıf başvuruları [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Sınıf başvuruları `CComFakeCriticalSection`.|
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Sınıf başvuruları `CComMultiThreadModelNoCS`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statik) Azaltır değişkenin değeri olarak belirtilen bir iş parçacığı açısından güvenli şekilde.|
|[CComMultiThreadModelNoCS::Increment](#increment)|(Statik) Belirtilen değişkenin değerini, iş parçacığı açısından güvenli bir şekilde artar.|

## <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS` benzer [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) içeren, iş parçacığı açısından güvenli yöntemleri artırma ve azaltma için bir değişken sağlar. Ancak, kritik bölüm sınıfı aracılığıyla başvurduğunuzda `CComMultiThreadModelNoCS`, gibi yöntemler `Lock` ve `Unlock` hiçbir şey yapmaz.

Genellikle, kullandığınız `CComMultiThreadModelNoCS` aracılığıyla `ThreadModelNoCS` **typedef** adı. Bu **typedef** tanımlanan `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).

> [!NOTE]
>  Genel **typedef** adları [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ve [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) başvurusu `CComMultiThreadModelNoCS`.

Ek olarak `ThreadModelNoCS`, `CComMultiThreadModelNoCS` tanımlar `AutoCriticalSection` ve `CriticalSection`. Bu ikinci iki **typedef** başvuru adları [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), alma ve kritik bölüm serbest ilişkili boş yöntemleri sağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `AutoCriticalSection` başvuran sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Çünkü `CComFakeCriticalSection` kritik bir bölüm sağlamaz metotlarını hiçbir şey yapma.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ayrıca tanımlarını içeren `AutoCriticalSection`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan kritik bölüm sınıfı arasındaki ilişkiyi gösterir `AutoCriticalSection`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Ek olarak `AutoCriticalSection`, kullanabileceğiniz **typedef** adı [CriticalSection](#criticalsection). Değil belirtmelidir `AutoCriticalSection` genel nesnelerin veya statik sınıf üyeleri CRT başlatma kodunu ortadan kaldırmak istiyorsanız.

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `CriticalSection` başvuran sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

Çünkü `CComFakeCriticalSection` kritik bir bölüm sağlamaz metotlarını hiçbir şey yapma.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ayrıca tanımlarını içeren `CriticalSection`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan kritik bölüm sınıfı arasındaki ilişkiyi gösterir `CriticalSection`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Ek olarak `CriticalSection`, kullanabileceğiniz **typedef** adı `AutoCriticalSection`. Değil belirtmelidir `AutoCriticalSection` genel nesnelerin veya statik sınıf üyeleri CRT başlatma kodunu ortadan kaldırmak istiyorsanız.

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement

Bu statik işlevi Win32 işlevini çağırır [InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement), değişkenin değeri tarafından işaret edilen hangi azaltır *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
[in] Azaltılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Azaltma sonucu 0, ardından ise `Decrement` 0 döndürür. Azaltma sonucunu sıfır değilse, dönüş değeri de sıfır olmayan, ancak azaltma sonucunu eşit değildir.

### <a name="remarks"></a>Açıklamalar

**InterlockedDecrement** birden fazla iş parçacığı aynı anda bu değişken kullanmasını önler.

##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment

Bu statik işlevi Win32 işlevini çağırır [InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement), işaret ettiği değişken değerini artırır *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
[in] Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sonucu artışı 0, ardından olup olmadığını **artışı** 0 döndürür. Sonucu artışı sıfır değilse, dönüş değeri de sıfır olmayan ancak artırma sonucunu eşit değildir.

### <a name="remarks"></a>Açıklamalar

**InterlockedIncrement** birden fazla iş parçacığı aynı anda bu değişken kullanmasını önler.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `ThreadModelNoCS` yalnızca başvuran `CComMultiThreadModelNoCS`.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ayrıca tanımlarını içeren `ThreadModelNoCS`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan sınıfı arasındaki ilişkiyi gösterir `ThreadModelNoCS`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

Unutmayın tanımını `ThreadModelNoCS` içinde `CComMultiThreadModelNoCS` Simetri ile sağlar `CComMultiThreadModel` ve `CComSingleThreadModel`. Örneğin, örnek kodda varsayalım `CComMultiThreadModel::AutoCriticalSection` aşağıdaki bildirilen **typedef**:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

İçin belirtilen sınıf bakılmaksızın `ThreadModel` (gibi `CComMultiThreadModelNoCS`), `_ThreadModel` uygun şekilde giderir.

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)