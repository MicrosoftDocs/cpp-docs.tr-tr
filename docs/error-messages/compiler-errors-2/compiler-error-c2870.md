---
title: Derleyici Hatası C2870 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe9f47a96422493d6d731a18add8c23ff683f14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2870"></a>Derleyici Hatası C2870
'name': ad alanı tanımını dosya kapsamda ya da hemen başka bir ad alanı tanımını içinde gösterilmesi gerekir  
  
 Ad tanımlı `name` yanlış. Ad alanları (dışında tüm blokları ve sınıfları) dosya kapsamında tanımlanması gerekir ya da başka bir ad alanı içinde hemen.  
  
 Aşağıdaki örnek C2870 oluşturur:  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```