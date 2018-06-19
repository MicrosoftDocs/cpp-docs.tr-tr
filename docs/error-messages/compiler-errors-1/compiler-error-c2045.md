---
title: Derleyici Hatası C2045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2045
dev_langs:
- C++
helpviewer_keywords:
- C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f81e22214cf9f89a2b2bcabe1bc484647d7f9c0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172842"
---
# <a name="compiler-error-c2045"></a>Derleyici Hatası C2045
'tanımlayıcısı': Etiket yeniden tanımlandı  
  
 Aynı işlevi birden fazla deyime önce etiketi görüntülenir.  
  
 Aşağıdaki örnek C2045 oluşturur:  
  
```  
// C2045.cpp  
int main() {  
   label: {  
   }  
   goto label;  
   label: {}   // C2045  
}  
```