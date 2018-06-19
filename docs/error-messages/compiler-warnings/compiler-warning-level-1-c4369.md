---
title: Derleyici Uyarısı (düzey 1) C4369 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4369
dev_langs:
- C++
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63445f0713b43ce7fde418ebd9d65403965c07ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276535"
---
# <a name="compiler-warning-level-1-c4369"></a>Derleyici Uyarısı (düzey 1) C4369
'Numaralandırıcı': Numaralayıcı değeri 'value' 'type' temsil edilemez, değer 'yeni_değer'.  
  
 Belirtilen temel tür için en büyük değerden daha büyük olması için bir numaralandırıcı hesaplanır.  Bu taşmaya neden oldu ve derleyici türü için olası en düşük değer Numaralandırıcı değerine sarılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4369 oluşturur.  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```