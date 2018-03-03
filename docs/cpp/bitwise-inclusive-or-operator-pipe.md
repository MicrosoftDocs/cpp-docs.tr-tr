---
title: "Bit düzeyinde kapsamlı OR işleci: || Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eaef650cc747cdb9e628ae3b786bc1c1e21b5bdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-inclusive-or-operator-"></a>Bit Düzeyinde Kapsamlı OR İşleci: |
## <a name="syntax"></a>Sözdizimi  
  
```  
  
expression   
|  
 expression  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bit düzeyinde kapsamlı OR işleci (**&#124;**), ilk işleneninin ikinci işleneninin karşılık gelen bit her bit karşılaştırır. Her iki bit 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi halde, karşılık gelen sonuç bit 0 olarak ayarlanır.  
  
 Bit düzeyinde kapsamlı OR işlecinin her iki işleneni de, integral türde olmalıdır. Olağan aritmetik dönüştürmeler ele [standart dönüşümler](standard-conversions.md) işlenenler için uygulanır.  
  
## <a name="operator-keyword-for-124"></a>Operator anahtar sözcüğü için &#124;  
 `bitor` İşlecidir metin denk **&#124;**. Erişim için iki yolla `bitor` programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Bit Düzeyinde İşleçler](../c-language/c-bitwise-operators.md)

