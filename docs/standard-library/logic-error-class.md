---
description: 'Hakkında daha fazla bilgi edinin: logic_error sınıfı'
title: logic_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::logic_error
helpviewer_keywords:
- logic_error class
ms.assetid: b290d73d-94e1-4288-af86-2bb5d71f677a
ms.openlocfilehash: b4b592d268a29a1bf1c095beb79904789d695e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277719"
---
# <a name="logic_error-class"></a>logic_error Sınıfı

Sınıfı, program yürütmeden önce, mantıksal önkoşulların ihlalleri gibi, hataları bildirmek üzere oluşan tüm özel durumlar için temel sınıf görevi görür.

## <a name="syntax"></a>Syntax

```cpp
class logic_error : public exception {
public:
    explicit logic_error(const string& message);

    explicit logic_error(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what()` bir kopyasıdır `message.data()` . Daha fazla bilgi için bkz [`what`](../standard-library/exception-class.md) [`data`](../standard-library/basic-string-class.md#data) . ve.

## <a name="example"></a>Örnek

```cpp
// logic_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;

int main( )
{
   try
   {
      throw logic_error( "logic error" );
   }
   catch ( exception &e )
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
```

```Output
Caught: logic error
Type: class std::logic_error
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<stdexcept>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[özel durum sınıfı](../standard-library/exception-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
