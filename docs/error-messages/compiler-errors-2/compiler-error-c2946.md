---
title: Derleyici Hatası C2946 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2946
dev_langs:
- C++
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9485f424306d66514c9e919f13ff5988f8b0d1f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2946"></a>Derleyici Hatası C2946
Açık örnekleme; 'class' Şablon sınıfı uzmanlık değil  
  
 Açıkça nontemplated sınıfı örneği oluşturulamıyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2946 oluşturur.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```