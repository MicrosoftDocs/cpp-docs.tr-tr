---
title: 'Mantıksal AND işleci: &amp; &amp; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '&&'
dev_langs:
- C++
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f683b7ff17a1dd3945f5cb554a7440ab47fad454
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="logical-and-operator-ampamp"></a>Mantıksal AND işleci: &amp;&amp;
## <a name="syntax"></a>Sözdizimi  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Mantıksal AND işleci (**&&**) Boole değeri döndürür **true** her iki işlenen olursa **true** ve döndürür **yanlış** Aksi takdirde. İşlenenler, değerlendirilmeden önce örtük olarak `bool` türüne dönüştürülür ve sonuçta `bool` türü ortaya çıkar. Mantıksal AND soldan sağa birleşim vardır.  
  
 Mantıksal AND işleci için işlenen aynı türde olması gerekmez, ancak bunlar olmalıdır tamsayı veya işaretçi türü. İşlenenler, genel olarak ilişkisel veya eşitlik ifadeleridir.  
  
 İlk işlenen tamamen değerlendirilir ve tüm yan etkileri mantıksal ve ifadesi değerlendirmesi devam etmeden önce tamamlanır.  
  
 Yalnızca ilk işleneni (sıfır) true olarak değerlendirilirse ikinci işlenen değerlendirilir. Mantıksal ve ifade false olduğunda bu değerlendirmeyi ikinci işlenen gereksiz değerlendirmesi ortadan kaldırır. Bu kullanabileceğiniz null işaretçi başvurusunun kaldırılmasının, önlemek için aşağıdaki örnekte gösterildiği gibi değerlendirmesi:  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Varsa `pch` null (0) ifade sağ tarafındaki değerlendirildiği hiçbir zaman. Bu nedenle, null işaretçi üzerinden atama mümkün değildir.  
  
## <a name="operator-keyword-for-"></a>Operator anahtar sözcüğü için & &  
 **Ve** işlecidir metin denk **&&**. Erişim için iki yolla **ve** programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ yerleşik işleçleri öncelik ve birleşim](cpp-built-in-operators-precedence-and-associativity.md) [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Mantıksal İşleçleri](../c-language/c-logical-operators.md)