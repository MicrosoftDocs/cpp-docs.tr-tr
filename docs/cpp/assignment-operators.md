---
title: "Atama İşleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '>>='
- xor_eq
- '&='
- <<=
- -=
- and_eq
- ^=
- '|='
- /=
- '%='
- or_eq
- +=
- '*='
dev_langs: C++
helpviewer_keywords:
- or_eq operator
- '&= operator'
- operators [C++], assignment
- assignment operators [C++], C++
- xor_eq operator
- += operator
- and_eq operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- assignment operators [C++]
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c84244a619873dcd61b52dee317a751ff28ec3ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="assignment-operators"></a>Atama İşleçleri
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      expression assignment-operator expression   
assignment-operator : one of  
   =   *=   /=   %=   +=   -=   <<=   >>=   &=   ^=   |=  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Atama işleçleri, sol işlenen tarafından belirlenen nesnede bir değer depolar. İki tür arama işlemi vardır: İkinci işlenen değerinin ilk işlenen tarafından belirtilen nesne içinde depolandığı basit atama ve sonucu depolamadan önce içinde bir aritmetik, kaydırma veya bit düzeyinde işlemin yapıldığı birleşik atama. Aşağıdaki tabloda, = işleci hariç tüm atama işleçleri birleşik atama işleçleridir.  
  
### <a name="assignment-operators"></a>Atama İşleçleri  
  
|İşleç|Açıklama|  
|--------------|-------------|  
|**=**|Birinci işlenen (basit atama) tarafından belirtilen nesnede ikinci işlenenin değerini depolar.|  
|**\*=**|Birinci işlenenin değeriyle ikinci işlenenin değerini çarpar; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|`/=`|Birinci işlenenin değerini ikinci işlenenin değerine böler; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|`%=`|İkinci işlenenin değeri tarafından belirtilen birinci işlenenin modüllerini alır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|`+=`|İkinci işlenenin değerine birinci işlenenin değerini ekler; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|**-=**|İkinci işlenenin değerinden ilk işlenenin değerini çıkarır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|**<\<=**|Birinci işlenenin değerini ikinci işlenenin değeri tarafından belirtilen bit sayısının soluna kaydırır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|**>>=**|Birinci işlenenin değerini ikinci işlenenin değeri tarafından belirtilen bit sayısının sağına kaydırır; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|**&=**|Birinci ve ikinci işlenenden bit seviyesinde VE elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|`^=`|Birinci ve ikinci işlenenden bit seviyesinde dışlamalı VEYA elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
|`&#124;=`|Birinci ve ikinci işlenenden bit seviyesinde kapsamalı VEYA elde eder; sonucu ilk işlenen tarafından belirtilen nesnede depolar.|  
  
 **İşleç Anahtar Sözcükleri**  
  
 Bileşik atama işleçlerinden üçünün metin eşdeğerleri vardır. Bunlar:  
  
|İşleç|Eşdeğer|  
|--------------|----------------|  
|**&=**|`and_eq`|  
|`&#124;=`|`or_eq`|  
|`^=`|`xor_eq`|  
  
 Bu işleç anahtar sözcükleri programlarınızı içinde erişmek için iki yolu vardır: üst bilgi dosyasını dahil `iso646.h`, veya ile derleme [/Za](../build/reference/za-ze-disable-language-extensions.md) (dil uzantılarını devre dışı bırak) derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Assignment_Operators.cpp  
