---
title: "&lt;allocators&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs: C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: c6b19eb0c4f8d63ce288ce47a759e949714daf5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; işleçleri
|||  
|-|-|  
|[operator! =](#op_neq)|[operator ==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>operator! =  
 Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Eşitsizlik için sınanacak ayırıcısı nesnelerinden biri.|  
|`right`|Eşitsizlik için sınanacak ayırıcısı nesnelerinden biri.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** ayırıcı nesneleri eşit; değilse **false** ayırıcı nesneleri eşit olması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işleci döndürür `!(left == right)`.  
  
##  <a name="op_eq_eq"></a>operator ==  
 Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Bir ayırıcı nesnenin eşitlik için test edilmelidir.|  
|`right`|Bir ayırıcı nesnenin eşitlik için test edilmelidir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** ayırıcı nesneleri eşitse; **false** ayırıcı nesneleri eşit değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şablon işleci döndürür `left.equals(right)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



