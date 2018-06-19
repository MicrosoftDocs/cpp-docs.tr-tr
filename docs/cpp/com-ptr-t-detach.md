---
title: _com_ptr_t::detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fbe8fd203c3fda75e83aee623254676dacaf1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32410586"
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