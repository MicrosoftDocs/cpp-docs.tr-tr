---
title: Lambda ifadesi sözdizimi | Microsoft Docs
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
ms.openlocfilehash: 1faf0458a9cf1a528e9a0c2582e8d2ec3715f149
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32421048"
---
# <a name="lambda-expression-syntax"></a>Lambda İfadesi Sözdizimi
Bu makalede, sözdizimi ve lambda ifadeleri yapısal öğeleri gösterilmektedir. Lambda ifadeleri açıklaması için bkz: [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).  
  
## <a name="function-objects-vs-lambdas"></a>İşlev nesneleri vs. Lambda ifadeleri  
 Kodu yazarken, büyük olasılıkla işlev işaretçileri ve işlev nesneleri sorunlarını çözmek ve özellikle kullandığınızda, hesaplamalar için kullandığınız [C++ Standart Kitaplığı algoritmaları](../cpp/algorithms-modern-cpp.md). İşlev işaretçileri ve işlev nesneleri sahip olumlu ve olumsuz yönleri — Örneğin, işlev işaretçileri en az söz dizimi ek yükleri vardır ancak bir kapsam içinde durum içermez ve işlev nesneleri durumunu korumak ancak söz dizimi yükü gerektirir bir sınıf tanımı.  
  
 Bir lambda, işlev işaretçilerinin ve işlev nesnelerinin avantajlarını bir araya getirirken dezavantajlarını ortadan kaldırır. İşlev nesneleri gibi bir lambda esnektir ve durumunu korumak, ancak işlev nesnesi, bir açık sınıf tanımını kısaltılmış sözdizimi gerektirmez. Lambdaları kullanarak, bir işlev nesnesine eşdeğer koda göre daha az hantal ve hataya daha az eğilimli kod yazabilirsiniz.  
  
 Aşağıdaki örnekler, lambda kullanımını işlevi nesnesi kullanımıyla karşılaştırır. İlk örnek bir lambda konsola yazdırma kullanmasını olup olmadığını her bir öğe bir `vector` nesnesidir bile ya da tek. İkinci örnek aynı görevi başarmak için bir işlev nesnesi kullanır.  
  
## <a name="example-1-using-a-lambda"></a>Örnek 1: Bir Lambda Kullanma  
 Bu örnek bir lambda geçirir `for_each` işlevi. Lambda bildiren bir sonuç yazdırır olup olmadığını her bir öğesinde bir `vector` nesnesidir bile ya da tek.  
  
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
 Örnekte, üçüncü bağımsız değişkeni `for_each` bir lambda işlevdir. `[&evenCount]` Bölümü yakalama yan tümcesi ifadesinin belirtir `(int n)` parametre listesi ve bölümü kalan ifadesinin gövdesi belirtir.  
  
## <a name="example-2-using-a-function-object"></a>Örnek 2: Bir İşlev Nesnesi Kullanma  
 Bazen bir lambda önceki örnekten daha fazla genişletmek için çok kullanışsız olur. Sonraki örnek ile birlikte bir işlev nesnesi bir lambda yerine kullanan `for_each` örnek 1 aynı sonuçları üretmek için işlevi. Örneklerin her ikisi de bile numaraları sayısı depolamak bir `vector` nesnesi. İşlemin durumunu korumak için `FunctorClass` sınıf depoları `m_evenCount` değişken olarak bir üye değişkenine başvuruya. İşlemi gerçekleştirmek için `FunctorClass` işlev çağırma işleci uygulayan `operator()`. Visual C++ derleyicisi, Örnek 1'deki lambda koduyla boyut ve performans açısından karşılaştırılabilir kodu oluşturur. Bu makaledeki gibi temel bir sorun için, daha basit bir lambda tasarımı işlev nesnesi tasarımından genellikle daha iyi bir tasarımdır. Ancak ilerde işlevsellik için önemli bir genişletme gerekeceğini düşünüyorsanız, kodu korumayı kolaylaştıracak işlev nesnesi tasarımını kullanabilirsiniz.  
  
 Hakkında daha fazla bilgi için `operator()`, bkz: [işlevini çağırın](../cpp/function-call-cpp.md). Hakkında daha fazla bilgi için `for_each` işlev, bkz: [for_each](../standard-library/algorithm-functions.md#for_each).  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md)   
 [Lambda ifadeleri örnekleri](../cpp/examples-of-lambda-expressions.md)   
 [Oluştur](../standard-library/algorithm-functions.md#generate)   
 [generate_n](../standard-library/algorithm-functions.md#generate_n)   
 [for_each](../standard-library/algorithm-functions.md#for_each)   
 [Özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md)   
 [Derleyici Uyarısı (düzey 1) C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)   
 [Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)