// compile with: /EHsc  
// Demonstrate assignment operators  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;  
  
   a += b;      // a is 9  
   b %= a;      // b is 6  
   c >>= 1;      // c is 5  
   d |= e;      // Bitwise--d is 0xFFFF   
  
   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl  
         << "a += b yields " << a << endl  
         << "b %= a yields " << b << endl  
         << "c >>= 1 yields " << c << endl  
         << "d |= e yields " << hex << d << endl;  
}  
```  
  
## <a name="simple-assignment"></a>Basit atama  
 Basit atama işleci (=) ilk işlenen tarafından belirtilen nesne depolanması için ikinci işlenen değeri neden olur. Hem nesnelerini aritmetik türleri varsa, türde bir değer depolama önce sol, sağ işleneni dönüştürülür.  
  
 Const ve volatile türden nesneler l değerleri için yalnızca geçici olmayan veya const veya volatile türlerinin atanabilir.  
  
 Sınıf türü (yapısı, union ve sınıf türleri) nesnelere atama işleci adlı bir işlev tarafından gerçekleştirilen =. Bit düzeyinde kopyasını gerçekleştirmek için bu işleci işlevi varsayılan davranışı değildir; Ancak, bu davranış aşırı yüklenmiş işleçler kullanılarak değiştirilebilir. (Bkz [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md) daha fazla bilgi için.)  
  
 Verilen temel sınıfından belirsizliğe türetilmiş herhangi sınıfın bir nesnesi için temel sınıfın bir nesnesi atanabilir. Ters temel sınıfından türetilmiş bir sınıf örtük bir dönüştürme olduğundan true değil ancak taban sınıfı için değil, türetilmiş sınıf. Örneğin:  
  
```  
// expre_SimpleAssignment.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
class ABase  
{  
public:  
    ABase() { cout << "constructing ABase\n"; }  
};  
  
class ADerived : public ABase  
{  
public:  
    ADerived() { cout << "constructing ADerived\n"; }  
};  
  
int main()  
{  
    ABase aBase;  
    ADerived aDerived;  
  
    aBase = aDerived; // OK  
    aDerived = aBase; // C2679  
}  
```  
  
 Başvuru türleri atamalar atama başvuru işaret ettiği nesnesine yapılmakta gibi hareket etmesini.  
  
 Sınıf türü nesneler için atama başlatma farklıdır. Farklı atama ve başlatma göstermeye olması, kodu düşünün  
  
```  
UserType1 A;  
UserType2 B = A;  
```  
  
 Önceki kod bir başlatıcı gösterir; Oluşturucusu çağırır `UserType2` türünde bir bağımsız değişken alan `UserType1`. Kod verilen  
  
```  
UserType1 A;  
UserType2 B;  
  
B = A;  
```  
  
 atama deyimi  
  
```  
B = A;   
```  
  
 Aşağıdaki etkileri biri olabilir:  
  
-   İşlev işleci çağırmak için = `UserType2`, işleci sağlanan = ile sağlanan bir `UserType1` bağımsız değişkeni.  
  
-   Açık Dönüşüm işlevini çağırın `UserType1::operator UserType2`, bu tür bir işlevi varsa.  
  
-   Bir oluşturucu çağrısı `UserType2::UserType2`, bu tür bir oluşturucuya alan var. sağlanan bir `UserType1` bağımsız değişkeni ve sonucu kopyalar.  
  
## <a name="compound-assignment"></a>Bileşik atama  
 Tabloda gösterilen bileşik atama işleçleri [atama işleçleri](../cpp/assignment-operators.md), formda belirtilen *e1* `op` =  *e2*, burada *e1* const türünde değil değiştirilebilir bir l-değeri ve *e2* aşağıdakilerden biri:  
  
-   Bir aritmetik tür  
  
-   Bir işaretçi varsa `op` olan + veya -  
  
 *E1* `op` =  *e2* form davranır olarak *e1* *e1 =* `op` *e2*, ancak *e1* yalnızca bir kez değerlendirilir.  
  
 Numaralandırılmış bir türe yapılan bileşik atama bir hata iletisi oluşturur. Sol işlenen bir işaretçi türü ise, sağ işlenen bir işaretçi türünde olmalıdır veya 0 olarak değerlendirilen bir sabit bir ifade olması gerekir. Sol işlenen bir tamsayı türü ise, sağ işlenen bir işaretçi türü olmamalıdır.  
  
## <a name="result-of-assignment-operators"></a>Atama İşleçleri sonucu  
 Atama İşleçleri Atama sonra sol işleneni tarafından belirtilen nesne değerini döndürür. Sonuç türü sol işleneni türüdür. Bir atama ifadesi her zaman bir l-değeri sonucudur. Bu işleçlere sağdan sola birleşim vardır. Sol işleneni değiştirilebilir l-değeri olmalıdır.  
  
 ANSI C atama ifade sonuç l-değeri değil. Bu nedenle, yasal C++ ifade `(a += b) += c` c dilinde geçersiz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C Atama İşleçleri](../c-language/c-assignment-operators.md)