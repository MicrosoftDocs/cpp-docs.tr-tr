---
title: Derleyici Hatası C2081 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2081
dev_langs:
- C++
helpviewer_keywords:
- C2081
ms.assetid: 7db9892d-364d-4178-a49d-f8398ece09a0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 165217b3ea4d50dc965927419786a01a6cc92af3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166867"
---
# <a name="compiler-error-c2081"></a>Derleyici Hatası C2081
'tanımlayıcısı': biçimsel parametresi listesi geçersiz ad  
  
 Tanımlayıcı Sözdizimi hatası neden oldu.  
  
 Bu hata için biçimsel parametresi listesi eski stili kullanılarak neden olabilir. Biçimsel parametresi listesinde biçimsel parametresi türünü belirtmeniz gerekir.  
  
 Aşağıdaki örnek C2081 oluşturur:  
  
```  
// C2081.c  
void func( int i, j ) {}  // C2081, no type specified for j  
```  
  
 Olası çözüm:  
  
```  
// C2081b.c  
// compile with: /c  
void func( int i, int j ) {}  
```