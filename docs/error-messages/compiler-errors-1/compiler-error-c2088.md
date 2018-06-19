---
title: Derleyici Hatası C2088 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2088
dev_langs:
- C++
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d35b736c8945b71a53c4ac5b7372dfed642fed44
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166630"
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