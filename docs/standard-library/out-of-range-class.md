---
title: out_of_range Sınıfı
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::out_of_range
helpviewer_keywords:
- out_of_range class
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
ms.openlocfilehash: 3bbbc48aa2020782594606c6a53a34f7b937fc58
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87521284"
---
# <a name="out_of_range-class"></a>out_of_range Sınıfı

Sınıfı, geçerli aralığının dışında bir bağımsız değişkeni raporlamak için oluşturulan tüm özel durumlar için temel sınıf olarak hizmet verir.

## <a name="syntax"></a>Syntax

```cpp
class out_of_range : public logic_error {
public:
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `what()` bir kopyasıdır `message.data()` . Daha fazla bilgi için bkz [`what`](../standard-library/exception-class.md) [`data`](../standard-library/basic-string-class.md#data) . ve.

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

## <a name="output"></a>Çıktı

```cpp
Caught: invalid string position
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<stdexcept>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[logic_error sınıfı](../standard-library/logic-error-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
