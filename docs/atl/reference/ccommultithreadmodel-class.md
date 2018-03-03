---
title: "CComMultiThreadModel sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96f8c24736309ef1030664ee0fd466537d739496
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel sınıfı
`CComMultiThreadModel`iş parçacığı yöntemleri artırma ve azaltma için bir değişkenin değerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComMultiThreadModel
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|Başvuran sınıfı [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).|  
|[CComMultiThreadModel::CriticalSection](#criticalsection)|Başvuran sınıfı [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md).|  
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|Başvuran sınıfı [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](#decrement)|(Statik) Azaltır değişkenin değeri olarak belirtilen bir iş parçacığı açısından güvenli şekilde.|  
|[CComMultiThreadModel::Increment](#increment)|(Statik) Belirtilen değişkenin değeri olarak bir iş parçacığı açısından güvenli şekilde artırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Genellikle, kullandığınız `CComMultiThreadModel` iki biri aracılığıyla `typedef` adları, her iki [CComObjectThreadModel] (atl typedefs.md #ccomobjectthreadmodel veya [CComGlobalsThreadModel] (atl typedefs.md #ccomglobalsthreadmodel. Her tarafından başvurulan sınıfı `typedef` iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:  
  
|typedef|Çoklu iş parçacığı oluşturma|Apartman iş parçacığı oluşturma|Ücretsiz iş parçacığı oluşturma|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComMultiThreadModel`kendisini tanımlayan üç `typedef` adları. `AutoCriticalSection`ve `CriticalSection` başvuru alma ve önemli bir bölümü sahipliğini serbest bırakma için yöntemleri sağlayan sınıflar. `ThreadModelNoCS`başvurular [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md). sınıfı  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComMultiThreadModel::AutoCriticalSection  
 Kullanırken `CComMultiThreadModel`, `typedef` adı `AutoCriticalSection` başvuruyor sınıfı [CComAutoCriticalSection](ccomautocriticalsection-class.md), alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemler sağlar.  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) de tanımlarını içeren `AutoCriticalSection`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu kritik bölüm sınıf arasındaki ilişkiyi gösterir `AutoCriticalSection`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Ek olarak `AutoCriticalSection`, kullanabileceğiniz `typedef` adı [CriticalSection](#criticalsection). Değil belirtmelisiniz `AutoCriticalSection` genel nesneler veya CRT başlatma kodunu ortadan kaldırmak istiyorsanız, statik sınıf üyeleri.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod sonra modellenir [in uygulamasına](ccomobjectrootex-class.md), gösterir `AutoCriticalSection` bir iş parçacığı ortamında kullanılmakta.  
  

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
  
 Aşağıdaki tablolarda sonuçlarını göster `InternalAddRef` ve `Lock` yöntemleri bağlı olarak, **ThreadModel** şablon parametresi ve uygulama tarafından kullanılan iş parçacığı modeli:  
  
### <a name="threadmodel--ccomobjectthreadmodel"></a>ThreadModel CComObjectThreadModel =  
  
|Yöntem|Tek veya grup iş parçacığı oluşturma|Boş iş parçacığı oluşturma|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|Artırma iş parçacığı açısından güvenli değil.|İş parçacığı açısından güvenli değerdir.|  
|`Lock`|Hiçbir şey yapmaz; kilitlemek için kritik bölümü yoktur.|Kritik Bölümü kilitlendi.|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>ThreadModel CComObjectThreadModel::ThreadModelNoCS =  
  
|Yöntem|Tek veya grup iş parçacığı oluşturma|Boş iş parçacığı oluşturma|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|Artırma iş parçacığı açısından güvenli değil.|İş parçacığı açısından güvenli değerdir.|  
|`Lock`|Hiçbir şey yapmaz; kilitlemek için kritik bölümü yoktur.|Hiçbir şey yapmaz; kilitlemek için kritik bölümü yoktur.|  
  
##  <a name="criticalsection"></a>CComMultiThreadModel::CriticalSection  
 Kullanırken `CComMultiThreadModel`, `typedef` adı `CriticalSection` başvuruyor sınıfı [CComCriticalSection](ccomcriticalsection-class.md), alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemler sağlar.  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md) de tanımlarını içeren `CriticalSection`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu kritik bölüm sınıf arasındaki ilişkiyi gösterir `CriticalSection`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Ek olarak `CriticalSection`, kullanabileceğiniz `typedef` adı [AutoCriticalSection](#autocriticalsection). Değil belirtmelisiniz `AutoCriticalSection` genel nesneler veya CRT başlatma kodunu ortadan kaldırmak istiyorsanız, statik sınıf üyeleri.  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](#autocriticalsection).  
  
##  <a name="decrement"></a>CComMultiThreadModel::Decrement  
 Bu statik işlevi Win32 işlevini çağırır [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), tarafından değişkenin değerini işaret için hangi azaltır `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] İşaretçi değişken azaltılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Azaltma sonuç 0, ardından ise `Decrement` 0 döndürür. Azaltma sonuç sıfır değilse, dönüş değeri da sıfır olmayan ancak azaltma sonuç eşit değil.  
  
### <a name="remarks"></a>Açıklamalar  
 **InterlockedDecrement** bu değişkeni kullanarak aynı anda birden çok iş parçacığı engeller.  
  
##  <a name="increment"></a>CComMultiThreadModel::Increment  
 Bu statik işlevi Win32 işlevini çağırır [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), gösterdiği değişkenin değerini artırır `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] İşaretçi artırılması değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Artırma sonucunu 0, ardından ise **artırma** 0 döndürür. Artırma sonucunu sıfır değilse, dönüş değeri da sıfır olmayan ancak artışı sonucunu eşit değil.  
  
### <a name="remarks"></a>Açıklamalar  
 **InterlockedIncrement** bu değişkeni kullanarak aynı anda birden çok iş parçacığı engeller.  
  
##  <a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS  
 Kullanırken `CComMultiThreadModel`, `typedef` adı `ThreadModelNoCS` başvuruyor sınıfı [CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md).  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CComMultiThreadModelNoCS`iş parçacığı yöntemleri artırma ve azaltma bir değişken için sağlar; Ancak, önemli bir bölümü sağlamaz.  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md) ve `CComMultiThreadModelNoCS` de tanımlarını içeren `ThreadModelNoCS`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu sınıf arasındaki ilişkiyi gösterir `ThreadModelNoCS`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
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
 [Sınıfa genel bakış](../atl-class-overview.md)
