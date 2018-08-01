---
title: Çarpan işleçleri ve Modulus işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '%'
- /
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b238a496718088f0251faa49281fdc8939c01c7
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408365"
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
  
-   Mod (bölmeden kalan) (`%`)  
  
 Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.  
  
 Çarpma işleçleri aritmetik türlerin işlenenlerini alır. Modulus işleci (`%`), işlenenlerinin integral türünde olmalıdır, bir katı gereksinimine sahiptir. (Kayan nokta bölme kalanını almak için çalışma zamanı işlevini [fmod](../c-runtime-library/reference/fmod-fmodf.md).) İçinde kapsanan dönüştürmeler [standart dönüştürmeler](standard-conversions.md) işlenenlere uygulanır ve sonuç dönüştürülmüş türü verir.  
  
 Çarpma işleci, birinci işlenenin ikinci işlenen ile çarpımının sonucu verir.  
  
 Bölme işleci, birinci işlenenin ikinci işlenene bölünmesinin sonucu verir.  
  
 Mod işleci aşağıdaki ifade tarafından verilen kalanı verir burada *e1* ilk işlenen ve *e2* ikinci: *e1* -(*e1*  /  *e2*) \* *e2*, burada her iki işlenen de integral türleridir.  
  
 Bir bölüm ya da mod ifadesinde 0'a bölme tanımlı değildir ve bir çalışma zamanı hatasına neden olur. Bu nedenle, aşağıdaki ifadeler tanımlanmamış, hatalı sonuçlar oluşturur:  
  
```cpp 
i % 0  
f / 0.0  
```  
  
 Çarpma, bölme ya da mod ifadelerinde her iki işlenen de aynı işarete sahipse, sonuç pozitif olur. Aksi halde, sonuç negatif olur. Bir mod işleminin işaretinin sonucu uygulama tarafından tanımlanır.  
  
> [!NOTE]
>  Çarpma işleçleri tarafından gerçekleştirilen dönüştürmeler taşma veya yetersiz kalma koşulları sağlamadığından, çarpma işleminin sonucu dönüştürme sonrası işlenenlerin türünde gösterilmezse bilgiler kaybolabilir.  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Microsoft C++'da, bir mod ifadesinin sonucu her zaman birinci işlenenin işaretiyle aynıdır.  
  
**END Microsoft özgü**  
 Hesaplanan iki tamsayı bölümünü kesin değilse ve yalnızca tek bir işlenen negatif ise, sonuç bölme işleminin vereceği tam değerden daha küçük en büyük tamsayı (büyüklükte, işaret dikkate alınmadığında) olur. Örneğin, hesaplanan değeri -11 / 3-3.666666666. Bu integral bölümünün sonucu -3 ' dir.  
  
 Çarpma işleçleri arasındaki ilişki Özdeşlik ile verilir (*e1* / *e2*) \* *e2*  +  *e1* % *e2* == *e1*.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki program çarpma işleçlerini gösterir. Unutmayın her iki işleneninin `10 / 3` türüne açıkça dönüştürülmelidir **float** her iki işlenen türü olacak şekilde kesilmesini önlemek için **float** bölme önce.  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçler, öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Çarpma İşleçleri](../c-language/c-multiplicative-operators.md)