---
title: Derleyici Hatası C2513 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 704e5d71301886d46c8a2ce08d7ea34ef1f8275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228264"
---
# <a name="compiler-error-c2513"></a>Derleyici Hatası C2513
'type': hiçbir değişken bildirilen '=' önce  
  
 Hiçbir değişken tanımlayıcıyla bildiriminde tür belirteci görüntülenir.  
  
 Aşağıdaki örnek C2513 oluşturur:  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Bu hata, Visual Studio .NET 2003'te yapılan bir derleyici uyumluluğu iş sonucunda da oluşturulabilir: artık izin TypeDef başlatma. Bir typedef başlatma standardına göre izin verilmiyor ve şimdi derleyici hatası oluşturur.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Silmek için bir alternatif olacaktır `typedef` bu türle aynı ada sahip bir değişken oluşturun ve tür adı gizlemek için toplama başlatıcı listesi, ancak bu bir değişkeni tanımlamak için önerilmez.