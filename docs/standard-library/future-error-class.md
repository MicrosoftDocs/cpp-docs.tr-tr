---
title: future_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: 2b3f754c0ceb7384d99c6a657de214d30aca24b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430479"
---
# <a name="futureerror-class"></a>future_error Sınıfı

Türlerinin yönetme yöntemleri tarafından oluşturulan bir özel durum nesnesi açıklar [gelecekteki](../standard-library/future-class.md) nesneleri.

## <a name="syntax"></a>Sözdizimi

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<gelecek >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[logic_error Sınıfı](../standard-library/logic-error-class.md)<br/>
[error_code Sınıfı](../standard-library/error-code-class.md)<br/>
