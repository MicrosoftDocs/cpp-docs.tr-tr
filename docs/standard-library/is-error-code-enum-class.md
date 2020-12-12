---
description: 'Hakkında daha fazla bilgi edinin: is_error_code_enum sınıfı'
title: is_error_code_enum Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 359f15c3d809435df81408a721a0c9ad11c1e7e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323761"
---
# <a name="is_error_code_enum-class"></a>is_error_code_enum Sınıfı

[Error_code](../standard-library/error-code-class.md) numaralandırması için test edilen bir tür koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Açıklamalar

Türü türünde bir [](../standard-library/type-traits.md) `_Enum` nesnede depolamaya uygun bir numaralandırma değeri ise, bu tür koşulunun bir örneği true olarak tutulur `error_code` .

Kullanıcı tanımlı türler için bu türe uzmanlık eklemek için izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
