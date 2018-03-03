---
title: "Koşullu işleç:? : | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 296ced0754dd12017353469845b3bc4b30e0dc11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="conditional-operator--"></a>Koşullu işleç:? :
## <a name="syntax"></a>Sözdizimi  
  
```  
  
expression ? expression : expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Koşullu işleç (**?:**) (üç işlenen alır) Üçlü işleci. Koşullu işleç aşağıdaki gibi çalışır:  
  
-   İlk işlenen örtülü olarak `bool` öğesine dönüştürülür. Değerlendirilir ve devam etmeden önce tüm yan etkileri tamamlanır.  
  
-   İlk işlenen değerlendirilirse **true** (1), ikinci işlenen değerlendirildiği.  
  
-   İlk işlenen değerlendirilirse **false** (0), üçüncü işleneni değerlendirildiği.  
  
 Koşullu işlecin sonucu, değerlendirilen işlenenin sonucudur — ikinci veya üçüncü. Son iki işlenenden yalnızca biri bir koşullu ifade içinde değerlendirilir.  
  
 Koşullu ifadeler sağdan sola birleşme özelliği içindedir. Birinci işlenen bir entegral veya işaretçi türü olmalıdır. İkinci ve üçüncü işlenenler için aşağıdaki kurallar geçerli olur:  
  
-   Her iki işlenen aynı türde varsa, bu tür bir sonucudur.  
  
-   Her iki işlenen aritmetik veya numaralandırma türleri, olağan aritmetik dönüştürmeler olursa (ele [standart dönüşümler](standard-conversions.md)) için ortak bir türü dönüştürmek için gerçekleştirilir.  
  
-   Her iki işlenen işaretçi türleri olursa ya da bir işaretçi türü ve diğer 0 olarak değerlendirir, sabit bir ifade ise işaretçi dönüşümleri ortak türüne dönüştürmek için gerçekleştirilir.  
  
-   Her iki işlenen başvuru türleri varsa, bunları ortak bir türe dönüştürmek için başvuru dönüşümleri gerçekleştirilir.  
  
-   Her iki işlenen türü void olursa, ortak türü türü void.  
  
-   Her iki işlenen aynı kullanıcı tanımlı tür olursa, ortak türü bu türüdür.  
  
-   İşlenen farklı türleri sahiptir ve işlenen en az biri kullanıcı tanımlı tür varsa dil kuralları ortak türü belirlemek için kullanılır. (Uyarı aşağıya bakın.)  
  
 Yukarıdaki listede bulunmayan ikinci ve üçüncü işlenenlerin birleşimleri geçersizdir. Hem ikinci hem de üçüncü işlenen aynı türdeyse ve her ikisi de l-değeri ise, sonucun türü ortak türdür ve bir l-değerdir.  
  
> [!WARNING]
>  İkinci ve üçüncü işlenen türleri aynı değilse, C++ Standart belirtildiği gibi karmaşık tür dönüştürme kurallarını çağrılır. Bu dönüşümleri yapım ve geçici nesneleri yok etme gibi beklenmeyen davranışlara neden olabilir. Bu nedenle, biz güçlü, kullanıcı tanımlı türler kullanın, ardından açıkça her işlenen ortak bir tür cast (2), ya da (1) kullanıcı tanımlı türler koşullu işleç ile işlenen olarak kullanmaktan kaçının veya öneriyoruz.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Koşullu İfade İşleci](../c-language/conditional-expression-operator.md)