---
title: "overflow_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdexcept/std::overflow_error
dev_langs: C++
helpviewer_keywords: overflow_error class
ms.assetid: bae7128d-e36b-4a45-84f1-2f89da441d20
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eff6eb00c6658983cb734b7db53e909a17b9bfd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overflowerror-class"></a>overflow_error Sınıfı
Sınıfı, aritmetik taşma bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class overflow_error : public runtime_error {  
public:  
    explicit overflow_error(const string& message);

    explicit overflow_error(const char *message);

};  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer [ne](../standard-library/exception-class.md) bir kopyası **ileti**`.`[veri](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Örnek  
  
```cpp  
// overflow_error.cpp  
// compile with: /EHsc /GR  
#include <bitset>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   try   
   {  
      bitset< 33 > bitset;  
      bitset[32] = 1;  
      bitset[0] = 1;  
      unsigned long x = bitset.to_ulong( );  
   }  
   catch ( exception &e )   
   {  
      cerr << "Caught " << e.what( ) << endl;  
      cerr << "Type " << typeid( e ).name( ) << endl;  
   };  
}  
\* Output:   
Caught bitset<N> overflow  
Type class std::overflow_error  
*\  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<stdexcept >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [runtime_error sınıfı](../standard-library/runtime-error-class.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

