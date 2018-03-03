---
title: _com_ptr_t::detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c04007df7d40e12f3f416b2f2cd437bdaf1314f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft özel**  
  
 Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Ayıklar ve kapsüllenmiş arabirim işaretçisi döndürür ve kapsüllenmiş işaretçi depolama birimine temizler **NULL**. Bu, arabirim işaretçisini kapsüllemeden kaldırır. Çağrı size olan **sürüm** döndürüldü arabirim işaretçisi üzerinde.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)