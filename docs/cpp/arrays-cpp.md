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
ms.openlocfilehash: ce914f47f62a742b24830d848fd9d82b91796f31
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408059"
---
# <a name="arrays-c"></a>Diziler (C++)
Koleksiyonu nesneleri gibi bir dizidir. Bir dizinin en basit durumu aşağıdaki sırayla bildirilebilecek bir vektör şöyledir:  
  
```  
decl-specifier identifier [ constant-expression ]  
decl-specifier identifier []  
decl-specifier identifer [][ constant-expression] . . .  
decl-specifier identifier [ constant-expression ]  
[ constant-expression ] . . .  
```  
  
 1. Bildirim belirticisi:  
  
-   İsteğe bağlı bir depolama sınıfı tanımlayıcısı.  
  
-   İsteğe bağlı **const** ve/veya **geçici** tanımlayıcıları.  
  
-   Dizideki öğelerin tür adı.  
  
 2. Bildirimci:  
  
-   Tanımlayıcı.  
  
-   Köşeli ayraç içinde Tamsayı türünde sabit bir ifade **[]**. Birden çok boyutta ek oluşur. parantez kullanılarak bildirilirse, Birinci ayraç kümesi sabit ifade atlanabilir.  
  
-   Sabit ifadeleri kapsayan isteğe bağlı ek parantezler.  
  
 3. İsteğe bağlı bir başlatıcı.  Bkz: [başlatıcılar](../cpp/initializers.md).  
  
 Dizideki öğelerin sayısını sabit ifade tarafından verilir. Dizideki ilk öğe 0 öğedir ve son öğe (*n*-1) öğe, burada *n* dizi içerebilir öğe sayısı. *Sabit-ifade* bir tamsayı türünde olmalı ve 0'dan büyük olmalıdır. Dizi içinde son alan olduğunda sıfır boyutlu bir dizi yasal bir **yapı** veya **birleşim** ve Microsoft Uzatmaları (/Ze) etkinleştirildiğinde.  
  
 Aşağıdaki örnek, çalışma zamanında bir dizi tanımlamak gösterilmektedir:  
  
```cpp 
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
  
 Diziler türetilmiş türlerdir, dolayısıyla İşlevler, başvurular dışında herhangi bir diğer türetilmiş veya temel türden oluşturulabilir ve **void**.  
  
 Diğer dizilerden oluşturulmuş diziler çok boyutlu dizilerdir. Bu çok boyutlu dizilerin dizisi birden fazla parantezli sabit ifadeler yerleştirerek belirtilir. Örneğin, bu bildirimi göz önünde bulundurun:  
  
```cpp 
int i2[5][7];  
```  
  
 Türünde bir dizi belirtir **int**, kavramsal olarak düzenlenmiş iki boyutlu bir matris beş satırdan ve yedi sütundan aşağıdaki şekilde gösterildiği gibi:  
  
 ![Bir çoklu kavramsal düzeni&#45;boyutlu bir dizi](../cpp/media/vc38rc1.gif "vc38RC1")  
Çok boyutlu dizinin kavramsal düzeni  
  
 Başlatıcı listesi olan dizilerin bildirimlerinde (açıklandığı [başlatıcılar](../cpp/initializers.md)), ilk boyut sınırlarını belirten sabit ifade atlanabilir. Örneğin:  
  
```cpp 
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
  
 Yukarıdaki bildirim üç satıra dört sütun bir dizi tanımlar. Satırlar üreticileri temsil eder ve sütunlar pazarlar için fabrikaları sevk temsil eder. Değerler, fabrikalardan marketlere nakliye maliyetlerini bağlıdır. Dizinin ilk boyutu kalır, ancak derleyici bunu başlatıcıyı inceleyerek doldurur.  
  
 Bu bölümdeki konular:  
  
-   [Dizileri Kullanma](../cpp/using-arrays-cpp.md)  
  
-   [İfadelerdeki Diziler](../cpp/arrays-in-expressions.md)  
  
-   [Alt Simge İşleci Yorumu](../cpp/interpretation-of-subscript-operator.md)  
  
-   [Dizi Türleri Yöneltmesi](../cpp/indirection-on-array-types.md)  
  
-   [C++ Dizilerini Sıralama](../cpp/ordering-of-cpp-arrays.md)  
  
## <a name="example"></a>Örnek  
 Çok boyutlu bir dizinin ilk boyutu için sınır belirtimini atlama tekniği de İşlev bildirimlerinde gibi kullanılabilir:  
  
```cpp 
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
 İşlev `FindMinToMkt` yeni Fabrika ekleme herhangi bir kod değişikliği, yalnızca yeniden derleme gerektirmeyen yazılmıştır. 