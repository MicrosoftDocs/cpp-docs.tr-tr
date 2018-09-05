---
title: CComMultiThreadModel sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33eac78dc871dd2a9869452bc829150c3356fd0a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754949"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel sınıfı

`CComMultiThreadModel` iş parçacığı açısından güvenli yöntemleri artırma ve azaltma için bir değişkenin değerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComMultiThreadModel
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Sınıf başvuruları [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|
|[CComMultiThreadModel::CriticalSection](#criticalsection)|Sınıf başvuruları [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Sınıf başvuruları [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModel::Decrement](#decrement)|(Statik) Azaltır değişkenin değeri olarak belirtilen bir iş parçacığı açısından güvenli şekilde.|
|[CComMultiThreadModel::Increment](#increment)|(Statik) Belirtilen değişkenin değerini, iş parçacığı açısından güvenli bir şekilde artar.|

## <a name="remarks"></a>Açıklamalar

Genellikle, kullandığınız `CComMultiThreadModel` iki biri aracılığıyla **typedef** ad [CComObjectThreadModel] (atl-typedefs.md #ccomobjectthreadmodel veya [CComGlobalsThreadModel] (atl-typedefs.md #ccomglobalsthreadmodel. Her tarafından başvurulan sınıfın **typedef** iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:

|typedef|Çoklu iş parçacığı oluşturma|Grup iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; M = `CComMultiThreadModel`

`CComMultiThreadModel` kendisini tanımlayan üç **typedef** adları. `AutoCriticalSection` ve `CriticalSection` başvuru edinme ve kritik bölüm sahipliğini serbest yöntemleri sağlayan sınıflar. `ThreadModelNoCS` başvurular [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md). sınıfı

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="autocriticalsection"></a>  CComMultiThreadModel::AutoCriticalSection

Kullanırken `CComMultiThreadModel`, **typedef** adı `AutoCriticalSection` başvuran sınıfı [CComAutoCriticalSection](ccomautocriticalsection-class.md), alma ve kritik bölüm sahipliğini serbest için yöntemler sağlar nesne.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) ayrıca tanımlarını içeren `AutoCriticalSection`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan kritik bölüm sınıfı arasındaki ilişkiyi gösterir `AutoCriticalSection`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Ek olarak `AutoCriticalSection`, kullanabileceğiniz **typedef** adı [CriticalSection](#criticalsection). Değil belirtmelidir `AutoCriticalSection` genel nesnelerin veya statik sınıf üyeleri CRT başlatma kodunu ortadan kaldırmak istiyorsanız.

### <a name="example"></a>Örnek

Aşağıdaki kod modellenmiştir [CComObjectRootEx](ccomobjectrootex-class.md)ve `AutoCriticalSection` iş parçacığı bir ortamda kullanılan.

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

Aşağıdaki tablolarda sonuçlarını göster `InternalAddRef` ve `Lock` yöntemleri bağlı olarak, `ThreadModel` şablon parametresi ve uygulama tarafından kullanılan iş parçacığı modeli:

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel CComObjectThreadModel =

|Yöntem|Tek veya grup iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Artırma iş parçacığı açısından güvenli değildir.|Artış, iş parçacığı açısından güvenlidir.|
|`Lock`|Hiçbir şey yapmaz; kilitlemek için kritik bölümü yoktur.|Kritik bölümü kilitli.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel CComObjectThreadModel::ThreadModelNoCS =

|Yöntem|Tek veya grup iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Artırma iş parçacığı açısından güvenli değildir.|Artış, iş parçacığı açısından güvenlidir.|
|`Lock`|Hiçbir şey yapmaz; kilitlemek için kritik bölümü yoktur.|Hiçbir şey yapmaz; kilitlemek için kritik bölümü yoktur.|

##  <a name="criticalsection"></a>  CComMultiThreadModel::CriticalSection

Kullanırken `CComMultiThreadModel`, **typedef** adı `CriticalSection` başvuran sınıfı [CComCriticalSection](ccomcriticalsection-class.md), alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) ayrıca tanımlarını içeren `CriticalSection`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan kritik bölüm sınıfı arasındaki ilişkiyi gösterir `CriticalSection`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Ek olarak `CriticalSection`, kullanabileceğiniz **typedef** adı [AutoCriticalSection](#autocriticalsection). Değil belirtmelidir `AutoCriticalSection` genel nesnelerin veya statik sınıf üyeleri CRT başlatma kodunu ortadan kaldırmak istiyorsanız.

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).

##  <a name="decrement"></a>  CComMultiThreadModel::Decrement

Bu statik işlevi Win32 işlevini çağırır [InterlockedDecrement](/windows/desktop/api/winbase/nf-winbase-interlockeddecrement), değişkenin değeri tarafından işaret edilen hangi azaltır *p*.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Parametreler

*p*  
[in] Azaltılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Azaltma sonucu 0, ardından ise `Decrement` 0 döndürür. Azaltma sonucunu sıfır değilse, dönüş değeri de sıfır olmayan, ancak azaltma sonucunu eşit değildir.

### <a name="remarks"></a>Açıklamalar

`InterlockedDecrement` birden fazla iş parçacığı, bu değişken aynı anda kullanmasını önler.

##  <a name="increment"></a>  CComMultiThreadModel::Increment

Bu statik işlevi Win32 işlevini çağırır [InterlockedIncrement](/windows/desktop/api/winbase/nf-winbase-interlockedincrement), işaret ettiği değişken değerini artırır *p*.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Parametreler

*p*  
[in] Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Sonucu artışı 0, ardından olup olmadığını `Increment` 0 döndürür. Sonucu artışı sıfır değilse, dönüş değeri de sıfır olmayan ancak artırma sonucunu eşit değildir.

### <a name="remarks"></a>Açıklamalar

`InterlockedIncrement` birden fazla iş parçacığı, bu değişken aynı anda kullanmasını önler.

##  <a name="threadmodelnocs"></a>  CComMultiThreadModel::ThreadModelNoCS

Kullanırken `CComMultiThreadModel`, **typedef** adı `ThreadModelNoCS` başvuran sınıfı [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS` artırma ve azaltma bir değişken için iş parçacığı açısından güvenli yöntemleri sağlar. Ancak, kritik bölüm sağlamaz.

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve `CComMultiThreadModelNoCS` ayrıca tanımlarını içeren `ThreadModelNoCS`. Aşağıdaki tablo iş parçacığı model sınıfı tarafından başvurulan sınıfı arasındaki ilişkiyi gösterir `ThreadModelNoCS`:

|Tanımlanan sınıfı|Başvuru sınıfı|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

Bkz: [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).

## <a name="see-also"></a>Ayrıca Bkz.

[CComSingleThreadModel sınıfı](ccomsinglethreadmodel-class.md)   
[CComAutoCriticalSection sınıfı](ccomautocriticalsection-class.md)   
[CComCriticalSection sınıfı](ccomcriticalsection-class.md)   
[Sınıfına genel bakış](../atl-class-overview.md)
