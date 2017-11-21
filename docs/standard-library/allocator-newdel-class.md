---
title: "allocator_newdel sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
dev_langs: C++
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 76ecf50e5f8e120dd4139d47b28688a79cda3791
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="allocatornewdel-class"></a>allocator_newdel Sınıfı
Kullanan bir ayırıcı uygulayan `operator delete` bellek ayırması için blok ve `operator new` bir bellek bloğu ayrılamadı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Type>  
class allocator_newdel;
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Type`|Ayırıcı tarafından ayrılan öğelerin türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) makrosu geçirir bu sınıfı olarak `name` aşağıdaki ifadeyi parametresinde:`ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



