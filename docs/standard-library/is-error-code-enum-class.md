---
title: is_error_code_enum Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: bc4ed7cd2e058414448c9366011b9efab97ee3d5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245183"
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum Sınıfı

İçin test eden bir tür koşulu temsil eden [error_code](../standard-library/error-code-class.md) sabit listesi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Açıklamalar

Bu örneği [tür koşulu](../standard-library/type-traits.md) ayrı tutma true ise tür `_Enum` bir sabit listesi değeri türünde bir nesne depolamak için uygundur `error_code`.

Kullanıcı tanımlı türler için bu tür uzmanlıklar eklemek için izin verilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
