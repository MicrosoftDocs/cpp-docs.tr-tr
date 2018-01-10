---
title: "Bit düzeyinde AND işleci: &amp; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: bitand
dev_langs: C++
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3d74a39c68e4c16e55837a87e027e9e5991351f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-and-operator-amp"></a>Bit düzeyinde AND işleci:&amp;
## <a name="syntax"></a>Sözdizimi  
  
```  
  
expression   
&  
 expression  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İfadeler diğer ve-ifadeleri, veya olabilir (konu aşağıda belirtilen türü kısıtlamaları) eşitlik ifadeleri, ilişkisel ifadeleri, ek ifadeler, çarpma ifadeleri, üye ifadeleri, cast ifadeleri birli işaretçi deyimler, ifadeler ya da birincil ifadeler sonek.  
  
 Bit düzeyinde AND işleci (**&**) karşılık gelen bit ikinci işleneninin ilk işleneninin her bit karşılaştırır. Her iki BITS 1 ise, karşılık gelen sonuç bit 1 olarak ayarlanır. Aksi halde, karşılık gelen sonuç bit 0 olarak ayarlanır.  
  
 Bit düzeyinde AND işleci için iki işlenen tam sayı türleri olmalıdır. Olağan aritmetik dönüştürmeler ele [standart dönüşümler](standard-conversions.md), işlenen uygulanır.  
  
## <a name="operator-keyword-for-"></a>Operator anahtar sözcüğü için &  
 `bitand` İşlecidir metin denk  **&** . Erişim için iki yolla `bitand` programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](cpp-built-in-operators-precedence-and-associativity.md)  
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Bit Düzeyinde İşleçler](../c-language/c-bitwise-operators.md)