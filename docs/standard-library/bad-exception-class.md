---
title: bad_exception Class
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 94d1104b66fc6bd84e209caa23ce309cffd9fa85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457466"
---
# <a name="badexception-class"></a>bad_exception Class

Beklenmeyen bir işleyici oluşturulan bir özel durum sınıfı açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Açıklamalar

[Beklenmeyen](../standard-library/exception-functions.md#unexpected) oluşturmaz bir `bad_exception` sonlandırma yerine ya da belirtilen başka bir işlevi çağırmak yerine [set_unexpected](../standard-library/exception-functions.md#set_unexpected) varsa `bad_exception` bir işlevin throw listeye dahil.

Tarafından döndürülen değer `what` bir uygulama tanımlı C dizesi. Üye işlevlerinin hiçbiri, tüm özel durumlar.

Tarafından devralınan üyelerin listesi için `bad_exception` sınıfı [özel durum sınıfı](../standard-library/exception-class.md).

## <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek [beklenmeyen](../standard-library/exception-functions.md#unexpected) atma bir `bad_exception`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<özel durum >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[exception Sınıfı](../standard-library/exception-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
