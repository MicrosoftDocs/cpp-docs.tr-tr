---
title: "Alt simge işleci: | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '[]'
dev_langs: C++
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e1b40b16c3ee349419259ae1e2240e28e3e7e911
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="subscript-operator"></a>Alt simge işleci:
## <a name="syntax"></a>Sözdizimi  
  
```  
  
postfix-expression [ expression ]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Alt simge işleci tarafından izlenen (aynı zamanda birincil bir ifade olabilir) bir sonek ifadesi **[]**, dizi dizinini belirtir.  
  
 Yönetilen diziler hakkında daha fazla bilgi için bkz: [diziler](../windows/arrays-cpp-component-extensions.md).  
  
 Genellikle, tarafından temsil edilen değer *sonek ifade* bir dizi tanımlayıcı gibi bir işaretçi değeri ve *ifade* (numaralandırılmış türler dahil) bir tamsayı değeri. Ancak, tüm sözdizimsel olarak olduğundan bu ifadelerden biri işaretçi türü ve diğer tamsayı türünde olması gereklidir. Bu nedenle tam sayı değeri olabilir. *sonek ifade* konumu ve işaretçi değeri parantez içinde olabilir *ifade* veya alt simge konumu. Aşağıdaki kod parçası göz önünde bulundurun:  
  
```  
int nArray[5] = { 0, 1, 2, 3, 4 };  
cout << nArray[2] << endl;            // prints "2"  
cout << 2[nArray] << endl;            // prints "2"  
```  
  
 Önceki örnekte, ifade `nArray[2]` aynıdır `2[nArray]`. Bunun nedeni, bir alt simge ifadesi sonucudur *e1***[** *e2* **]** tarafından verilir:  
  
 **\*((** *e2* **)**  *+*  **(***e1***))**  
  
 İfadeyle verdiğini adresi değil *e2* adresinden bayt *e1*. Bunun yerine, adres dizisindeki sonraki nesnesini verecek şekilde ölçeklendirilir *e2*. Örneğin:  
  
```  
double aDbl[2];  
```  
  
 Adreslerini `aDb[0]` ve `aDb[1]` 8 bayt parçası olan — türünde bir nesne boyutunu **çift**. Bu nesne türüne göre ölçeklendirme C++ dili tarafından otomatik olarak yapılır ve içinde tanımlanan [ADDITIVE işleçleri](../cpp/additive-operators-plus-and.md) burada toplama ve çıkarma işaretçi türü işlenenleri olarak ele alınmıştır.  
  
 Bir alt simge ifadesinde de aşağıdaki gibi birden fazla alt simge olabilir:  
  
 *İfade1* **[***İfade2***] [***deyim3***]**...  
  
 Alt simge ifadeleri soldan sağa ilişkilendirilir. Soldaki alt simge ifadesi *İfade1***[***İfade2***]**, ilk olarak değerlendirilir. Eklemelerini sonuçları adresi *İfade1* ve *İfade2* bir işaretçi ifadesi; formları sonra *deyim3* yeni bir form için bu işaretçi ifadesi eklenir son alt simge ifadesi bir vb. eklenene kadar işaretçi ifade. İndirection işleci (**\***) son alt ifade değerlendirildikten sonra bir dizi türü son işaretçi değeri adresleri sürece uygulanır.  
  
 Birden çok alt simgeler ifadelerle çok boyutlu diziler öğelerine bakın. Çok boyutlu bir dizi, öğeleri dizi olan bir dizidir. Örneğin, üç boyutlu bir dizinin ilk öğesi iki boyutlu bir dizidir. Aşağıdaki örnek bildirir ve basit iki boyutlu bir dizi karakter başlatır:  
  
```  
// expre_Subscript_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
#define MAX_ROWS 2  
#define MAX_COLS 2  
  
int main() {  
   char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };  
   for ( int i = 0; i < MAX_ROWS; i++ )  
      for ( int j = 0; j < MAX_COLS; j++ )  
         cout << c[ i ][ j ] << endl;  
}  
```  
  
## <a name="positive-and-negative-subscripts"></a>Pozitif ve negatif alt simgeler  
 Bir dizinin ilk öğesi 0 öğesidir. C++ dizi aralık *dizi*[0] için *dizi*[*boyutu* - 1]. Ancak, C++ pozitif ve negatif alt simgeler destekler. Negatif alt simgeler dizi sınırları içinde olmalıdır; yapmazsanız, sonuçları öngörülemeyen sonuçlara yol açabilir. Aşağıdaki kod dizi pozitif ve negatif alt simgeler gösterir:  
  
```  
#include <iostream>  
using namespace std;  
  
int main() {  
    int intArray[1024];  
    for (int i = 0, j = 0; i < 1024; i++)  
    {  
        intArray[i] = j++;  
    }  
  
    cout << intArray[512] << endl;// 512  
  
    int *midArray = &intArray[512];  // pointer to the middle of the array  
  
    cout << midArray[-256] << endl;   // 256  
  
    cout << intArray[-256] << endl; // unpredictable  
}  
```  
  
 Dizi kökeni daha bellekte bir adresi 256 baytı alt işaret ettiğinden negatif alt simge lasta satırında bir çalışma zamanı hatası üretebilir. İşaretçinin `midArray` ortasını için başlatılan `intArray`; bu nedenle hem pozitif ve negatif dizi dizinlerini üzerinde kullanılması mümkün değildir. Dizi alt simge hataları derleme zamanı hataları oluşturmaz, ancak bunlar öngörülemeyen sonuçlar.  
  
 Alt simge işleci yer değiştirebilme ' dir. Bu nedenle, ifadeleri *dizi*[*dizin*] ve *dizi*[*dizi*] alt simge sürece eşdeğer olması garanti İşleç aşırı (bkz [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md)). İlk form en yaygın kodlama, ya da çalışır ancak uygulamadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sonek ifadeleri](../cpp/postfix-expressions.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Diziler](../cpp/arrays-cpp.md)   
 [Tek boyutlu diziler](../c-language/one-dimensional-arrays.md)   
 [Çok boyutlu diziler](../c-language/multidimensional-arrays-c.md)