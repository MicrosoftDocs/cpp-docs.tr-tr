---
description: 'Hakkında daha fazla bilgi edinin: length_error sınıfı'
title: length_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::length_error
helpviewer_keywords:
- length_error class
ms.assetid: d53c46c5-4626-400d-bd76-bf3e1e0f64ae
ms.openlocfilehash: 051f79da569a153413a88af4976cb619e4b04e66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112056"
---
# <a name="length_error-class"></a>length_error Sınıfı

Sınıfı, belirtilene çok uzun bir nesne oluşturma girişimini raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Syntax

```cpp
class length_error : public logic_error {
public:
    explicit length_error(const string& message);

    explicit length_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what()` bir kopyasıdır `message.data()` . Daha fazla bilgi için bkz [`what`](../standard-library/exception-class.md) [`data`](../standard-library/basic-string-class.md#data) . ve.

## <a name="example"></a>Örnek

```cpp
// length_error.cpp
// compile with: /EHsc /GR /MDd
#include <vector>
#include <iostream>

using namespace std;

template<class  T>
class stingyallocator : public allocator< T>
{
public:
   template <class U>
      struct rebind { typedef stingyallocator<U> other; };
   _SIZT max_size( ) const
   {
         return 10;
   };

};

int main( )
{
   try
   {
      vector<int, stingyallocator< int > > myv;
      for ( int i = 0; i < 11; i++ ) myv.push_back( i );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught vector<T> too long
Type class std::length_error
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<stdexcept>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[logic_error sınıfı](../standard-library/logic-error-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
