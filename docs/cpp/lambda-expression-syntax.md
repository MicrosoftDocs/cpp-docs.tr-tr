---
title: Lambda ifadesi söz dizimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++], syntax
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cae12ecefebe81bf73ffdbc32c0ce253e726dda2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405048"
---
# <a name="lambda-expression-syntax"></a>Lambda İfadesi Sözdizimi
Bu makalede, söz dizimi ve lambda ifadelerinin yapısal öğelerini gösterir. Lambda ifadeleri bir açıklaması için bkz: [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).  
  
## <a name="function-objects-vs-lambdas"></a>İşlev nesneleri vs. Lambda ifadeleri  
 Kod yazdığınızda, büyük olasılıkla işlev işaretçilerini ve işlev nesneleri problemleri çözmenize ve özellikle kullandığınızda hesaplamaları gerçekleştirmek için kullandığınız [standart C++ Kitaplığı algoritmaları](../cpp/algorithms-modern-cpp.md). İşlev işaretçileri ve işlev nesnelerinin avantajları ve dezavantajları vardır; örneğin, işlev işaretçilerinin söz dizimsel az yükü vardır ancak bir kapsam içindeki durumu korumaz ve işlev nesneleri durumunu koruyabilir ancak söz dizimsel getirdiği ek yüke gerek bir sınıf tanımı.  
  
 Bir lambda, işlev işaretçilerinin ve işlev nesnelerinin avantajlarını bir araya getirirken dezavantajlarını ortadan kaldırır. Bir işlev nesnesi gibi bir lambda esnektir ve durumu koruyabilir, ancak bir işlev nesnesinin aksine onun sıkıştırılmış söz dizimi bir açık sınıf tanımı gerektirmez. Lambdaları kullanarak, bir işlev nesnesine eşdeğer koda göre daha az hantal ve hataya daha az eğilimli kod yazabilirsiniz.  
  
 Aşağıdaki örnekler, lambda kullanımını işlevi nesnesi kullanımıyla karşılaştırır. İlk örnek konsola yazdırmak için bir lambda kullanır olup olmadığını her öğe bir `vector` çift veya tek nesne. İkinci örnek aynı görevi başarmak için bir işlev nesnesi kullanır.  
  
## <a name="example-1-using-a-lambda"></a>Örnek 1: Bir Lambda Kullanma  
 Bu örnek için bir lambda geçirir **for_each** işlevi. Lambda bildiren bir sonucu yazdırmaya olup olmadığını her öğe bir `vector` çift veya tek nesne.  
  
### <a name="code"></a>Kod  
  
```cpp  
// even_lambda.cpp  
// compile with: cl /EHsc /nologo /W4 /MTd  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
   // Create a vector object that contains 10 elements.  
   vector<int> v;  
   for (int i = 1; i < 10; ++i) {  
      v.push_back(i);  
   }  
  
   // Count the number of even numbers in the vector by   
   // using the for_each function and a lambda.  
   int evenCount = 0;  
   for_each(v.begin(), v.end(), [&evenCount] (int n) {  
      cout << n;  
      if (n % 2 == 0) {  
         cout << " is even " << endl;  
         ++evenCount;  
      } else {  
         cout << " is odd " << endl;  
      }  
   });  
  
   // Print the count of even numbers to the console.  
   cout << "There are " << evenCount   
        << " even numbers in the vector." << endl;  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```Output  
1 is odd  
2 is even  
3 is odd  
4 is even  
5 is odd  
6 is even  
7 is odd  
8 is even  
9 is odd  
There are 4 even numbers in the vector.  
```  
  
### <a name="comments"></a>Açıklamalar  
 Örnekte, üçüncü bağımsız değişkeni **for_each** işlevi bir lambdadır. `[&evenCount]` Kısmı belirtir ifadesinin yakalama yan tümcesi `(int n)` parametre listesi ve kalan bölümü ifadesinin gövdesi belirtir.  
  
## <a name="example-2-using-a-function-object"></a>Örnek 2: Bir İşlev Nesnesi Kullanma  
 Bazen bir lambda önceki örnekten daha fazla genişletmek için çok kullanışsız olur. Sonraki örnek ile birlikte bir işlev nesnesi bir lambda yerine kullanır **for_each** örnek 1'dekiyle aynı sonucu elde etmek. Örneklerin her ikisi de çift sayıların sayısını depolar bir `vector` nesne. İşlemin durumunu korumak üzere `FunctorClass` sınıfı depoları `m_evenCount` bir üye değişkeni başvurusuna göre. İşlemi gerçekleştirmek için `FunctorClass` işlev çağrısı işlecini uygular **operator()**. Visual C++ derleyicisi, Örnek 1'deki lambda koduyla boyut ve performans açısından karşılaştırılabilir kodu oluşturur. Bu makaledeki gibi temel bir sorun için, daha basit bir lambda tasarımı işlev nesnesi tasarımından genellikle daha iyi bir tasarımdır. Ancak ilerde işlevsellik için önemli bir genişletme gerekeceğini düşünüyorsanız, kodu korumayı kolaylaştıracak işlev nesnesi tasarımını kullanabilirsiniz.  
  
 Hakkında daha fazla bilgi için **operator()**, bkz: [işlevi çağrısı](../cpp/function-call-cpp.md). Hakkında daha fazla bilgi için **for_each** çalışması için bkz: [for_each](../standard-library/algorithm-functions.md#for_each).  
  
### <a name="code"></a>Kod  
  
```cpp  
// even_functor.cpp  
// compile with: /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class FunctorClass  
{  
public:  
    // The required constructor for this example.  
    explicit FunctorClass(int& evenCount)  
        : m_evenCount(evenCount) { }  
  
    // The function-call operator prints whether the number is  
    // even or odd. If the number is even, this method updates  
    // the counter.  
    void operator()(int n) const {  
        cout << n;  
  
        if (n % 2 == 0) {  
            cout << " is even " << endl;  
            ++m_evenCount;  
        } else {  
            cout << " is odd " << endl;  
        }  
    }  
  
private:  
    // Default assignment operator to silence warning C4512.  
    FunctorClass& operator=(const FunctorClass&);  
  
    int& m_evenCount; // the number of even variables in the vector.  
};  
  
int main()  
{  
    // Create a vector object that contains 10 elements.  
    vector<int> v;  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
  
    // Count the number of even numbers in the vector by   
    // using the for_each function and a function object.  
    int evenCount = 0;  
    for_each(v.begin(), v.end(), FunctorClass(evenCount));  
  
    // Print the count of even numbers to the console.  
    cout << "There are " << evenCount  
        << " even numbers in the vector." << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```Output  
1 is odd  
2 is even  
3 is odd  
4 is even  
5 is odd  
6 is even  
7 is odd  
8 is even  
9 is odd  
There are 4 even numbers in the vector.  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md)   
 [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md)   
 [Oluştur](../standard-library/algorithm-functions.md#generate)   
 [generate_n](../standard-library/algorithm-functions.md#generate_n)   
 [for_each](../standard-library/algorithm-functions.md#for_each)   
 [Özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md)   
 [Derleyici Uyarısı (düzey 1) C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)   
 [Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)