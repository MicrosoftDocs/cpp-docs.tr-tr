---
title: CComMultiThreadModel Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
ms.openlocfilehash: 7ef803439d2d683633e8f9c00810542dd787541e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327666"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel Sınıfı

`CComMultiThreadModel`bir değişkenin değerini artım ve düşürmek için iş parçacığı için güvenli yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComMultiThreadModel
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CcomMultiThreadmodel::Otokritikbölüm](#autocriticalsection)|Referanslar sınıf [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|
|[CcomMultiThreadModel::kritik bölüm](#criticalsection)|Referanslar sınıf [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|
|[CcomMultiThreadModel::ThreadModelnocs](#threadmodelnocs)|Referanslar sınıf [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComMultiThreadModel::Decrement](#decrement)|(Statik) Belirtilen değişkenin değerini iş parçacığı güvenli bir şekilde erteler.|
|[CComMultiThreadModel::Artış](#increment)|(Statik) Belirtilen değişkenin değerini iş parçacığı güvenli bir şekilde artışlar.|

## <a name="remarks"></a>Açıklamalar

Tipik olarak, `CComMultiThreadModel` iki **typedef** adlarından birini kullanırsınız, [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Her **typedef** tarafından başvurulan sınıf, aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

| typedef|Tek iş parçacığı|Daire diş ipliği|Serbest iş parçacığı|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S= `CComSingleThreadModel`; M=`CComMultiThreadModel`

`CComMultiThreadModel`kendisi üç **typedef** adtanımlar. `AutoCriticalSection`ve `CriticalSection` kritik bir bölümün sahipliğini elde etme ve serbest bırakma yöntemleri sağlayan başvuru sınıfları. `ThreadModelNoCS`referanslar sınıf [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccommultithreadmodelautocriticalsection"></a><a name="autocriticalsection"></a>CcomMultiThreadmodel::Otokritikbölüm

Kullanırken `CComMultiThreadModel`, **typedef** adı `AutoCriticalSection` kritik bir bölüm nesnesinin sahipliğini elde etmek ve serbest bırakmak için yöntemler sağlayan [cComAutoCriticalSection](ccomautocriticalsection-class.md)sınıfı başvurur.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) için `AutoCriticalSection`tanımlar da içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan kritik `AutoCriticalSection`bölüm sınıfı arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek `AutoCriticalSection`olarak, **typedef** adı [CriticalSection](#criticalsection)kullanabilirsiniz. CRT başlangıç `AutoCriticalSection` kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerine belirtmemelisiniz.

### <a name="example"></a>Örnek

Aşağıdaki kod [CComObjectRootEx](ccomobjectrootex-class.md)sonra modellenmiştir ve `AutoCriticalSection` bir iş parçacığı ortamında kullanıldığını gösterir.

```cpp
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```

Aşağıdaki tablolar, `InternalAddRef` `Lock` `ThreadModel` şablon parametreye ve uygulama tarafından kullanılan iş parçacığı modeline bağlı olarak, yöntem ve yöntemlerin sonuçlarını gösterir:

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel

|Yöntem|Tek veya Daire Diş İşliği|Ücretsiz İş Parçacığı|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Artış iş parçacığı güvenli değildir.|Artış iş parçacığı için güvenlidir.|
|`Lock`|Hiçbir şey yapmaz; kilitlemek için kritik bir bölüm yoktur.|Kritik bölüm kilitlendi.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel::ThreadModelNoCS

|Yöntem|Tek veya Daire Diş İşliği|Ücretsiz İş Parçacığı|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Artış iş parçacığı güvenli değildir.|Artış iş parçacığı için güvenlidir.|
|`Lock`|Hiçbir şey yapmaz; kilitlemek için kritik bir bölüm yoktur.|Hiçbir şey yapmaz; kilitlemek için kritik bir bölüm yoktur.|

## <a name="ccommultithreadmodelcriticalsection"></a><a name="criticalsection"></a>CcomMultiThreadModel::kritik bölüm

Kullanırken `CComMultiThreadModel`, **typedef** adı `CriticalSection` kritik bir bölüm nesnesinin sahipliğini elde etmek ve serbest bırakmak için yöntemler sağlayan [cComCriticalSection](ccomcriticalsection-class.md)sınıfı başvurur.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) için `CriticalSection`tanımlar da içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan kritik `CriticalSection`bölüm sınıfı arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek `CriticalSection`olarak, **typedef** adı [AutoCriticalSection](#autocriticalsection)kullanabilirsiniz. CRT başlangıç `AutoCriticalSection` kodunu ortadan kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerine belirtmemelisiniz.

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](#autocriticalsection).

## <a name="ccommultithreadmodeldecrement"></a><a name="decrement"></a>CComMultiThreadModel::Decrement

Bu statik fonksiyon Win32 fonksiyonu [InterlockedDecrement](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)çağırır , *hangi p*tarafından işaret değişkenin değerini decrements .

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Değişkenin verilecek işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Kararnamenin sonucu 0 ise, 0 `Decrement` döndürür. Decrement sonucu sıfırsız ise, iade değeri de sıfırsız, ancak decrement sonucu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

`InterlockedDecrement`birden fazla iş parçacığının aynı anda bu değişkeni kullanmasını engeller.

## <a name="ccommultithreadmodelincrement"></a><a name="increment"></a>CComMultiThreadModel::Artış

Bu statik fonksiyon Win32 fonksiyonu [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)çağırır , *hangi p*tarafından işaret değişkenin değerini artımlar .

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Değişkenin artımlı olmasını işareteder.

### <a name="return-value"></a>Dönüş Değeri

Artış sonucu 0 ise, 0 `Increment` döndürür. Artış sonucu sıfır değilse, iade değeri de sıfır sızdır, ancak artış sonucuna eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

`InterlockedIncrement`birden fazla iş parçacığının aynı anda bu değişkeni kullanmasını engeller.

## <a name="ccommultithreadmodelthreadmodelnocs"></a><a name="threadmodelnocs"></a>CcomMultiThreadModel::ThreadModelnocs

Kullanırken `CComMultiThreadModel`, **typedef** adı `ThreadModelNoCS` referanslar sınıf [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS`bir değişkeni artımve crecrementing için iş parçacığı güvenli yöntemler sağlar; ancak, kritik bir bölüm sağlamaz.

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) `CComMultiThreadModelNoCS` ve aynı zamanda `ThreadModelNoCS`tanımlar içerir. Aşağıdaki tablo, iş parçacığı modeli sınıfı ile başvurulan `ThreadModelNoCS`sınıf arasındaki ilişkiyi gösterir:

|Tanımlanan sınıf|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

[Bkz. ccommultithreadmodel::autocriticalsection](#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[CcomsingleThreadModel Sınıfı](ccomsinglethreadmodel-class.md)<br/>
[CComAutoCriticalSection Sınıfı](ccomautocriticalsection-class.md)<br/>
[CComCriticalSection Sınıfı](ccomcriticalsection-class.md)<br/>
[Sınıfa Genel Bakış](../atl-class-overview.md)
