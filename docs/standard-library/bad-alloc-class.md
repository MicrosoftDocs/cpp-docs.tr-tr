---
title: "bad_alloc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: new/std::bad_alloc
dev_langs: C++
helpviewer_keywords: bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3bb9257e83eb5c94361bb20ce689eff115817912
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="badalloc-class"></a>bad_alloc Sınıfı
Ayırma isteği başarılı olmadı belirtmek için bir özel durum sınıfı tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer **ne** bir uygulama tanımlı C dize. Üye işlevleri hiçbiri tüm özel durumlar oluşturma.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yeni >  
  
 **Namespace:** std  
  
## <a name="example"></a>Örnek  
  
```cpp  
// bad_alloc.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
using namespace std;  
  
int main() {  
   char* ptr;  
   try {  
      ptr = new char[(~unsigned int((int)0)/2) - 1];  
      delete[] ptr;  
   }  
   catch( bad_alloc &ba) {  
      cout << ba.what( ) << endl;  
   }  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
bad allocation  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yeni >  
  
## <a name="see-also"></a>Ayrıca Bkz.
 [özel durum sınıfı](../standard-library/exception-class.md)  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

