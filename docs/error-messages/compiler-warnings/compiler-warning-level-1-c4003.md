---
title: Derleyici Uyarısı (düzey 1) C4003 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4003
dev_langs:
- C++
helpviewer_keywords:
- C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a90202bfc06d50089e2ac283a5060bc431b9549c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274264"
---
# <a name="compiler-warning-level-1-c4003"></a>Derleyici Uyarısı (düzey 1) C4003
Makro 'tanımlayıcısı' için gerçek yeterli parametreleri  
  
 Makro tanımı'ndaki biçimsel parametresi sayısı makrosu gerçek parametrelerinde sayısını aşıyor. Eksik parametre için boş metin makrosu genişletme değiştirir.  
  
 Aşağıdaki örnek C4003 oluşturur:  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```