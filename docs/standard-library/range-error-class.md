---
title: range_error sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 08/14/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stdexcept/std::range_error
dev_langs:
- C++
helpviewer_keywords:
- range_error class
ms.assetid: 8afb3e88-fc49-4213-b096-ed63d7aea37c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91769b0982bcc92c1f300766250b3ca13d231706
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313838"
---
# <a name="rangeerror-class"></a>range_error Sınıfı

Sınıfı, bir aralık hatayı bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.

## <a name="syntax"></a>Sözdizimi

```cpp
class range_error : public runtime_error {
public:
    explicit range_error(const string& message);
    explicit range_error(const char *message);
};
```

## <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer [ne](../standard-library/exception-class.md) bir kopyasıdır `message.data`. Daha fazla bilgi için [basic_string::data](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Örnek

```cpp
// range_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;
int main()
{
   try
   {
      throw range_error( "The range is in error!" );
   }
   catch (range_error &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The range is in error!
Type: class std::range_error
*/
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<stdexcept >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[runtime_error Sınıfı](../standard-library/runtime-error-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
