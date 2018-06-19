---
title: Derleyici Hatası C2892 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2892
dev_langs:
- C++
helpviewer_keywords:
- C2892
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f348c56c4ae243738307f12fab568821840e7fe4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242003"
---
# <a name="compiler-error-c2892"></a>Derleyici Hatası C2892
Yerel sınıf üye şablonları olmaması  
  
 Şablonlu üye işlevleri bir işlevde tanımlı bir sınıf geçerli değil.  
  
 Aşağıdaki örnek C2892 oluşturur:  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```