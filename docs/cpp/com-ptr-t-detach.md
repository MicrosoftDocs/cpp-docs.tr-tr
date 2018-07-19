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
ms.openlocfilehash: c07a9ce1d315c6738472850b987ccb397feda267
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941359"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach
**Microsoft'a özgü**  
  
 Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Ayıklar kapsüllenmiş arabirim işaretçisini döndürür ve ardından kapsüllenmiş işaretçi depolamasını null temizler. Bu, arabirim işaretçisini kapsüllemeden kaldırır. Size kalmıştır çağrılacak olan `Release` döndürülen arabirim işaretçisinde üzerinde.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)