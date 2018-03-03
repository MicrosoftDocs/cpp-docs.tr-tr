---
title: "Eşitlik işleçleri: == ve! = | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2be0d4cf45bbedc5e799b07962c05f845d5f3efe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="equality-operators--and-"></a>Eşitlik İşleçleri: == ve !=
## <a name="syntax"></a>Sözdizimi  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İkili eşitlik işleçleri kendi işlenenler katı eşitlik veya eşitsizlik için karşılaştırın.  
  
 Eşitlik işleçleri eşit (`==`) ve eşit değildir (`!=`), ilişkisel işleçleri daha düşük önceliğe sahip, ancak bunlar benzer şekilde davranır. Bu işleçlere sonuç türü olan `bool`.  
  
 Eşittir işleci (`==`) döndürür **true** (1) ise her iki işlenen aynı değere sahip; Aksi halde döndürür **false** (0). Not-eşittir operatörü (`!=`) döndürür **true** Aksi halde, işlenen aynı değeri; yoksa döndürür **false**.  
  
## <a name="operator-keyword-for-"></a>Operator anahtar sözcüğü için! =  
 `not_eq` işleci, `!=` öğesinin metin eşdeğeridir. Erişim için iki yolla `not_eq` programlarınızı işleci: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 Eşitlik işleçleri aynı türde üye işaretçileri karşılaştırabilirsiniz. Bu tür bir Karşılaştırmada işaretçi-üye dönüşümleri gerçekleştirilir. Üye işaretçileri da 0 olarak değerlendirir, sabit bir ifade karşılaştırılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C İlişkisel ve Eşitlik İşleçleri](../c-language/c-relational-and-equality-operators.md)