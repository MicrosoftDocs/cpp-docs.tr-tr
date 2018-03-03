---
title: "Değer türleri (Modern C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d84888236b81fe862c6a22793e926ebf7df55c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="value-types-modern-c"></a>Değer Türleri (Modern C++)
C++ sınıfları, varsayılan değer türleri şunlardır. Bu konu, değer türleri ve bunların kullanılması ile ilgili sorunları tanıtıcı genel bakış sağlar.  
  
## <a name="value-vs-reference-types"></a>Değer başvuru türleri  
 Daha önce belirtildiği gibi C++ sınıfları tarafından varsayılan değer türleri şunlardır. Nesne odaklı programlama desteklemek çok biçimli davranışı etkinleştirmek başvuru türleri belirtilebilir. Başvuru türleri temel sınıflar ve sanal işlevleri hakkında çok biçimli amacıyla ise değer türleri bazen bellek ve düzen denetimi perspektifinden görüntülenir. Varsayılan olarak, her zaman bir kopya oluşturucu ve kopya atama işleci anlamına gelir, değer türleri copyable,. Referans türleri için sınıf copyable olmayan yaptığınız (kopya oluşturucu ve kopya atama işleci devre dışı bırak) ve bunların hedeflenen çok biçimlilik destekleyen bir sanal yıkıcı kullanın. Değer türleri ayrıca kopyalanırlar, bağlandığınızda, ayrı ayrı değiştirilebilir iki bağımsız değer her zaman size içeriği değildir. Başvuru türleri ne tür bir nesneyi olduğu kimlik hakkında - misiniz? Bu nedenle, "başvuru türleri" "çok biçimli türleri olarak" de denir.  
  
 Bir başvuru benzeri türü (temel sınıf, sanal işlevler) gerçekten istiyorsanız, açıkça kopyalama, devre dışı bırakmak de gösterildiği gibi ihtiyacınız `MyRefType` aşağıdaki kodda sınıfı.  
  
```cpp  
// cl /EHsc /nologo /W4  
  
class MyRefType {  
private:  
    MyRefType & operator=(const MyRefType &);  
    MyRefType(const MyRefType &);  
public:  
    MyRefType () {}  
};  
  
int main()  
{  
    MyRefType Data1, Data2;  
    // ...  
    Data1 = Data2;  
}  
```  
  
 Yukarıdaki kod derleme aşağıdaki hatayla sonuçlanır:  
  
```Output  
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'  
        meow.cpp(5) : see declaration of 'MyRefType::operator ='  
        meow.cpp(3) : see declaration of 'MyRefType'  
  
```  
  
## <a name="value-types-and-move-efficiency"></a>Değer türleri ve verimlilik taşıma  
 Kopya ayırma yükünü yeni kopya iyileştirmeler nedeniyle önlenmiş olur. Örneğin, bir dize dizeleri vektörü ortasında eklediğinizde, olacaktır kopyalama yeniden ayırma olmamasıdır, yalnızca bir move - bir vektör Büyüt içinde sonuçları olsa bile. Bu örneği için çok büyük iki nesne bir ekleme işlemi gerçekleştirilirken diğer işlemler için de geçerlidir. Bu değer işlemi iyileştirmelerinden nasıl etkinleştirebilirim? Çok kopya oluşturucuları otomatik olarak derleyici tarafından oluşturulabilir gibi bazı C++ Derleyicileri derleyici bu sizin için dolaylı olarak etkinleştirir. Ancak, Visual C++'da, sınıfınız "sınıf tanımında bildirerek atama ve oluşturucular taşımak için katılımı" gerekir. Çift ve işareti kullanılarak elde edilir (& &) uygun üye rvalue başvuru işlev bildirimleri ve tanımlama taşıma oluşturucusuna ve taşıma atama yöntemlerinde.  Ayrıca "kaynak nesne dışında guts çalmak için" doğru kodunu eklemeniz gerekir.  
  
 Nasıl etkin taşıma varsa karar? Etkin yapım kopyalama zaten biliyorsanız, büyük olasılıkla derin bir kopya ucuz olabiliyorsa, etkin taşımak istersiniz. Destek taşıma biliyorsanız, ancak, bu mutlaka etkin kopyalama istediğiniz anlamına gelmez. Bu ikinci durumda, bir "yalnızca taşıma türü" adlı. Standart Kitaplığı'nda zaten örneğidir `unique_ptr`. Eski bir yan not olarak `auto_ptr` kullanım dışıdır ve tarafından değiştirildi `unique_ptr` C++'ın önceki sürümünde taşıma semantiği destek eksikliği nedeniyle tam olarak.  
  
 Taşıma semantiği kullanarak, dönüş değeri veya Ekle-in-middle kullanabilirsiniz. Taşıma bir iyileştirme kopyasının. Yığın ayırma geçici bir çözüm olarak gerek yoktur. Aşağıdaki yarı kodu göz önünde bulundurun:  
  
```cpp  
#include <set>  
#include <vector>  
#include <string>  
using namespace std;  
  
//...  
set<widget> LoadHugeData() {  
    set<widget> ret;  
    // ... load data from disk and populate ret  
    return ret;  
}  
//...  
widgets = LoadHugeData();   // efficient, no deep copy  
  
vector<string> v = IfIHadAMillionStrings();  
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle  
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)  
//...  
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );  
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);  
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );  
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);  
//...  
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies  
```  
  
### <a name="enabling-move-for-appropriate-value-types"></a>Taşıma uygun değer türleri için etkinleştirme  
 Burada taşıma derin bir kopya ucuz olabilir bir değer benzeri sınıf için taşıma yapım etkinleştirmek ve verimlilik için atama taşıyın. Aşağıdaki yarı kodu göz önünde bulundurun:  
  
```cpp  
#include <memory>  
#include <stdexcept>  
using namespace std;  
// ...  
class my_class {  
    unique_ptr<BigHugeData> data;  
public:  
    my_class( my_class&& other )   // move construction  
        : data( move( other.data ) ) { }  
    my_class& operator=( my_class&& other )   // move assignment  
    { data = move( other.data ); return *this; }  
    // ...  
    void method() {   // check (if appropriate)  
        if( !data )   
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");  
    }  
};  
  
```  
  
 Kopya oluşturma/atama etkinleştirirseniz, derin bir kopya ucuz olabilir varsa taşıma yapım/atamasını sağlar.  
  
 Bazı *değer olmayan* türleri taşıma bir kaynak yalnızca Aktarım sahipliği zaman kopyalayamıyor gibi yalnızca,. Örnek: `unique_ptr`.  
  
## <a name="section"></a>Bölüm  
 İçerik  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ tür sistemi](../cpp/cpp-type-system-modern-cpp.md)   
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)