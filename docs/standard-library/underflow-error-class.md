---
title: underflow_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::underflow_error
helpviewer_keywords:
- underflow_error class
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
ms.openlocfilehash: 3f521e8ec083cd158212b3ae9cb9fcf26edc7e76
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520518"
---
# <a name="underflow_error-class"></a>underflow_error Sınıfı

Sınıfı, aritmetik bir alt sınırın raporlanmak üzere oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Syntax

```cpp
class underflow_error : public runtime_error {
public:
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what()` bir kopyasıdır `message.data()` . Daha fazla bilgi için bkz [`what`](../standard-library/exception-class.md) [`data`](../standard-library/basic-string-class.md#data) . ve.

## <a name="example"></a>Örnek

```cpp
// underflow_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      throw underflow_error( "The number's a bit small, captain!" );
   }
   catch ( exception &e ) {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The number's a bit small, captain!
Type: class std::underflow_error
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<stdexcept>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[runtime_error sınıfı](../standard-library/runtime-error-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
