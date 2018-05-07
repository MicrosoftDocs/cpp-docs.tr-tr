---
title: Derleyici Hatası C2357 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c8739576eced6b831f5c3b72d85417e2daabb06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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