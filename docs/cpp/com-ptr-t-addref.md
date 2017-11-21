---
title: _com_ptr_t::AddRef | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::AddRef
dev_langs: C++
helpviewer_keywords: AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e1230ac8bcf210e519420e8fb4ef84e77bcd4869
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrtaddref"></a>_com_ptr_t::AddRef
**Microsoft özel**  
  
 Çağrıları `AddRef` üye işlevini **IUnknown** kapsüllenmiş arabirim işaretçisi üzerinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
void AddRef( );  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrıları `IUnknown::AddRef` kapsüllenmiş arabirim işaretçisi üzerinde gerçekleştiren bir `E_POINTER` işaretçi ise hata **NULL**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t sınıfı](../cpp/com-ptr-t-class.md)