---
title: "Mantıksal OR işleci: || | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a826b23f94c4eae4a4fdb5379563b015f05dde71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="logical-or-operator-"></a>Mantıksal OR İşleci: ||
## <a name="syntax"></a>Sözdizimi  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Mantıksal OR işleci (`||`) Boole değeri döndürür **true** birini veya her ikisini işlenenler ise **true** ve döndürür **false** Aksi takdirde. İşlenenler, değerlendirilmeden önce örtük olarak `bool` türüne dönüştürülür ve sonuçta `bool` türü ortaya çıkar. Mantıksal OR'un ilişkilendirilebilirliği soldan sağadır.  
  
 Mantıksal OR işlecinin işlenenlerinin aynı türden olmasına gerek yoktur, ancak integral veya işaretçi türünde olmaları gerekir. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.  
  
 İlk işlenen, mantıksal OR ifadesinin değerlendirilmesine devam edilmeden önce tamamen değerlendirilir ve tüm yan etkiler tamamlanır.  
  
 İkinci işlenen, yalnızca ilk işlenen yanlış (0) olarak değerlendirilirse değerlendirilir. Bu, mantıksal OR ifadesi doğru olduğunda ikinci işlenenin değerlendirilmesine gerek bırakmaz.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Yukarıdaki örnekte, `x``w`, `y` veya `z`'ye eşitse, `printf` işlevinin ikinci bağımsız değişkeni doğru olarak değerlendirilir ve 1 değeri yazdırılır. Aksi takdirde yanlış olarak değerlendirilir ve değerin 0 yazdırılır. Koşullardan biri doğru olarak değerlendirir hemen değerlendirme'ü sona erer.  
  
## <a name="operator-keyword-for-124124"></a>Operator anahtar sözcüğü için &#124; &#124;  
 **Veya** işlecidir metin denk `||`. Erişim için iki yolla **veya** programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C++ yerleşik işleçleri öncelik ve birleşim](cpp-built-in-operators-precedence-and-associativity.md) [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Mantıksal İşleçleri](../c-language/c-logical-operators.md)