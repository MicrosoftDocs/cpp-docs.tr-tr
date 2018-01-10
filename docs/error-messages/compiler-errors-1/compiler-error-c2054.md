---
title: "Derleyici Hatası C2054 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2054
dev_langs: C++
helpviewer_keywords: C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40a6947e23dfbc71e10ae607e952bee93be2607b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2054"></a>Derleyici Hatası C2054
Beklenen ' (' 'tanımlayıcısı' izlemek için  
  
 İşlevi tanımlayıcı sonunda parantez gerektiren bir bağlamda kullanılır.  
  
 Karmaşık başlatma üzerinde eşittir işareti (=) kaldırarak bu hataya neden.  
  
 Aşağıdaki örnek C2054 oluşturur:  
  
```  
// C2054.c  
int array1[] { 1, 2, 3 };   // C2054, missing =  
```  
  
 Olası çözüm:  
  
```  
// C2054b.c  
int main() {  
   int array2[] = { 1, 2, 3 };  
}  
```