---
title: Derleyici Hatası C2724 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2724
dev_langs:
- C++
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0bf22539a53a0eee78a7d0be110d7459cf5d4f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2724"></a>Derleyici Hatası C2724
'tanımlayıcısı': 'static' kullanılmamalıdır üzerinde dosya kapsamında tanımlı üye işlevleri  
  
 Statik üye işlevleri ile dış bağlantı bildirilmelidir.  
  
 Aşağıdaki örnek C2724 oluşturur:  
  
```  
// C2724.cpp  
class C {  
   static void func();  
};  
  
static void C::func(){};   // C2724  
// try the following line instead  
// void C::func(){};  
```