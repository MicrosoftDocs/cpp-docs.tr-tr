---
title: runtime_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::runtime_error
helpviewer_keywords:
- runtime_error class
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
ms.openlocfilehash: c4c4436c32f5f23c6bea119e95b165631384f583
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451114"
---
# <a name="runtimeerror-class"></a>runtime_error Sınıfı

Sınıfı, yalnızca program yürütüldüğünde oluşan hataları raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
class runtime_error : public exception {
public:
    explicit runtime_error(const string& message);

    explicit runtime_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

[Özel durum sınıfı](../standard-library/exception-class.md) tarafından döndürülen değer, **ileti**`.`[verilerinin](../standard-library/basic-string-class.md#data)bir kopyasıdır.

## <a name="example"></a>Örnek

```cpp
// runtime_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
// runtime_error
   try
   {
      locale loc( "test" );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught bad locale name
Type class std::runtime_error
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<stdexcept >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
