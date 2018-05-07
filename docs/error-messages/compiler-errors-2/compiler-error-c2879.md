---
title: Derleyici Hatası C2879 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba1738da7d349ecafd9f10f31d8f05ac1f12df0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2879"></a>Derleyici Hatası C2879
'simgesi': varolan bir ad bir diğer ad ad alanı diğer ad tanımı verilebilir yalnızca  
  
 Oluşturamazsınız bir [ad alanı diğer adı](../../cpp/namespaces-cpp.md#namespace_aliases) için bir ad alanı dışında bir simge.  
  
 Aşağıdaki örnek C2879 oluşturur:  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```