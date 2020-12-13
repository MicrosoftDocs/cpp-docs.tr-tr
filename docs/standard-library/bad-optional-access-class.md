---
description: 'Hakkında daha fazla bilgi edinin: bad_optional_access sınıfı'
title: bad_optional_access sınıfı
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: e3439c53766a1890592bde8ed449f5ff2779f347
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132762"
---
# <a name="bad_optional_access-class"></a>bad_optional_access sınıfı

Değer içermeyen bir nesnenin değerine erişmek için bir girişimde bulunuldu durumu raporlamak için özel durum olarak oluşturulan nesne türlerini tanımlar `optional` .

## <a name="syntax"></a>Syntax

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>Ayrıca bkz.

[\<optional>](optional.md)\
[isteğe bağlı sınıf](optional-class.md)
