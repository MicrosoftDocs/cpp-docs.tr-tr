---
title: Derleyici Hatası C3851 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82104776b2d1153310d0552bd873238333e746f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268845"
---
# <a name="compiler-error-c3851"></a>Derleyici Hatası C3851
'char': evrensel-karakter-name temel karakter kümesinde bir karakter belirtemezsiniz  
  
 C++ derlenmiş kod içinde bir dize dışında temel kaynak karakter kümesinde bir karakter veya karakter sabiti temsil eden bir evrensel karakter adı kullanamazsınız. Daha fazla bilgi için bkz: [karakter kümesi](../../cpp/character-sets.md). C derlenmiş kod içinde bir evrensel karakter adını karakterler 0x20 0x7f, ('$'), 0x24 dışında (dahil) aralığında 0x40 kullanamazsınız (' @'), ya da 0x60 ('' ').  
  
 Aşağıdaki örnekler C3851 oluşturmak ve nasıl düzeltileceği göster:  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```