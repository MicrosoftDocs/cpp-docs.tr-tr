---
title: "sync_shared sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
dev_langs: C++
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c84b340c82e735b3bcc62609ff1db10791f154e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="syncshared-class"></a>sync_shared Sınıfı
Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) tüm allocators tarafından paylaşılan bir önbellek nesnesi erişimi denetlemek için bir mutex kullanan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Cache>  
class sync_shared
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Cache`|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[ayırma](#allocate)|Bir bellek bloğu ayırır.|  
|[serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|  
|[eşittir](#equals)|Eşitlik için iki önbellekleri karşılaştırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>sync_shared::allocate  
 Bir bellek bloğu ayırır.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`count`|Ayrılacak dizideki öğelerin sayısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış nesnesine bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrıları mutex kilitler `cache.allocate(count)`mutex kilidini açar ve önceki çağrının sonucunu döndürür `cache.allocate(count)`. `cache`Geçerli önbellek nesnesini temsil eder.  
  
##  <a name="deallocate"></a>sync_shared::deallocate  
 Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ptr`|Depolama biriminden bırakılmasına ilk nesne için bir işaretçi.|  
|`count`|Depolama biriminden bırakılmasına nesnelerin sayısı.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi çağrıları mutex kilitler `cache.deallocate(ptr, count)`, burada `cache` mutex kilidini açar ve önbellek nesnesini temsil eder.  
  
##  <a name="equals"></a>sync_shared::Equals  
 Eşitlik için iki önbellekleri karşılaştırır.  
  
```
bool equals(const sync_shared<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Cache`|Eşitleme filtresiyle ilişkili önbellek türü.|  
|`Other`|Eşitlik için karşılaştırmak için önbellek.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa sonucu `cache.equals(Other.cache)`, burada `cache` önbellek nesnesini temsil eden, olan `true`; Aksi halde, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



