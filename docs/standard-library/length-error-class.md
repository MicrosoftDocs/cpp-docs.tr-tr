---
title: length_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::length_error
helpviewer_keywords:
- length_error class
ms.assetid: d53c46c5-4626-400d-bd76-bf3e1e0f64ae
ms.openlocfilehash: 67de20907dcf13fa54119d8886aabc8d521165cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223975"
---
# <a name="lengtherror-class"></a>length_error Sınıfı

Sınıfın belirtilmesi için çok uzun bir nesne oluşturma girişimi bildirmek için oluşturulan tüm özel durumlar için taban sınıf görevi görür.

## <a name="syntax"></a>Sözdizimi

```cpp
class length_error : public logic_error {
public:
    explicit length_error(const string& message);

    explicit length_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer [ne](../standard-library/exception-class.md) bir kopyasıdır **ileti**`.`[veri](../standard-library/basic-string-class.md#data).

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

**Başlık:** \<stdexcept >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[logic_error Sınıfı](../standard-library/logic-error-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
