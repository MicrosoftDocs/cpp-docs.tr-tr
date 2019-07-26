---
title: is_error_code_enum Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 4080c62034b224a9553eca2787aa1c2f2cf69ab8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454613"
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum Sınıfı

[Error_code](../standard-library/error-code-class.md) numaralandırması için test edilen bir tür koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Açıklamalar

Türü türünde bir `error_code`nesnede [](../standard-library/type-traits.md) depolamaya uygun bir numaralandırma değeri `_Enum` ise, bu tür koşulunun bir örneği true olarak tutulur.

Kullanıcı tanımlı türler için bu türe uzmanlık eklemek için izin verilir.

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
