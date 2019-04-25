---
title: is_error_condition_enum Sınıfı
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 1b5b55431db806bb109a58199ad9d2d7c16f38ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162440"
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum Sınıfı

İçin test eden bir tür koşulu temsil eden [error_condition](../standard-library/error-condition-class.md) sabit listesi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <_Enum>
class is_error_condition_enum;
```

## <a name="remarks"></a>Açıklamalar

Bu örneği [tür koşulu](../standard-library/type-traits.md) ayrı tutma true ise tür `_Enum` bir sabit listesi değeri türünde bir nesne depolamak için uygundur `error_condition`.

Kullanıcı tanımlı türler için bu tür uzmanlıklar eklemek için izin verilebilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<system_error >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
