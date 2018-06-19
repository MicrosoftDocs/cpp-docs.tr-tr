---
title: Derleyici Hatası C3176 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3176
dev_langs:
- C++
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fedeb9861d725e9c955bb55903b49ef9fefa586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248475"
---
# <a name="compiler-error-c3176"></a>Derleyici Hatası C3176
'type': yerel değerin türü bildiremezsiniz  
  
 Bir sınıf, yalnızca genel kapsamlı bir değer türü olarak bildirilebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3176 oluşturur.  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```