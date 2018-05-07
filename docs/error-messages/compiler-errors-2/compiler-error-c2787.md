---
title: Derleyici Hatası C2787 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2787
dev_langs:
- C++
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6b45d27c295b37d859d6451281f52c166dc1691
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2787"></a>Derleyici Hatası C2787
'tanımlayıcısı': hiçbir GUID Bu nesneyle ilişkili bırakıldı  
  
 [__Uuidof](../../cpp/uuidof-operator.md) işleci bağlı bir GUID veya türünde bir nesne gibi bir kullanıcı tarafından tanımlanan kullanıcı tarafından tanımlanan bir türü alır. Bağımsız değişken yok GUID ile kullanıcı tanımlı bir tür olduğunda bu hata oluşur.  
  
 Aşağıdaki örnek C2787 oluşturur:  
  
```  
// C2787.cpp  
#include <windows.h>  
struct F {};  
  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;  
  
int main() {  
   __uuidof(F);   // C2787  
   __uuidof(F2);   // OK  
}  
```