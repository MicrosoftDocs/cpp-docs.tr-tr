---
title: Derleyici Uyarısı (düzey 1) C4129 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc095a32e5cb0d5a0bf240282e11c3fa3382ffe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4129"></a>Derleyici Uyarısı (düzey 1) C4129
'character': Tanınmayan karakteri kaçış sırası  
  
 `character` İzleyen bir ters eğik çizgi (\\) bir karakter ya da dize sabiti geçerli kaçış sırası tanınmıyor. Ters eğik çizgi göz ardı ve değil yazdırılabilir. Ters eğik çizgi aşağıdaki karakter yazdırılır.  
  
 Tek bir ters eğik çizgi yazdırmak için bir çift ters eğik çizgi belirtin (\\\\).  
  
 C++ standart, bölüm 2.13.2'kaçış sıraları açıklanmaktadır.  
  
 Aşağıdaki örnek C4129 oluşturur:  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```