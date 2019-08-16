---
title: CComMultiThreadModel sınıfı
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
ms.openlocfilehash: 74fb68eead498685ef252968124368863e27be75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497096"
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel sınıfı

`CComMultiThreadModel`bir değişkenin değerini artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComMultiThreadModel
```

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModel:: oto Kritiksection](#autocriticalsection)|Sınıf [Ccomautocriticalhandle bölümüne](../../atl/reference/ccomautocriticalsection-class.md)başvurur.|
|[CComMultiThreadModel:: Kritiksection](#criticalsection)|Sınıf [Ccomcriticalhandle bölümüne](../../atl/reference/ccomcriticalsection-class.md)başvurur.|
|[CComMultiThreadModel:: ThreadModelNoCS](#threadmodelnocs)|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)sınıfına başvurur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComMultiThreadModel::D ecrement](#decrement)|Se Belirtilen değişkenin değerini iş parçacığı açısından güvenli bir şekilde azaltır.|
|[CComMultiThreadModel:: Increment](#increment)|Se Belirtilen değişkenin değerini iş parçacığı açısından güvenli bir şekilde arttırır.|

## <a name="remarks"></a>Açıklamalar

Genellikle, iki `CComMultiThreadModel` **typedef** adından birini kullanabilirsiniz ([CComObjectThreadModel] (ATL-Typedefs. MD # CComObjectThreadModel veya [CComGlobalsThreadModel] (ATL-Typedefs. MD # CComGlobalsThreadModel). Her **typedef** tarafından başvurulan sınıf, aşağıdaki tabloda gösterildiği gibi, kullanılan iş parçacığı modeline bağlıdır:

|typedef|Tek iş parçacığı|Apartman iş parçacığı|Serbest iş parçacığı|
|-------------|----------------------|-------------------------|--------------------|
|`CComObjectThreadModel`|S|S|M|
|`CComGlobalsThreadModel`|S|M|M|

S = `CComSingleThreadModel`; D =`CComMultiThreadModel`

`CComMultiThreadModel`, üç **typedef** adını tanımlar. `AutoCriticalSection`ve `CriticalSection` önemli bir bölümün sahipliğini almak ve serbest bırakmak için yöntemler sağlayan başvuru sınıfları. `ThreadModelNoCS`[CComMultiThreadModelNoCS (CComMultiThreadModelNoCS-class.md) sınıfına başvurur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="autocriticalsection"></a>CComMultiThreadModel:: oto Kritiksection

Kullanırken `CComMultiThreadModel`, **typedef** Name `AutoCriticalSection` sınıfı [ccomautocriticalhandle bölümüne](ccomautocriticalsection-class.md)başvurur, bu da kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

```
typedef CComAutoCriticalSection AutoCriticalSection;
```

### <a name="remarks"></a>Açıklamalar

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) Ayrıca için `AutoCriticalSection`tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu `AutoCriticalSection`kritik bölüm sınıfı arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek `AutoCriticalSection`olarak, **typedef** Name [CriticalHandle bölümünü](#criticalsection)de kullanabilirsiniz. CRT başlangıç kodunu ortadan `AutoCriticalSection` kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Aşağıdaki kod [CComObjectRootEx](ccomobjectrootex-class.md)öğesinden sonra modellenmiştir ve bir iş `AutoCriticalSection` parçacığı ortamında kullanıldığını gösterir.

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

Aşağıdaki tablolarda, uygulama tarafından kullanılan `InternalAddRef` `ThreadModel` Şablon parametresine ve `Lock` iş parçacığı modeline bağlı olarak ve yöntemlerinin sonuçları gösterilmektedir:

### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel = CComObjectThreadModel

|Yöntem|Tek veya apartman Iş parçacığı|Serbest Iş parçacığı|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Artış iş parçacığı açısından güvenli değildir.|Artış iş parçacığı güvenlidir.|
|`Lock`|Hiçbir şey yapmaz; kilitlenecek kritik bölüm yok.|Kritik bölüm kilitli.|

### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel = CComObjectThreadModel:: ThreadModelNoCS

|Yöntem|Tek veya apartman Iş parçacığı|Serbest Iş parçacığı|
|------------|-----------------------------------|--------------------|
|`InternalAddRef`|Artış iş parçacığı açısından güvenli değildir.|Artış iş parçacığı güvenlidir.|
|`Lock`|Hiçbir şey yapmaz; kilitlenecek kritik bölüm yok.|Hiçbir şey yapmaz; kilitlenecek kritik bölüm yok.|

##  <a name="criticalsection"></a>CComMultiThreadModel:: Kritiksection

Kullanırken `CComMultiThreadModel`, **typedef** adı `CriticalSection` sınıf [ccomcriticalhandle bölümüne](ccomcriticalsection-class.md)başvurur. Bu, kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

```
typedef CComCriticalSection CriticalSection;
```

### <a name="remarks"></a>Açıklamalar

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) Ayrıca için `CriticalSection`tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu `CriticalSection`kritik bölüm sınıfı arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComCriticalSection`|
|`CComSingleThreadModel`|`CComFakeCriticalSection`|
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|

