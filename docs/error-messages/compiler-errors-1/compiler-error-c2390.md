---
title: "Derleyici Hatası C2390 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2390
dev_langs: C++
helpviewer_keywords: C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93d4cbd9de274d53fdc0369c2b85dbf2e97af48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2390"></a>Derleyici Hatası C2390
'tanımlayıcısı': 'tanımlayıcısı' yanlış depolama sınıfı  
  
 Depolama sınıfı genel kapsam tanımlayıcısı geçerli değil. Varsayılan depolama sınıfı geçersiz sınıf yerine kullanılır.  
  
 Olası çözümler:  
  
-   Tanımlayıcı bir işlev ise, kendisiyle bildirme `extern` depolama.  
  
-   Tanımlayıcı biçimsel parametresi veya yerel değişken ise, otomatik depolama ile bildirin.  
  
-   Tanımlayıcı genel değişkeni ise hiçbir depolama sınıfı (otomatik depolama) bildirin.  
  
## <a name="example"></a>Örnek  
  
-   Aşağıdaki örnek C2390 oluşturur:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```