---
title: 'Eşitlik işleçleri: == ve! = | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 073e642b99dea4eb6f77fd1e79731713748f1f61
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403121"
---
# <a name="equality-operators--and-"></a>Eşitlik İşleçleri: == ve !=
## <a name="syntax"></a>Sözdizimi  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İkili eşitlik işleçleri işlenenleri katı eşitlik ve eşitsizlik için karşılaştırın.  
  
 Eşitlik işleçleri eşit (`==`) ve eşit değildir (`!=`), ilişkisel işleçler daha düşük önceliğe sahip, ancak benzer şekilde davranır. Bu işleçler için sonuç türü **bool**.  
  
 Eşittir işleci (`==`) döndürür **true** (1) Eğer her iki işlenen de aynı değere sahip; Aksi halde **false** (0). Not-eşittir operatörü (`!=`) döndürür **true** işlenenler aynı değeri; yoksa, aksi halde döndürür **false**.  
  
## <a name="operator-keyword-for-"></a>İçin işleç anahtar sözcüğü! =  
 `not_eq` işleci, `!=` öğesinin metin eşdeğeridir. Erişmenin iki yöntemi vardır `not_eq` programlarınızda işleci: üstbilgi dosyasını dahil `iso646.h`, ya da derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırakma) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
 Eşitlik işleçleri, aynı türde üye işaretçileri karşılaştırabilirsiniz. Böyle bir Karşılaştırmada işaretçi-üye dönüşümleri gerçekleştirilir. Üye işaretçileri için 0 olarak değerlendirilen sabit bir ifade ayrıca karşılaştırılabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C İlişkisel ve Eşitlik İşleçleri](../c-language/c-relational-and-equality-operators.md)