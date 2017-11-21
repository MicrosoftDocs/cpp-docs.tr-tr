---
title: _com_ptr_t::detach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::Detach
dev_langs: C++
helpviewer_keywords: Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ddb1d52ab9706293a03be074c3698c35c1bf291c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)