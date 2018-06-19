---
title: Derleyici Hatası C3309 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3309
dev_langs:
- C++
helpviewer_keywords:
- C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 390740c3a7083ede314f58a7bc68432c243583ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33255962"
---
# <a name="compiler-error-c3309"></a>Derleyici Hatası C3309
'macro_name': Modül adı bir makro ya da anahtar sözcük olamaz  
  
 Modül özniteliği name özelliğine geçirdiğiniz değer genişletmek önişlemci sembolü olamaz; bir dize sabit değeri olmalıdır.  
  
 Aşağıdaki örnek C3309 oluşturur:  
  
```  
// C3309.cpp  
#define NAME MyModule  
[module(name="NAME")];   // C3309  
// Try the following line instead  
// [module(name="MyModule")];  
[coclass]  
class MyClass {  
public:  
   void MyFunc();  
};  
  
int main() {  
}  
```