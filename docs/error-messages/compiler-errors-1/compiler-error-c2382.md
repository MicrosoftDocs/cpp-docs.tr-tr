---
title: Derleyici Hatası C2382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2382
dev_langs:
- C++
helpviewer_keywords:
- C2382
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a17a1038e7e5923e0ee7570754d5c146b55a06f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2382"></a>Derleyici Hatası C2382
'function': şemadaki; farklı bir özel durum belirtimleri  
  
 Altında [/Za](../../build/reference/za-ze-disable-language-extensions.md), bu hata, bir işlev aşırı yüklemesiyle yalnızca denendi belirtir. [özel durum belirtimi](../../cpp/exception-specifications-throw-cpp.md).  
  
 Aşağıdaki örnek C2382 oluşturur:  
  
```  
// C2382.cpp  
// compile with: /Za /c  
void f1(void) throw(int) {}  
void f1(void) throw(char) {}   // C2382  
void f2(void) throw(char) {}   // OK  
```