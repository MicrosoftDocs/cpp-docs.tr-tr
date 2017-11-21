---
title: "Derleyici Hatası C3851 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3851
dev_langs: C++
helpviewer_keywords: C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed2a62b859e37455041171c81bb6830db372c697
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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