---
title: "Çarpan işleçleri ve Modulus işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '%'
- /
dev_langs: C++
helpviewer_keywords:
- operators [C++], multiplicative
- arithmetic operators [C++], multiplicative operators
- modulus operator [C++]
- '* operator'
- division operator [C++], multiplicative operators
- '% operator'
- multiplication operator [C++], multiplicative operators
- multiplicative operators [C++]
- division operator
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb6ad2396b47932f05d9404485e4b32a7e92363b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>Çarpan İşleçleri ve Modulus İşleci
## <a name="syntax"></a>Sözdizimi  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çarpma işleçleri şunlardır:  
  
-   Çarpma (**\***)  
  
-   Bölme (**/**)  
  
-   Mod (kalan bölme gelen) (`%`)  
  
 Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.  
  
 Çarpma işleçleri aritmetik türlerin işlenenlerini alır. Modulus işleci (`%`) işlenenleri Tamsayı türünde olmalıdır, daha sıkı bir gereksinim vardır. (Kayan nokta bölme kalanını almak için çalışma zamanı işlevini [fmod](../c-runtime-library/reference/fmod-fmodf.md).) Dönüşümler ele [standart dönüşümler](standard-conversions.md) işlenenler için uygulanır ve sonuç dönüştürülen türüdür.  
  
 Çarpma işleci, birinci işlenenin ikinci işlenen ile çarpımının sonucu verir.  
  
 Bölme işleci, birinci işlenenin ikinci işlenene bölünmesinin sonucu verir.  
  
 Modulus işleci aşağıdaki ifadeyle verilen kalanı verir nerede *e1* ilk işleneni ve *e2* ikinci: *e1* -(*e1*  /  *e2*) \* *e2*, burada her iki işlenen tam sayı türleridir.  
  
 Bir bölüm ya da mod ifadesinde 0'a bölme tanımlı değildir ve bir çalışma zamanı hatasına neden olur. Bu nedenle, aşağıdaki ifadeler tanımlanmamış, hatalı sonuçlar oluşturur:  
  
```  
i % 0  
f / 0.0  
```  
  
 Çarpma, bölme ya da mod ifadelerinde her iki işlenen de aynı işarete sahipse, sonuç pozitif olur. Aksi halde, sonuç negatif olur. Bir mod işleminin işaretinin sonucu uygulama tarafından tanımlanır.  
  
> [!NOTE]
>  Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Microsoft C++'da, bir mod ifadesinin sonucu her zaman birinci işlenenin işaretiyle aynıdır.  
  
**SON Microsoft özel**  
 Hesaplanan iki tamsayı bölümünü kesin değilse ve yalnızca tek bir işlenen negatif ise, sonuç bölme işleminin vereceği tam değerden daha küçük en büyük tamsayı (büyüklükte, işaret dikkate alınmadığında) olur. Örneğin, hesaplanan değeri-11 / 3-3.666666666. Bu tamsayı bölme -3 sonucudur.  
  
 Çarpma işleçleri arasındaki ilişki kimliği tarafından verilen (*e1* / *e2*) \* *e2*  +  *e1* % *e2* == *e1*.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki program çarpma işleçlerini gösterir. Dikkat edin ya da işleneni `10 / 3` yazmak için açıkça dönüştürülmelidir `float` her iki işlenen türü; böylece bunu önlemek için `float` bölme önce.  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Çarpma İşleçleri](../c-language/c-multiplicative-operators.md)