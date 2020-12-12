---
description: 'Hakkında daha fazla bilgi edinin: is_error_condition_enum sınıfı'
title: is_error_condition_enum Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 3fd4f95e06ebee66a1f4d7d0e7de039d26b9f1fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323734"
---
# <a name="is_error_condition_enum-class"></a>is_error_condition_enum Sınıfı

[Error_condition](../standard-library/error-condition-class.md) numaralandırması için test edilen bir tür koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```cpp
template <_Enum>
    class is_error_condition_enum;
```

## <a name="remarks"></a>Açıklamalar

Türü türünde bir [](../standard-library/type-traits.md) `_Enum` nesnede depolamaya uygun bir numaralandırma değeri ise, bu tür koşulunun bir örneği true olarak tutulur `error_condition` .

Kullanıcı tanımlı türler için bu türe uzmanlık eklemek için izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
