---
title: future_error sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::future_error
dev_langs:
- C++
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e5d5c24a658f53dbef4075d68f5aead5454356b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845017"
---
# <a name="futureerror-class"></a>future_error Sınıfı

Yönetme türleri yöntemleri ile oluşturulan bir özel durum nesnesi tanımlar [gelecekteki](../standard-library/future-class.md) nesneleri.

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

**Başlık:** \<gelecekteki >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[logic_error Sınıfı](../standard-library/logic-error-class.md)<br/>
[error_code Sınıfı](../standard-library/error-code-class.md)<br/>
