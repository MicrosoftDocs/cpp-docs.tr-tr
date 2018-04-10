---
title: Derleyici Uyarısı (düzey 1) C4129 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6405c7c156f34b49ab892304ee51a6b996ac2595
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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