---
title: _com_ptr_t::Release | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
dev_langs: C++
helpviewer_keywords: Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 207569a2ad719e907fc46ba2abdd80a0c2e6239e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release
**Microsoft özel**  
  
 Çağrıları **sürüm** üye işlevini **IUnknown** kapsüllenmiş arabirim işaretçisi üzerinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
void Release( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları `IUnknown::Release` kapsüllenmiş arabirim işaretçisi üzerinde gerçekleştiren bir `E_POINTER` bu arabirim işaretçisi ise hata **NULL**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)