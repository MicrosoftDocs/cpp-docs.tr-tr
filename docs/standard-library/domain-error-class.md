---
description: 'Hakkında daha fazla bilgi edinin: domain_error sınıfı'
title: domain_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::domain_error
helpviewer_keywords:
- domain_error class
ms.assetid: a1d8245d-61c2-4d1e-973f-073bd5dd5fa3
ms.openlocfilehash: 337df7c7c8e2327a4e5b88a45a736c697e6cb1bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324494"
---
# <a name="domain_error-class"></a>domain_error Sınıfı

Sınıfı, bir etki alanı hatasını raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Syntax

```cpp
class domain_error : public logic_error {
public:
    explicit domain_error(const string& message);

    explicit domain_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what()` bir kopyasıdır `message.data()` . Daha fazla bilgi için bkz [`what`](../standard-library/exception-class.md) [`data`](../standard-library/basic-string-class.md#data) . ve.

## <a name="example"></a>Örnek

```cpp
// domain_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      throw domain_error( "Your domain is in error!" );
   }
   catch (exception &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid(e).name( ) << endl;
   };
}
/* Output:
Caught: Your domain is in error!
Type: class std::domain_error
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<stdexcept>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[logic_error sınıfı](../standard-library/logic-error-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
