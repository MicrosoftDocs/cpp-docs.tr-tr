---
title: "Derleyici Hatası C2088 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2088
dev_langs: C++
helpviewer_keywords: C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0798acfa554a0a3911e40c221db5fdb67e008468
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2088"></a>Derleyici Hatası C2088
'işleci': 'sınıf anahtarı' için geçersiz  
  
 İşleci, yapı veya birlik için tanımlanmadı. Bu hata yalnızca C kodu için geçerli olur.  
  
 Aşağıdaki örnek, üç kez C2088 oluşturur:  
  
```  
// C2088.c  
struct S {  
   int m_i;   
} s;  
  
int main() {  
   int i = s * 1;   // C2088  
   struct S s2 = +s;   // C2088  
   s++;   // C2088  
}  
```