---
title: "Derleyici Uyarısı (düzey 1) C4530 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: adfa006e3b84517601237bbd844ac983115e74ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4530"></a>Derleyici Uyarısı (düzey 1) C4530
C++ özel durum işleyici olarak kullanılır, ancak semantiği bırakma etkin değil. /EHsc belirtin  
  
 C++ özel durum işleme kullanıldı ancak [/EHsc](../../build/reference/eh-exception-handling-model.md) seçilmedi.  
  
 /EHsc seçeneği etkinleştirilmemiş zaman çerçevesinde, throw yapılması işlevi throw yakalama işlevi arasındaki otomatik depolama sahip bir nesne yok edilmez. Otomatik depolama sahip bir nesne ancak, oluşturulan bir **deneyin** veya **catch** bloğu yok etme.  
  
 Aşağıdaki örnek C4530 oluşturur:  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Uyarıyı çözmek için /EHsc örnekle derleyin.