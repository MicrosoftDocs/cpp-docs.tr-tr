---
description: 'Hakkında daha fazla bilgi edinin: future_error sınıfı'
title: future_error Sınıfı
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: c7dc99ea842cd13658c13a5c2492bda3d853302f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324219"
---
# <a name="future_error-class"></a>future_error Sınıfı

[Gelecekteki](../standard-library/future-class.md) nesneleri yöneten türlerin yöntemleriyle oluşturulabilecek bir özel durum nesnesi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<future>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[logic_error sınıfı](../standard-library/logic-error-class.md)\
[error_code sınıfı](../standard-library/error-code-class.md)
