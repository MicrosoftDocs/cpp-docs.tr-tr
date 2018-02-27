---
title: "sync_none sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb01cc0df6765b8aae994ba272dc12bcf25f9be9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="syncnone-class"></a>sync_none Sınıfı
Açıklayan bir [eşitleme filtresi](../standard-library/allocators-header.md) eşitleme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Cache>  
class sync_none
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Cache`|Eşitleme filtresiyle ilişkili önbellek türü. Bu, [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[allocate](#allocate)|Bir bellek bloğu ayırır.|  
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|  
|[equals](#equals)|Eşitlik için iki önbellekleri karşılaştırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>  sync_none::allocate  
 Bir bellek bloğu ayırır.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`count`|Ayrılacak dizideki öğelerin sayısı.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `cache.allocate(count)`, burada `cache` önbellek nesnesidir.  
  
##  <a name="deallocate"></a>  sync_none::deallocate  
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
 Üye işlev çağrılarını `cache.deallocate(ptr, count)`, burada `cache` önbellek nesnesini temsil eder.  
  
##  <a name="equals"></a>  sync_none::Equals  
 Eşitlik için iki önbellekleri karşılaştırır.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Cache`|Eşitleme filtresi önbellek nesnesi.|  
|`Other`|Eşitlik için karşılaştırmak için önbellek nesnesi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlev her zaman döndürür `true`.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



