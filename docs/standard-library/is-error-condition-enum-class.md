---
title: is_error_condition_enum Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: c40f8f6eb93a33098cfbcf8133f08c56285abb43
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452600"
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum Sınıfı

[Error_condition](../standard-library/error-condition-class.md) numaralandırması için test edilen bir tür koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <_Enum>
    class is_error_condition_enum;
```

## <a name="remarks"></a>Açıklamalar

Türü türünde bir `error_condition`nesnede [](../standard-library/type-traits.md) depolamaya uygun bir numaralandırma değeri `_Enum` ise, bu tür koşulunun bir örneği true olarak tutulur.

Kullanıcı tanımlı türler için bu türe uzmanlık eklemek için izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
