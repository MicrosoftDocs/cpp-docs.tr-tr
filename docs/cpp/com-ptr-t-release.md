---
title: _com_ptr_t::Release | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c5da56c3c85c17bcd2cd91f9fa5a5f8399e9528
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404281"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft'a özgü**  
  
 Çağrıları **yayın** üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void Release( );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları `IUnknown::Release` kapsüllenmiş arabirim işaretçisini üzerinde oluşturma bir `E_POINTER` bu arabirim işaretçisi, NULL ise hata.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)