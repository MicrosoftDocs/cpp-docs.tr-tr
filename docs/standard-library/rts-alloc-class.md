---
title: "rts_alloc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5f20215050a5488402cc17c849e20fe2c51608c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="rtsalloc-class"></a>rts_alloc Sınıfı
Rts_alloc Şablon sınıfı açıklayan bir [filtre](../standard-library/allocators-header.md) tutan bir dizi önbelleği örnekleri ve ayırma ve ayırmayı kaldırma yerine çalışma zamanında derleme zamanında kullanmak için hangi örneğinin belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Cache>  
class rts_alloc
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Cache`|Önbelleği örnekleri dizisi içinde yer alan türü. Bu, [cache_chunklist sınıfı](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md), veya [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu şablon sınıfı ayırıcısı örnekleri birden çok blok tutar ve ayırma veya derleme zamanında ayırmayı kaldırma yerine çalışma zamanında kullanılacak hangi örneği belirler. Yeniden bağlamasını derlenemiyor derleyicileri ile kullanılır.  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[allocate](#allocate)|Bir bellek bloğu ayırır.|  
|[Serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|  
|[equals](#equals)|Eşitlik için iki önbellekleri karşılaştırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>  rts_alloc::allocate  
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
 Üye işlevi döndürür `caches[_IDX].allocate(count)`, burada dizini `_IDX` istenen blok boyutu tarafından belirlenir `count`, veya `count` döndürdüğü çok büyük olduğundan `operator new(count)`. `cache`, önbellek nesnesini temsil eder.  
  
##  <a name="deallocate"></a>  rts_alloc::deallocate  
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
 Üye işlev çağrılarını `caches[_IDX].deallocate(ptr, count)`, burada dizini `_IDX` istenen blok boyutu tarafından belirlenir `count`, veya `count` döndürdüğü çok büyük olduğundan `operator delete(ptr)`.  
  
##  <a name="equals"></a>  rts_alloc::Equals  
 Eşitlik için iki önbellekleri karşılaştırır.  
  
```
bool equals(const sync<_Cache>& _Other) const;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Cache`|Filtreyle ilişkili önbellek nesnesi.|  
|`_Other`|Eşitlik için karşılaştırmak için önbellek nesnesi.|  
  
### <a name="remarks"></a>Açıklamalar  
 `true` varsa sonucu `caches[0].equals(other.caches[0])`; Aksi halde, `false`. `caches` Önbellek nesnelerinin dizisini temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)   
 [\<allocators >](../standard-library/allocators-header.md)



