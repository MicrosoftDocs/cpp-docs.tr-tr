---
title: "Sol kaydırma ve sağ kaydırma işleçleri (&gt; &gt; ve &lt; &lt;) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- <<
- '>>'
dev_langs: C++
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad2da0f4f8807bef5899a32eabda931092641260
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>Sol kaydırma ve sağ kaydırma işleçleri (&gt; &gt; ve &lt; &lt;)
Bit kaydırma işleçleri olan sağa kaydırma işleci (>>), bitleri taşıyan *shift ifade* sağa ve sola kaydırma işleci (<<), bitleri taşıyan *shift-ifade* sol. <sup>1</sup>  
  
## <a name="syntax"></a>Sözdizimi  
  
> *Shift ifade* `<<` *ADDITIVE ifade*  
> *Shift ifade* `>>` *ADDITIVE ifade*  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!IMPORTANT]
> Aşağıdaki açıklamalar ve örnekler Windows X86 ve x64 mimarilerinde geçerlidir. Sola kaydırma ve sağa kaydırma işleçlerinin uygulamaları ARM cihazları için Windows RT'de önemli ölçüde farklılık gösterir. Daha fazla bilgi için "Kaydırma işleçleri" bölümüne bakın [Hello ARM](http://blogs.msdn.com/b/vcblog/archive/2012/10/25/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c.aspx) blog postası.  
  
## <a name="left-shifts"></a>Sola Kaydırmalar  
 Sola kaydırma işleci bitleri neden *shift ifade* sola tarafından belirtilen konumlar sayısına göre değişebilir *ADDITIVE ifade*. Kaydırma işleci tarafından boşaltılmış bit konumları sıfır dolguludur. Sola kaydırma mantıksal bir kaydırmadır (imza biti dahil, sona kaydırılan bitler atılır). Bit düzeyinde kaydırmalar türleri hakkında daha fazla bilgi için bkz: [Bitsel kaydırmalar](http://en.wikipedia.org/wiki/Bitwise_shift).  
  
 Aşağıdaki örnek, işaretsiz sayıların kullanıldığı sola kaydırma işleçlerini gösterir. Bu örnek değeri bir bit kümesi olarak temsil eden bitlere ne olduğunu göstermektedir. Daha fazla bilgi için bkz: [bitset sınıfı](../standard-library/bitset-class.md).  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short1 = 4;      
    bitset<16> bitset1{short1};   // the bitset representation of 4  
    cout << bitset1 << endl;  // 0000000000000100  
  
    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;  // 0000000000001000  
  
    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16  
    bitset<16> bitset3{short3};  
    cout << bitset3 << endl;  // 0000000000010000  
}  
  
```  
  
 İşaretli bir sayıyı sola kaydırırsanız, imza biti etkilenir ve sonuç tanımsız olur. Aşağıdaki örnek, bir 1 bit imza biti konumuna sola kaydırıldığında, Visual C++'ta ne olduğunu gösterir.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 16384;      
    bitset<16> bitset1{short2};  
    cout << bitset1 << endl;  // 0100000000000000   
  
    short short3 = short1 << 1;  
    bitset<16> bitset3{short3};  // 16384 left-shifted by 1 = -32768  
    cout << bitset3 << endl;  // 100000000000000  
  
    short short4 = short1 << 14;  
    bitset<16> bitset4{short4};  // 4 left-shifted by 14 = 0  
    cout << bitset4 << endl;  // 000000000000000    
}  
```  
  
## <a name="right-shifts"></a>Sağa Kaydırmalar  
 Sağa kaydırma işleci bit desende neden *shift ifade* sağ tarafından belirtilen konumlar sayısına göre değişebilir *ADDITIVE ifade*. İşaretsiz sayılar için, kaydırma işleci tarafından boşaltılmış bit konumları sıfır dolguludur. İşaretli sayılar için, imza biti boşaltılmış bit konumlarını doldurmak için kullanılır. Başka bir deyişle, sayı pozitif ise 0 kullanılır ve sayı negatif ise 1 kullanılır.  
  
