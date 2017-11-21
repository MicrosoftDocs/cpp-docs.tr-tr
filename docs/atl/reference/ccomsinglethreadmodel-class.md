---
title: "CComSingleThreadModel sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel
- ATLBASE/ATL::CComSingleThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComSingleThreadModel::CriticalSection
- ATLBASE/ATL::CComSingleThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComSingleThreadModel::Decrement
- ATLBASE/ATL::CComSingleThreadModel::Increment
dev_langs: C++
helpviewer_keywords:
- single-threaded applications
- CComSingleThreadModel class
- single-threaded applications, ATL
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65af9492f3721fd642def72a3049552cdff75ce6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomsinglethreadmodel-class"></a>CComSingleThreadModel sınıfı
Bu sınıf bir değişkenin değerini artırma ve azaltma için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComSingleThreadModel
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSingleThreadModel::AutoCriticalSection](#autocriticalsection)|Başvuran sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).|  
|[CComSingleThreadModel::CriticalSection](#criticalsection)|Başvuran sınıfı `CComFakeCriticalSection`.|  
|[CComSingleThreadModel::ThreadModelNoCS](#threadmodelnocs)|Başvurular `CComSingleThreadModel`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComSingleThreadModel::Decrement](#decrement)|Azaltır belirtilen değişkeninin değeri. Bu uygulama iş parçacığı açısından güvenli değil.|  
|[CComSingleThreadModel::Increment](#increment)|Belirtilen değişken değerini artırır. Bu uygulama iş parçacığı açısından güvenli değil.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComSingleThreadModel`yöntemleri artırma ve azaltma için bir değişkenin değerini sağlar. Farklı [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), bu yöntemleri iş parçacığı açısından güvenli değildir.  

 Genellikle, kullandığınız `CComSingleThreadModel` iki biri aracılığıyla `typedef` adları, ya da [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) veya [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel). Her tarafından başvurulan sınıfı `typedef` iş parçacığı modeline kullanıldığında, aşağıdaki tabloda gösterildiği gibi bağlıdır:  

  
|typedef|Çoklu iş parçacığı modeli|Grup iş parçacığı modeli|Ücretsiz iş parçacığı modeli|  
|-------------|----------------------------|-------------------------------|--------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S = `CComSingleThreadModel`; M =`CComMultiThreadModel`  
  
 `CComSingleThreadModel`kendisini tanımlayan üç `typedef` adları. `ThreadModelNoCS`Başvurular `CComSingleThreadModel`. `AutoCriticalSection`ve `CriticalSection` başvuru sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), önemli bir bölümü sahipliğini serbest bırakma ve alma ile ilişkili boş yöntemler sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComSingleThreadModel::AutoCriticalSection  
 Kullanırken `CComSingleThreadModel`, `typedef` adı `AutoCriticalSection` başvuruyor sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `CComFakeCriticalSection` önemli bir bölümü sağlamaz yöntemlerinden hiçbir şey yapma.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) tanımlarını içeren `AutoCriticalSection`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu kritik bölüm sınıf arasındaki ilişkiyi gösterir `AutoCriticalSection`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComAutoCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Ek olarak `AutoCriticalSection`, kullanabileceğiniz `typedef` adı [CriticalSection](#criticalsection). Değil belirtmelisiniz `AutoCriticalSection` genel nesneler veya CRT başlatma kodunu ortadan kaldırmak istiyorsanız, statik sınıf üyeleri.  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="criticalsection"></a>CComSingleThreadModel::CriticalSection  
 Kullanırken `CComSingleThreadModel`, `typedef` adı `CriticalSection` başvuruyor sınıfı [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md).  
  
```
typedef CComFakeCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü `CComFakeCriticalSection` önemli bir bölümü sağlamaz yöntemlerinden hiçbir şey yapma.  
  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) tanımlarını içeren `CriticalSection`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu kritik bölüm sınıf arasındaki ilişkiyi gösterir `CriticalSection`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 Ek olarak `CriticalSection`, kullanabileceğiniz `typedef` adı [AutoCriticalSection](#autocriticalsection). Değil belirtmelisiniz `AutoCriticalSection` genel nesneler veya CRT başlatma kodunu ortadan kaldırmak istiyorsanız, statik sınıf üyeleri.  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
##  <a name="decrement"></a>CComSingleThreadModel::Decrement  
 Bu statik işlev azaltır değişkenin değeri olarak gösterdiği `p`.  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] İşaretçi değişken azaltılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Azaltma sonuç.  
  
##  <a name="increment"></a>CComSingleThreadModel::Increment  
 Bu statik işlev azaltır değişkenin değeri olarak gösterdiği `p`.  
  
```
static ULONG WINAPI Increment(LPLONG p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 [in] İşaretçi artırılması değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Artırma sonucu.  
  
##  <a name="threadmodelnocs"></a>CComSingleThreadModel::ThreadModelNoCS  
 Kullanırken `CComSingleThreadModel`, `typedef` adı `ThreadModelNoCS` yalnızca başvuran `CComSingleThreadModel`.  
  
```
typedef CComSingleThreadModel ThreadModelNoCS;
```  
  
### <a name="remarks"></a>Açıklamalar  
 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) ve [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md) tanımlarını içeren `ThreadModelNoCS`. Aşağıdaki tabloda iş parçacığı modeli ve başvurduğu sınıf arasındaki ilişkiyi gösterir `ThreadModelNoCS`:  
  
|Tanımlanan sınıfı|Başvurulan sınıfı|  
|----------------------|----------------------|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>Örnek  
 Bkz: [CComMultiThreadModel::AutoCriticalSection](../../atl/reference/ccommultithreadmodel-class.md#autocriticalsection).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
