---
title: "allocator_suballoc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::allocators::allocator_suballoc
- allocators/stdext::allocator_suballoc
dev_langs: C++
helpviewer_keywords: allocator_suballoc class
ms.assetid: 50c6a5c0-d00d-4276-9285-d908fd4f6483
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 62f91cfbe39967dc5c95dba0f0e4c70a4bc96a14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="allocatorsuballoc-class"></a>allocator_suballoc Sınıfı
Depolama ayırma ve serbest bırakma türündeki nesneler için yöneten bir nesneyi tanımlayan `Type` bir önbellek türü kullanarak [cache_suballoc](../standard-library/cache-suballoc-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Type>  
class allocator_suballoc;
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Type`|Ayırıcı tarafından ayrılan öğelerin türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu geçirir bu sınıfı olarak `name` aşağıdaki ifadeyi parametresinde:`ALLOCATOR_DECL(CACHE_SUBALLOC, SYNC_DEFAULT, allocator_suballoc);`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



