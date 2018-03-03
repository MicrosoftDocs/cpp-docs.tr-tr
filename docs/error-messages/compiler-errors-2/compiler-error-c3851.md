---
title: "Derleyici Hatası C3851 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c5f0cca8f3c1dfc4b3b35d494ebf73459a74d03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3851"></a>Derleyici Hatası C3851
'char': evrensel-karakter-name temel karakter kümesinde bir karakter belirtemezsiniz  
  
 C++ derlenmiş kod içinde bir dize dışında temel kaynak karakter kümesinde bir karakter veya karakter sabiti temsil eden bir evrensel karakter adı kullanamazsınız. Daha fazla bilgi için bkz: [karakter kümesi](../../cpp/character-sets2.md). C derlenmiş kod içinde bir evrensel karakter adını karakterler 0x20 0x7f, ('$'), 0x24 dışında (dahil) aralığında 0x40 kullanamazsınız (' @'), ya da 0x60 ('' ').  
  
 Aşağıdaki örnekler C3851 oluşturmak ve nasıl düzeltileceği göster:  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```