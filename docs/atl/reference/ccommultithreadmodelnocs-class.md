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
ms.openlocfilehash: 01c7f953b6b8916394ee4c2b5b27cf84af52b920
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497082"
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS sınıfı

`CComMultiThreadModelNoCS`kritik bölüm kilitleme veya kilit açma işlevleri olmadan, bir değişkenin değerini artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComMultiThreadModelNoCS
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS:: oto Kritiksection](#autocriticalsection)|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.|
|[CComMultiThreadModelNoCS:: Kritiksection](#criticalsection)|Başvuru sınıfı `CComFakeCriticalSection`.|
|[CComMultiThreadModelNoCS:: ThreadModelNoCS](#threadmodelnocs)|Başvuru sınıfı `CComMultiThreadModelNoCS`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModelNoCS::D ecrement](#decrement)|Se Belirtilen değişkenin değerini iş parçacığı açısından güvenli bir şekilde azaltır.|
|[CComMultiThreadModelNoCS:: Increment](#increment)|Se Belirtilen değişkenin değerini iş parçacığı açısından güvenli bir şekilde arttırır.|

## <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS`, bir değişkeni artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlayan, [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ile benzerdir. Ancak, bir kritik bölüm sınıfına aracılığıyla `CComMultiThreadModelNoCS`başvuru yaptığınızda `Lock` ve `Unlock` gibi yöntemler hiçbir şey yapmaz.

Genellikle, **typedef** adı `CComMultiThreadModelNoCS` `ThreadModelNoCS` aracılığıyla kullanırsınız. Bu **typedef** `CComMultiThreadModelNoCS` ,`CComMultiThreadModel`, ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)içinde tanımlanmıştır.

> [!NOTE]
>  [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ve [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) genel `CComMultiThreadModelNoCS` **typedef** adları başvuru değildir.

Ayrıca `ThreadModelNoCS`, `CComMultiThreadModelNoCS` ve tanımlar.`CriticalSection` `AutoCriticalSection` Bu ikinci iki **typedef** adı başvuru [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)ve kritik bir bölüm alma ve serbest bırakma ile ilişkili boş yöntemler sağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="autocriticalsection"></a>CComMultiThreadModelNoCS:: oto Kritiksection

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `AutoCriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection` Kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) Ayrıca için `AutoCriticalSection`tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu `AutoCriticalSection`kritik bölüm sınıfı arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComAutoCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Buna ek `AutoCriticalSection`olarak, **typedef** Name [CriticalHandle bölümünü](#criticalsection)de kullanabilirsiniz. CRT başlangıç kodunu ortadan `AutoCriticalSection` kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="criticalsection"></a>CComMultiThreadModelNoCS:: Kritiksection

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `CriticalSection` [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)sınıfına başvurur.

```
typedef CComFakeCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

`CComFakeCriticalSection` Kritik bir bölüm sağlamadığından, yöntemleri hiçbir şey yapmaz.

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) Ayrıca için `CriticalSection`tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu `CriticalSection`kritik bölüm sınıfı arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|

Buna ek `CriticalSection`olarak, **typedef** adını `AutoCriticalSection`da kullanabilirsiniz. CRT başlangıç kodunu ortadan `AutoCriticalSection` kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

##  <a name="decrement"></a>CComMultiThreadModelNoCS::D ecrement

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini azaltan, [Stalockedazaltma](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)Win32 işlevini çağırır.

```
static ULONG WINAPI Decrement(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Azaltılangirecek değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Azalış sonucu 0 `Decrement` ise 0 değerini döndürür. Azalış sonucu sıfır değilse, dönüş değeri de sıfır dışında olur, ancak azalış sonucunu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

**Interlockedazaltma** , bu değişkeni aynı anda birden fazla iş parçacığının kullanmasını engelliyor.

##  <a name="increment"></a>CComMultiThreadModelNoCS:: Increment

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini artıran bir Win32 Işlevi [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)çağırır.

```
static ULONG WINAPI Increment(LPLONG p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Artış sonucu 0 ise, **artış** 0 döndürür. Artışın sonucu sıfır değilse, dönüş değeri de sıfır dışında olur, ancak artış sonucunu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

**InterlockedIncrement** , bu değişkeni aynı anda birden fazla iş parçacığının kullanmasını engelliyor.

##  <a name="threadmodelnocs"></a>CComMultiThreadModelNoCS:: ThreadModelNoCS

Kullanırken `CComMultiThreadModelNoCS`, **typedef** adı `ThreadModelNoCS` yalnızca başvuru `CComMultiThreadModelNoCS`olur.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) Ayrıca için `ThreadModelNoCS`tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu `ThreadModelNoCS`sınıf arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|

`ThreadModelNoCS` İçindeki `CComMultiThreadModel` tanımının ve ile`CComSingleThreadModel`simetri sağladığını unutmayın. `CComMultiThreadModelNoCS` Örneğin, örnek kodun aşağıdaki `CComMultiThreadModel::AutoCriticalSection` **typedef**'i bildirdiğini varsayalım:

[!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]

İçin `ThreadModel` belirtilen sınıftan bağımsız olarak `CComMultiThreadModelNoCS`, (gibi), `_ThreadModel` buna göre çözümler.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
