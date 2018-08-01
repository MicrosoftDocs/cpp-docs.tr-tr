---
title: 'Koşullu işleç:? : | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '?:'
- '?'
dev_langs:
- C++
helpviewer_keywords:
- conditional operators [C++]
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 205a03323a765940ce8cdc5def413faa716fa2fc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402210"
---
# <a name="conditional-operator--"></a>Koşullu işleç:? :
## <a name="syntax"></a>Sözdizimi  
  
``` 
expression ? expression : expression  
``` 
  
## <a name="remarks"></a>Açıklamalar  
 Koşullu işleç (**?:**) (üç işlenen alır) bir Üçlü işleçtir. Koşullu işleç aşağıdaki gibi çalışır:  
  
-   İlk işlenen örtülü olarak dönüştürülür **bool**. Değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlanır.  
  
-   Birinci işlenenin değerlendirilirse **true** (1), ikinci işlenenin değerlendirilir.  
  
-   Birinci işlenenin değerlendirilirse **false** (0), üçüncü işlenen değerlendirilir.  
  
 Koşullu işlecin sonucu, değerlendirilen işlenenin sonucudur — ikinci veya üçüncü. Son iki işlenenden yalnızca biri bir koşullu ifade içinde değerlendirilir.  
  
 Koşullu ifadeler sağdan sola birleşme özelliği içindedir. Birinci işlenen bir entegral veya işaretçi türü olmalıdır. İkinci ve üçüncü işlenenleri için aşağıdaki kurallar geçerlidir:  
  
-   Her iki işlenen de aynı türde ise, sonuç o türde olur.  
  
-   Her iki işlenen de aritmetik veya numaralandırma, olağan aritmetik dönüştürmeler türlerindeyse (ele [standart dönüştürmeler](standard-conversions.md)) bunları ortak bir türe dönüştürmek için gerçekleştirilir.  
  
-   Her iki işlenen de işaretçi türlerindeyse veya biri işaretçi türünde ve diğer 0 olarak değerlendirilen sabit bir ifade ise, bunları ortak bir türe dönüştürmek için işaretçi dönüşümleri gerçekleştirilir.  
  
-   Her iki işlenen de başvuru türlerindeyse, bunları ortak bir türe dönüştürmek için başvuru dönüşümleri gerçekleştirilir.  
  
-   Her iki işlenen void türündeyse, ortak tür void türüdür.  
  
-   Her iki işlenen de aynı kullanıcı tanımlı türde ise, ortak tür o türüdür.  
  
-   İşlenenleri farklı türlere sahip ve en az bir işlenen kullanıcı tanımlı türe sahipse dil kuralları ortak türünü belirlemek için kullanılır. (Aşağıdaki uyarı bakın.)  
  
 Yukarıdaki listede bulunmayan ikinci ve üçüncü işlenenlerin birleşimleri geçersizdir. Hem ikinci hem de üçüncü işlenen aynı türdeyse ve her ikisi de l-değeri ise, sonucun türü ortak türdür ve bir l-değerdir.  
  
> [!WARNING]
>  İkinci ve üçüncü işlenen türleri aynı değilse, C++ standardında belirtildiği gibi karmaşık tür dönüştürme kurallarını sonra çağrılır. Bu dönüştürmeler, oluşturma ve geçici nesnelerin yok edilmesi gibi beklenmeyen davranışlara neden olabilir. Bu nedenle, biz kesinlikle, kullanıcı tanımlı türler kullanın, ardından açıkça her işlenen ortak bir türe dönüştürün (2), ya da (1) kullanıcı tanımlı türler koşullu işleç içeren işlenen olarak kullanmaktan kaçının veya önerin.  
  
## <a name="example"></a>Örnek  
  
```cpp 
// expre_Expressions_with_the_Conditional_Operator.cpp  
// compile with: /EHsc  
// Demonstrate conditional operator  
#include <iostream>  
using namespace std;  
int main() {  
   int i = 1, j = 2;  
   cout << ( i > j ? i : j ) << " is greater." << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Koşullu İfade İşleci](../c-language/conditional-expression-operator.md)