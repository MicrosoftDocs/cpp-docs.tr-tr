---
title: "Derleyici Hatası C3799 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3799
dev_langs: C++
helpviewer_keywords: C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f26afc9573cc12b2f13c83911188e677ce134a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3799"></a>Derleyici Hatası C3799
Dizin oluşturulmuş özellik boş parametre listesi sahip olamaz  
  
Dizinli bir özelliği yanlış bildirildi. Daha fazla bilgi için bkz: [nasıl yapılır: kullanım özellikleri C + +/ CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3799 oluşturur ve nasıl düzeltileceği gösterir.  
  
```cpp  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```