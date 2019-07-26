---
title: underflow_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::underflow_error
helpviewer_keywords:
- underflow_error class
ms.assetid: d632f1f9-9c6c-4954-b96b-03041bfab22d
ms.openlocfilehash: 41e3c8606cb8c6c90a84927f01eb953be138534a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454998"
---
# <a name="underflowerror-class"></a>underflow_error Sınıfı

Sınıfı, aritmetik bir alt sınırın raporlanmak üzere oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Sözdizimi

```cpp
class underflow_error : public runtime_error {
public:
    explicit underflow_error(const string& message);

    explicit underflow_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

**İleti**[](../standard-library/basic-string-class.md#data) [](../standard-library/exception-class.md) verilerininbirkopyasıolan`.`tarafından döndürülen değer.

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

**Üst bilgi:** \<stdexcept >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[runtime_error sınıfı](../standard-library/runtime-error-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
