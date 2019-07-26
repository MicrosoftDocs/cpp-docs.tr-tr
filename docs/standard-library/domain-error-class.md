---
title: domain_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::domain_error
helpviewer_keywords:
- domain_error class
ms.assetid: a1d8245d-61c2-4d1e-973f-073bd5dd5fa3
ms.openlocfilehash: 6eabb4ca8ed1c7b5259a8479e1a3e067de073b8e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454313"
---
# <a name="domainerror-class"></a>domain_error Sınıfı

Sınıfı, bir etki alanı hatasını raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Sözdizimi

```cpp
class domain_error : public logic_error {
public:
    explicit domain_error(const string& message);

    explicit domain_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

**İleti**[](../standard-library/basic-string-class.md#data) [](../standard-library/exception-class.md) verilerininbirkopyasıolan`.`tarafından döndürülen değer.

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

**Üst bilgi:** \<stdexcept >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[logic_error sınıfı](../standard-library/logic-error-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
