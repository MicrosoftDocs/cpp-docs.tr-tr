---
title: CComMultiThreadModelNoCS sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::CriticalSection
- ATLBASE/ATL::CComMultiThreadModelNoCS::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModelNoCS::Decrement
- ATLBASE/ATL::CComMultiThreadModelNoCS::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModelNoCS class
- threading [ATL]
ms.assetid: 2b3f7a45-fd72-452c-aaf3-ccdaa621c821
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 758811b10757cd7903b4f1d6218a5f34f8a98462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccommultithreadmodelnocs-class"></a>CComMultiThreadModelNoCS sınıfı
`CComMultiThreadModelNoCS` iş parçacığı yöntemleri artırma ve azaltma için önemli bir bölümü kilitleme veya kilidini açma işlevselliği bir değişkenin değerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComMultiThreadModelNoCS
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::AutoCriticalSection](#autocriticalsection)|Başvuran sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComMultiThreadModelNoCS::CriticalSection](#criticalsection)|Başvuran sınıfı `CComFakeCriticalSection`.|  
|[CComMultiThreadModelNoCS::ThreadModelNoCS](#threadmodelnocs)|Başvuran sınıfı `CComMultiThreadModelNoCS`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComMultiThreadModelNoCS::Decrement](#decrement)|(Statik) Azaltır değişkenin değeri olarak belirtilen bir iş parçacığı açısından güvenli şekilde.|  
|[CComMultiThreadModelNoCS::Increment](#increment)|(Statik) Belirtilen değişkenin değeri olarak bir iş parçacığı açısından güvenli şekilde artırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComMultiThreadModelNoCS` benzer [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) içeren, iş parçacığı yöntemleri artırma ve azaltma için bir değişken sağlar. Ancak, başvuru yaptığınızda kritik bölüm sınıfı aracılığıyla `CComMultiThreadModelNoCS`, gibi yöntemler `Lock` ve `Unlock` hiçbir şey yapmaz.  
  
 Genellikle, kullandığınız `CComMultiThreadModelNoCS` aracılığıyla `ThreadModelNoCS` `typedef` adı. Bu `typedef` tanımlanan `CComMultiThreadModelNoCS`, `CComMultiThreadModel`, ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md).  
  
> [!NOTE]
>  Genel `typedef` adları [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ve [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel) başvuruda bulunmayın `CComMultiThreadModelNoCS`.  
  
 Ek olarak `ThreadModelNoCS`, `CComMultiThreadModelNoCS` tanımlar `AutoCriticalSection` ve `CriticalSection`. Bu ikinci iki `typedef` adları başvuru [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), önemli bir bölümü serbest bırakma ve alma ile ilişkili boş yöntemler sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="autocriticalsection"></a>  CComMultiThreadModelNoCS::AutoCriticalSection  
 Kullanırken `CComMultiThreadModelNoCS`, `typedef` adı `AutoCriticalSection` başvuruyor sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `CComFakeCriticalSection` önemli bir bölümü sağlamaz yöntemlerinden hiçbir şey yapma.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) de tanımlarını içeren `AutoCriticalSection`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu kritik bölüm sınıf arasındaki ilişkiyi gösterir `AutoCriticalSection`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 Ek olarak `AutoCriticalSection`, kullanabileceğiniz `typedef` adı [CriticalSection](#criticalsection). Değil belirtmelisiniz `AutoCriticalSection` genel nesneler veya CRT başlatma kodunu ortadan kaldırmak istiyorsanız, statik sınıf üyeleri.  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>  CComMultiThreadModelNoCS::CriticalSection  
 Kullanırken `CComMultiThreadModelNoCS`, `typedef` adı `CriticalSection` başvuruyor sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `CComFakeCriticalSection` önemli bir bölümü sağlamaz yöntemlerinden hiçbir şey yapma.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) de tanımlarını içeren `CriticalSection`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu kritik bölüm sınıf arasındaki ilişkiyi gösterir `CriticalSection`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
  
 Ek olarak `CriticalSection`, kullanabileceğiniz `typedef` adı `AutoCriticalSection`. Değil belirtmelisiniz `AutoCriticalSection` genel nesneler veya CRT başlatma kodunu ortadan kaldırmak istiyorsanız, statik sınıf üyeleri.  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>  CComMultiThreadModelNoCS::Decrement  
 Bu statik işlevi Win32 işlevini çağırır [InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580), tarafından değişkenin değerini işaret için hangi azaltır `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] İşaretçi değişken azaltılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Azaltma sonuç 0, ardından ise `Decrement` 0 döndürür. Azaltma sonuç sıfır değilse, dönüş değeri da sıfır olmayan ancak azaltma sonuç eşit değil.  
  
### <a name="remarks"></a>Açıklamalar  
 **InterlockedDecrement** bu değişkeni kullanarak aynı anda birden çok iş parçacığı engeller.  
  
##  <a name="increment"></a>  CComMultiThreadModelNoCS::Increment  
 Bu statik işlevi Win32 işlevini çağırır [InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614), gösterdiği değişkenin değerini artırır `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] İşaretçi artırılması değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Artırma sonucunu 0, ardından ise **artırma** 0 döndürür. Artırma sonucunu sıfır değilse, dönüş değeri da sıfır olmayan ancak artışı sonucunu eşit değil.  
  
### <a name="remarks"></a>Açıklamalar  
 **InterlockedIncrement** bu değişkeni kullanarak aynı anda birden çok iş parçacığı engeller.  
  
##  <a name="threadmodelnocs"></a>  CComMultiThreadModelNoCS::ThreadModelNoCS  
 Kullanırken `CComMultiThreadModelNoCS`, `typedef` adı `ThreadModelNoCS` yalnızca başvuran `CComMultiThreadModelNoCS`.  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) de tanımlarını içeren `ThreadModelNoCS`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu sınıf arasındaki ilişkiyi gösterir `ThreadModelNoCS`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
  
 Unutmayın tanımını `ThreadModelNoCS` içinde `CComMultiThreadModelNoCS` simetrisi ile sağlar `CComMultiThreadModel` ve `CComSingleThreadModel`. Örneğin, örnek kodda varsayalım `CComMultiThreadModel::AutoCriticalSection` aşağıdaki bildirilen `typedef`:  
  
 [!code-cpp[NVC_ATL_COM#37](../../atl/codesnippet/cpp/ccommultithreadmodelnocs-class_1.h)]  
  
 Belirtilen sınıf bağımsız olarak `ThreadModel` (gibi `CComMultiThreadModelNoCS`), `_ThreadModel` buna uygun olarak çözer.  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)