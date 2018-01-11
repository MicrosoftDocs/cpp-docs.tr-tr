---
title: "mask_array sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: valarray/std::mask_array
dev_langs: C++
helpviewer_keywords: mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7aafc5a418fbbe4d12a759237657e1909541a7eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="maskarray-class"></a>mask_array Sınıfı
Üst valarrays kümeleridir destekler nesneleri alt diziler arasındaki işlemleri sağlayarak bir Boolean ifadesiyle belirtilen bir yardımcı, iç Şablon sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf bir nesneye başvuru depolayan bir nesne tanımlar **va** sınıfının [valarray](../standard-library/valarray-class.md)**\<türü >**, bir nesne ile birlikte **ba**  sınıfının [valarray\<bool >](../standard-library/valarray-bool-class.md), aralarından seçim yapabileceğiniz öğe dizisi açıklayan **valarray\<türü >** nesnesi.  
  
 Oluşturmak bir **mask_array\<türü >** biçiminde bir ifade yazarak yalnızca nesne [va &#91; ba &#93;](../standard-library/valarray-class.md#op_at). Karşılık gelen işlevi imzalar için tanımlanan gibi sınıfı mask_array üye işlevlerini sonra davranır **valarray\<türü >**, yalnızca seçilen öğelerin sırasını etkilenen dışında.  
  
 Dizi en çok oluşur **ba.size** öğeleri. Bir öğenin *J* yalnızca eklenmiştir **ba**[ *J*] doğrudur. Bu nedenle, öğe daha vardır true öğeleri olarak kadar sırada **ba**. Varsa `I` en düşük doğru öğe dizini **ba**, ardından **va**[ `I`] sıfır seçilen sırası öğedir.  
  
## <a name="example"></a>Örnek:  
  
```  
// mask_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Use masked subsets to assign a value of 10  
   // to all elements grrater than 3 in value  
   va [va > 3 ] = 10;  
   cout << "The modified operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).  
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<valarray >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

