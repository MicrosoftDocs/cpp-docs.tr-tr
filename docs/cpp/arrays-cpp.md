---
title: Diziler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fe8e5f53d05ac159fd577b260268f297b59d146
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="arrays-c"></a>Diziler (C++)
Bir dizi nesneleri gibi koleksiyonudur. Basit dizi aşağıdaki sırası tarafından bildirilen bir vektör durumdur:  
  
```  
  
      decl-specifier identifier [ constant-expression ]  
decl-specifier identifier []  
decl-specifier identifer [][ constant-expression] . . .  
decl-specifier identifier [ constant-expression ]  
[ constant-expression ] . . .  
```  
  
 1. Bildirim tanımlayıcısı:  
  
-   İsteğe bağlı bir depolama sınıfı tanımlayıcısı.  
  
-   İsteğe bağlı **const** ve/veya `volatile` tanımlayıcıları.  
  
-   Dizideki öğeler türünün adı.  
  
 2. Bildirimcisi:  
  
-   Tanımlayıcı.  
  
-   Köşeli parantez içine alınmış Tamsayı türünde sabit bir ifade **[].** Birden çok boyut ek parantez kullanılarak bildirilir, sabit ifadesine köşeli ilk kümesinde atlanabilir.  
  
-   İsteğe bağlı ek kapsayan sabit ifadeler ayırır.  
  
 3. İsteğe bağlı bir başlatıcı.  Bkz: [başlatıcıları](../cpp/initializers.md).  
  
 Dizideki öğelerin sayısı sabit ifadeyle verilir. Dizinin ilk öğe 0 öğesidir ve son öğe (*n*-1) öğe, burada *n* dizi içerebilir öğe sayısı. *Sabit ifadesi* bir tamsayı türünde olmalıdır ve 0'dan büyük olmalıdır. Dizi en son alanda olduğunda sıfır boyutlu bir array yasal bir `struct` veya **UNION** ve Microsoft Uzantıları (/Ze) etkin olduğunda.  
  
 Aşağıdaki örnek, bir dizi çalışma zamanında tanımlamak gösterilmektedir:  
  
```  
// arrays.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main() {  
   using namespace std;  
   int size = 3, i = 0;  
  
   int* myarr = new int[size];  
  
   for (i = 0 ; i < size ; i++)  
      myarr[i] = 10;  
  
   for (i = 0 ; i < size ; i++)  
      printf_s("myarr[%d] = %d\n", i, myarr[i]);  
  
   delete [] myarr;  
}  
```  
  
 Diziler türetilmiş türler ve İşlevler, başvuruları dışında herhangi bir diğer türetilmiş veya temel türü oluşturulabilir ve `void`.  
  
 Diğer diziler de oluşturulan çok boyutlu diziler dizidir. Bu çok boyutlu diziler köşeli parantez içindeki birden çok sabit ifadeler sırayla yerleştirerek belirtilir. Örneğin, bu bildirim göz önünde bulundurun:  
  
```  
int i2[5][7];  
```  
  
 Türünde bir dizi belirtir `int`, kavramsal olarak düzenlenmiş iki boyutlu bir Matristeki beş satır ve yedi sütun, aşağıdaki çizimde gösterildiği gibi:  
  
 ![Bir çoklu kavramsal yerleşimini&#45;boyutlu bir dizi](../cpp/media/vc38rc1.gif "vc38RC1")  
Çok boyutlu dizinin kavramsal düzeni  
  
 Bir başlatıcı listeniz multidimensioned dizi bildirimlerden (açıklandığı gibi [başlatıcıları](../cpp/initializers.md)), ilk boyut sınırlarını belirtir sabit ifadesine atlanabilir. Örneğin:  
  
```  
// arrays2.cpp  
// compile with: /c  
const int cMarkets = 4;  
// Declare a float that represents the transportation costs.  
double TransportCosts[][cMarkets] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }  
};  
```  
  
 Önceki bildirimi dört sütun tarafından üç satır bir dizi tanımlar. Satırları oluşturucuları temsil eder ve sütunlar için oluşturucuları sevk pazarda temsil eder. Taşıma maliyetleri oluşturucuları pazarda değerlerdir. Dizinin ilk boyutu sol ancak derleyici, başlatıcı inceleyerek doldurur.  
  
 Bu bölümdeki konular:  
  
-   [Dizileri Kullanma](../cpp/using-arrays-cpp.md)  
  
-   [İfadelerdeki Diziler](../cpp/arrays-in-expressions.md)  
  
-   [Alt Simge İşleci Yorumu](../cpp/interpretation-of-subscript-operator.md)  
  
-   [Dizi Türleri Yöneltmesi](../cpp/indirection-on-array-types.md)  
  
-   [C++ Dizilerini Sıralama](../cpp/ordering-of-cpp-arrays.md)  
  
## <a name="example"></a>Örnek  
 Çok boyutlu bir diziye ilk boyutu için sınır belirtimi atlama tekniği de işlev bildirimleri gibi kullanılabilir:  
  
```  
// multidimensional_arrays.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <limits>   // Includes DBL_MAX  
#include <iostream>  
  
const int cMkts = 4, cFacts = 2;  
  
// Declare a float that represents the transportation costs  
double TransportCosts[][cMkts] = {   
   { 32.19, 47.29, 31.99, 19.11 },  
   { 11.29, 22.49, 33.47, 17.29 },  
   { 41.97, 22.09,  9.76, 22.55 }    
};  
  
// Calculate size of unspecified dimension  
const int cFactories = sizeof TransportCosts /  
                  sizeof( double[cMkts] );  
  
double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);  
  
using namespace std;  
  
int main( int argc, char *argv[] ) {  
   double MinCost;  
  
   if (argv[1] == 0) {  
      cout << "You must specify the number of markets." << endl;  
      exit(0);  
   }  
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);  
   cout << "The minimum cost to Market " << argv[1] << " is: "  
       << MinCost << "\n";  
}  
  
double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {  
   double MinCost = DBL_MAX;  
  
   for( int i = 0; i < cFacts; ++i )  
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?  
         MinCost : TransportCosts[i][Mkt];  
  
   return MinCost;  
}  
```  
  
```Output  
The minimum cost to Market 3 is: 17.29  
```  
  
## <a name="comments"></a>Açıklamalar  
 İşlev `FindMinToMkt` yeni oluşturucuları ekleme kod değişikliklerini, yalnızca yeniden derlenmek gerektirmez şekilde yazılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 