> [!IMPORTANT]
> İmzalı bir negatif sayının sağ kaydırmasının sonucu uygulama bağımlıdır. Visual C++ bitleri boşaltılmış konumları dolduracak şekilde kullansa da, başka bir uygulamanın da bunu yapacağının garantisi yoktur.  
  
 Bu örnek, işaretsiz sayıların kullanıldığı sağa kaydırma işleçlerini gösterir:  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned short short11 = 1024;  
    bitset<16> bitset11{short11};  
    cout << bitset11 << endl;     // 0000010000000000  
  
    unsigned short short12 = short11 >> 1;  // 512  
    bitset<16> bitset12{short12};  
    cout << bitset12 << endl;     // 0000001000000000  
  
    unsigned short short13 = short11 >> 10;  // 1  
    bitset<16> bitset13{short13};  
    cout << bitset13 << endl;     // 0000000000000001  
  
    unsigned short short14 = short11 >> 11;  // 0  
    bitset<16> bitset14{short14};  
    cout << bitset14 << endl;     // 0000000000000000}  
}  
```  
  
 Sonraki örnek, pozitif işaretli sayılara sahip sağa kaydırma işleçlerini gösterir.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short short1 = 1024;  
    bitset<16> bitset1{short1};  
    cout << bitset1 << endl;     // 0000010000000000  
  
    short short2 = short1 >> 1;  // 512  
    bitset<16> bitset2{short2};  
    cout << bitset2 << endl;     // 0000001000000000  
  
    short short3 = short1 >> 11;  // 0  
    bitset<16> bitset3{short3};     
    cout << bitset3 << endl;     // 0000000000000000  
}  
```  
  
 Sonraki örnek, negatif işaretli tamsayılara sahip sağa kaydırma işleçlerini gösterir.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    short neg1 = -16;  
    bitset<16> bn1{neg1};  
    cout << bn1 << endl;  // 1111111111110000  
  
    short neg2 = neg1 >> 1; // -8  
    bitset<16> bn2{neg2};  
    cout << bn2 << endl;  // 1111111111111000  
  
    short neg3 = neg1 >> 2; // -4  
    bitset<16> bn3{neg3};  
    cout << bn3 << endl;  // 1111111111111100  
  
    short neg4 = neg1 >> 4; // -1  
    bitset<16> bn4{neg4};      
    cout << bn4 << endl;  // 1111111111111111  
  
    short neg5 = neg1 >> 5; // -1   
    bitset<16> bn5{neg5};      
    cout << bn5 << endl;  // 1111111111111111  
}  
```  
  
## <a name="shifts-and-promotions"></a>Kaydırmalar ve Yükseltmeler  
 Bir kaydırma işlecinin her iki tarafındaki ifadelerin de tamsayı türünde olması gerekir. Tamsayı yükseltmeleri açıklanan kurallarına göre gerçekleştirilir [standart dönüşümler](standard-conversions.md). Sonuç türü yükseltilen türü ile aynıdır *shift ifade*.  
  
 Aşağıdaki örnekte, türünde bir değişken `char` için yükseltilmiş bir `int`.  
  
```cpp  
#include <iostream>  
#include <typeinfo>  
  
using namespace std;  
  
int main() {  
    char char1 = 'a';  
  
    auto promoted1 = char1 << 1;   // 194  
    cout << typeid(promoted1).name() << endl;  // int  
  
    auto promoted2 = char1 << 10;  // 99328  
    cout << typeid(promoted2).name() << endl;  // int  
}  
```  
  
## <a name="additional-details"></a>Ek Ayrıntılar  
 Bir kaydırma işleminin sonucu tanımsız ise *ADDITIVE ifade* negatif veya *ADDITIVE ifade* büyük veya eşit bit sayısına (yükseltilmiş)  *Shift ifade*. Hiçbir kaydırma işlemi yapılır *ADDITIVE ifade* 0'dır.  
  
```cpp  
#include <iostream>  
#include <bitset>  
using namespace std;  
  
int main() {  
    unsigned int int1 = 4;  
    bitset<32> b1{int1};  
    cout << b1 << endl;    // 00000000000000000000000000000100  
  
    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior  
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior  
  
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior  
  
    unsigned int int6 = int1 << 0;  
    bitset<32> b6{int6};  
    cout << b6 << endl;    // 00000000000000000000000000000100 (no change)}  
}  
```  
  
## <a name="footnotes"></a>Dipnotlar  
 1 aşağıdaki belirtiminde C ++ 11 ISO (INCITS/ISO/IEC 14882-2011[2012]), 5.8.2 ve 5.8.3 bölümlerine. kaydırma işleçleri açıklamasıdır.  
  
 Değeri **E1 << E2** olan **E1** sol gölgeye **E2** bit konumları; vacated BITS sıfırla doldurulur. Varsa **E1** imzasız bir türe sahip sonuç değeri **E1 × 2**<sup>**E2**</sup>, modül tane gösterilebilir içindeki en büyük değerden daha düşük Sonuç türü. Aksi halde, eğer **E1** imzalı türü ve negatif olmayan değer vardır ve **E1 × 2**<sup>**E2** </sup> karşılık gelen imzasız türünde gösterilebilir değil Sonuç türü, ardından sonuç türüne dönüştürülüp bu değer, sonuçta elde edilen değerdir; Aksi takdirde davranışı tanımlanmamıştır.  
  
 Değeri **E1 >> E2** olan **E1** sağ gölgeye **E2** bit konumları. Varsa **E1** imzasız türüne sahip veya **E1** işaretli bir türe ve negatif olmayan bir değer varsa, sayının oranı'nın ayrılmaz bir parçası sonuç değeri **E1/2** <sup> **E2**</sup>. Varsa **E1** işaretli bir türe ve negatif bir değere sahip, sonuçta elde edilen uygulama tanımlı değeridir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)