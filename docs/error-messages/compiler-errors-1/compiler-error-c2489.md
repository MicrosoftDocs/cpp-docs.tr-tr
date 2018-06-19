---
title: Derleyici Hatası C2489 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2489
dev_langs:
- C++
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44672cbfc519b37b1d7c1e42ab2cf0137f93394f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196457"
---
# <a name="compiler-error-c2489"></a>Derleyici Hatası C2489
'tanımlayıcısı': 'naked' işlevinde işlevi kapsamında izin verilmiyor otomatik veya kayıt değişkeni başlatıldı  
  
 Daha fazla bilgi için bkz: [naked](../../cpp/naked-cpp.md).  
  
 Aşağıdaki örnek C2489 oluşturur:  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```