---
title: "Derleyici Hatası C2357 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46fe3b489f32b7eb0243b1b5cb03d04b69b38c95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2357"></a>Derleyici Hatası C2357
'tanımlayıcısı': 'type' türünde bir işlev olmalıdır  
  
 Kodunuzu bir sürümünü bildirir `atexit` sürümüyle eşleşmiyor işlevi derleyici tarafından dahili olarak bildirilen. Bildirme `atexit` gibi:  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 Daha fazla bilgi için bkz: [init_seg](../../preprocessor/init-seg.md).  
  
 Aşağıdaki örnek C2357 oluşturur:  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```