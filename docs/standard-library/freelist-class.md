---
title: "FreeList sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs: C++
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63490ba1be2459aa31f461193c0f754ba9ec1e12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="freelist-class"></a>freelist Sınıfı
Bellek blokları bir listesini yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <std::size_t Sz, class Max>  
class freelist
 : public Max
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Sz`|Ayrılacak dizideki öğelerin sayısı.|  
|`Max`|Boş listede depolanması öğelerinin üst limiti temsil eden max sınıfı. Max sınıf olabilir [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md), veya [max_variable_size](../standard-library/max-variable-size-class.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu şablon sınıfı bellek blok boyutu bir listesini yönetir `Sz` geçirilen max sınıfı tarafından belirlenen listesinin en büyük uzunluğa sahip `Max`.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[FreeList](#freelist)|Türünde bir nesne oluşturur `freelist`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[POP](#pop)|İlk bellek bloğu boş listeden kaldırır.|  
|[push](#push)|Bir bellek bloğu listesine ekler.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="freelist"></a>FreeList::FreeList  
 Türünde bir nesne oluşturur `freelist`.  
  
```
freelist();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="pop"></a>FreeList::POP  
 İlk bellek bloğu boş listeden kaldırır.  
  
```
void *pop();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listeden kaldırılan bellek bloğu için bir işaretçi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür `NULL` liste boşsa. Aksi durumda, ilk bellek bloğu listeden kaldırır.  
  
##  <a name="push"></a>FreeList::push  
 Bir bellek bloğu listesine ekler.  
  
```
bool push(void* ptr);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ptr`|Ücretsiz listeye eklenecek bellek bloğu için bir işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `full` max sınıfının işlevi döndürür `false`; Aksi halde, `push` işlev döndürür `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `full` max sınıfının işlevi döndürür `false`, bu üye fonksiyonu gösterdiği bellek bloğu ekler `ptr` listenin başındaki için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



