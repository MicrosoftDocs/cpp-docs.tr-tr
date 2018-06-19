---
title: Derleyici Hatası C2774 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2774
dev_langs:
- C++
helpviewer_keywords:
- C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a6fc100bf7cd4a57c5c23630b28c41d92cf43d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234960"
---
# <a name="compiler-error-c2774"></a>Derleyici Hatası C2774
'tanımlayıcısı': Bu özellik ile ilişkili 'put' yöntemi yok  
  
 İle bir veri üyesi bildirilen [özelliği](../../cpp/property-cpp.md) hiç `put` işlevi, ancak bir ifadenin değerini ayarlama dener.  
  
 Aşağıdaki örnek C2774 oluşturur:  
  
```  
// C2774.cpp  
struct A {  
   __declspec(property(get=GetProp)) int prop;  
   int GetProp(void);  
  
   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;  
   int GetProp2(void);  
   void PutProp2(int);  
};  
  
int main() {  
   A* pa = new A;  
   int val = 0;  
   pa->prop = val;   // C2774  
   pa->prop++;   // C2774  
}  
```