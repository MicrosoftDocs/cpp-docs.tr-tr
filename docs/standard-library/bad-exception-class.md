---
description: 'Hakkında daha fazla bilgi edinin: bad_exception sınıfı'
title: bad_exception Class
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 6b47facc751e1f16e033f26be284db1287e79ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321618"
---
# <a name="bad_exception-class"></a>bad_exception Class

Sınıfı, beklenmeyen bir işleyiciden oluşturulabilecek bir özel durumu açıklar.

## <a name="syntax"></a>Syntax

```cpp
class bad_exception : public exception {};

bad_exception();
bad_exception(const bad_exception&);
bad_exception& operator=(const bad_exception&);
const char* what() const override;
```

## <a name="remarks"></a>Açıklamalar

[beklenmeyen](../standard-library/exception-functions.md#unexpected) bir `bad_exception` işlevin throw listesine dahil ise, beklenmeyen bir şekilde veya [set_unexpected](../standard-library/exception-functions.md#set_unexpected) ile belirtilen başka bir işlevi çağırmak yerine, beklenmeyen bir şekilde oluşturulur `bad_exception` .

Tarafından döndürülen değer, `what` uygulama tanımlı bir C dizesidir. Üye işlevlerinin hiçbiri özel durum oluşturmaz.

Sınıfı tarafından devralınan üyelerin listesi için `bad_exception` bkz. [Exception sınıfı](../standard-library/exception-class.md).

## <a name="example"></a>Örnek

[Beklenmeyen](../standard-library/exception-functions.md#unexpected) bir oluşturma hakkında bir örnek için bkz. [set_unexpected](../standard-library/exception-functions.md#set_unexpected) `bad_exception` .