Buna ek `CriticalSection`olarak, **typedef** Name, [oto CriticalHandle bölümünü](#autocriticalsection)de kullanabilirsiniz. CRT başlangıç kodunu ortadan `AutoCriticalSection` kaldırmak istiyorsanız, genel nesnelerde veya statik sınıf üyelerinde belirtmemelisiniz.

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](#autocriticalsection).

##  <a name="decrement"></a>CComMultiThreadModel::D ecrement

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini azaltan, [Stalockedazaltma](/windows/win32/api/winnt/nf-winnt-interlockeddecrement)Win32 işlevini çağırır.

```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Azaltılangirecek değişkene yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Azalış sonucu 0 `Decrement` ise 0 değerini döndürür. Azalış sonucu sıfır değilse, dönüş değeri de sıfır dışında olur, ancak azalış sonucunu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

`InterlockedDecrement`aynı anda birden fazla iş parçacığının bu değişkeni kullanmasını önler.

##  <a name="increment"></a>CComMultiThreadModel:: Increment

Bu statik işlev, *p*tarafından işaret edilen değişkenin değerini artıran bir Win32 Işlevi [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement)çağırır.

```
static ULONG WINAPI Increment(LPLONG p) throw ();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Arttırılacak değişken işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Artış sonucu 0 `Increment` ise 0 değerini döndürür. Artışın sonucu sıfır değilse, dönüş değeri de sıfır dışında olur, ancak artış sonucunu eşit olmayabilir.

### <a name="remarks"></a>Açıklamalar

`InterlockedIncrement`aynı anda birden fazla iş parçacığının bu değişkeni kullanmasını önler.

##  <a name="threadmodelnocs"></a>CComMultiThreadModel:: ThreadModelNoCS

Kullanırken `CComMultiThreadModel`, **typedef** adı `ThreadModelNoCS` [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)sınıfına başvurur.

```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```

### <a name="remarks"></a>Açıklamalar

`CComMultiThreadModelNoCS`bir değişkeni artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlar; Ancak, kritik bir bölüm sağlamaz.

[CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve `CComMultiThreadModelNoCS` Ayrıca için `ThreadModelNoCS`tanımlar içerir. Aşağıdaki tabloda, iş parçacığı modeli sınıfı ve başvurduğu `ThreadModelNoCS`sınıf arasındaki ilişki gösterilmektedir:

|Sınıf tanımlı|Başvurulan sınıf|
|----------------------|----------------------|
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|
|`CComSingleThreadModel`|`CComSingleThreadModel`|
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|

### <a name="example"></a>Örnek

Bkz. [CComMultiThreadModel:: oto Kritiksection](#autocriticalsection).

## <a name="see-also"></a>Ayrıca bkz.

[CComSingleThreadModel Sınıfı](ccomsinglethreadmodel-class.md)<br/>
[CComAutoCriticalSection Sınıfı](ccomautocriticalsection-class.md)<br/>
[CComCriticalSection Sınıfı](ccomcriticalsection-class.md)<br/>
[Sınıfa genel bakış](../atl-class-overview.md)
