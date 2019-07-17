---
title: bad_exception Class
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 1795a44d2d31cfbad964b41ef03e4bf65b401352
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246202"
---
# <a name="badexception-class"></a>bad_exception Class

Beklenmeyen bir işleyici oluşturulan bir özel durum sınıfı açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_exception : public exception {};

bad_exception();
bad_exception(const bad_exception&);
bad_exception& operator=(const bad_exception&);
const char* what() const override;
```

## <a name="remarks"></a>Açıklamalar

[Beklenmeyen](../standard-library/exception-functions.md#unexpected) oluşturmaz bir `bad_exception` sonlandırma yerine ya da belirtilen başka bir işlevi çağırmak yerine [set_unexpected](../standard-library/exception-functions.md#set_unexpected) varsa `bad_exception` bir işlevin throw listeye dahil.

Tarafından döndürülen değer `what` bir uygulama tanımlı C dizesi. Üye işlevlerinin hiçbiri, tüm özel durumlar.

Tarafından devralınan üyelerin listesi için `bad_exception` sınıfı [özel durum sınıfı](../standard-library/exception-class.md).

## <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek [beklenmeyen](../standard-library/exception-functions.md#unexpected) atma bir `bad_exception`.
