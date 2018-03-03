---
title: "Bit düzeyinde özel OR işleci: ^ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d6bd80c7144ea3f4a2288e07b7801612ed62efd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-exclusive-or-operator-"></a>Bit Düzeyinde Özel OR İşleci: ^
## <a name="syntax"></a>Sözdizimi  
  
```  
expression ^ expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
Bit düzeyinde özel OR işleci (**^**), ilk işleneninin ikinci işleneninin karşılık gelen bit her bit karşılaştırır. Bir bit 0'dır ve diğer bit 1 ise, karşılık gelen sonuç biti 1 olarak ayarlanır. Aksi halde, karşılık gelen sonuç bit 0 olarak ayarlanır.  
  
Bit düzeyinde özel OR işleci için iki işlenen tam sayı türleri olmalıdır. Olağan aritmetik dönüştürmeler ele [standart dönüşümler](standard-conversions.md) işlenenler için uygulanır.  
  
## <a name="operator-keyword-for-"></a>Operator anahtar sözcüğü için ^  
**Xor** işlecidir metin denk  **^** . Erişim için iki yolla **xor** programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   


