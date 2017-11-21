---
title: "out_of_range sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdexcept/std::out_of_range
dev_langs: C++
helpviewer_keywords: out_of_range class
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aec90b22bf3423ea93ae3ea5115dfd6b20a14c40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="outofrange-class"></a>out_of_range Sınıfı
Sınıfı, geçerli aralığın dışında bir bağımsız değişken bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class out_of_range : public logic_error {  
public:  
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer [ne](../standard-library/exception-class.md) bir kopyası **ileti**`.`[veri](../standard-library/basic-string-class.md#data).  
  
## <a name="example"></a>Örnek  
  
```cpp  
// out_of_range.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
using namespace std;  
  
int main() {  
// out_of_range  
   try {  
      string str( "Micro" );  
      string rstr( "soft" );  
      str.append( rstr, 5, 3 );  
      cout << str << endl;  
   }  
   catch ( exception &e ) {  
      cerr << "Caught: " << e.what( ) << endl;  
   };  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Caught: invalid string position  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<stdexcept >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [logic_error sınıfı](../standard-library/logic-error-class.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

