---
title: "cache_chunklist sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs: C++
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13d81e3eab6e93a138ac55ca53cbf8e61f195507
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cachechunklist-class"></a>cache_chunklist Sınıfı
Tanımlayan bir [ayırıcısı engelleme](../standard-library/allocators-header.md) ayırır ve bellek blokları tek bir boyutta kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <std::size_t Sz, std::size_t Nelts = 20>  
class cache_chunklist
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Sz`|Ayrılacak dizideki öğelerin sayısı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu şablon sınıfı kullanır `operator new` öbekleri ham bellek ayrılamadı suballocating engeller gerektiğinde bir bellek bloğu için ayrılacak; her öbek için ayrı bir ücretsiz listesinde deallocated bellek blokları depolar ve kullanır `operator delete` serbest bırakma için bir bellek blokları hiçbiri kullanımda olduğunda öbek.  
  
 Her bellek bloğu tutan `Sz` bayt kullanılabilir bellek ve ait öbek için bir işaretçi. Her bir öbeğin tutan `Nelts` bellek blokları, üç işaretçileri, int ve verileri, `operator new` ve `operator delete` gerektirir.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[cache_chunklist](#cache_chunklist)|Türünde bir nesne oluşturur `cache_chunklist`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[allocate](#allocate)|Bir bellek bloğu ayırır.|  
|[serbest bırakma](#deallocate)|Nesneleri belirtilen konumdaki depolama başından itibaren belirli sayıda boşaltır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a>cache_chunklist::allocate  
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
  
##  <a name="cache_chunklist"></a>cache_chunklist::cache_chunklist  
 Türünde bir nesne oluşturur `cache_chunklist`.  
  
```
cache_chunklist();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="deallocate"></a>cache_chunklist::deallocate  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



