---
title: Derleyici Hatası C3803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3803
dev_langs:
- C++
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d720e2f94cc4a480122413e31b897ec1718ebc15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3803"></a>Derleyici Hatası C3803
'property': özellik kendi erişimciler 'erişimcisi' biri ile uyumsuz bir türe sahip  
  
 İle tanımlanmış bir özellik türü [özelliği](../../cpp/property-cpp.md) için bir erişimci işlevlerini dönüş türüyle eşleşmiyor.  
  
 Aşağıdaki örnek C3803 oluşturur:  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```