---
title: nothrow_t Yapısı
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: bd65b5006326850522a251cbcf7d655133a1aa8a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245573"
---
# <a name="nothrowt-structure"></a>nothrow_t Yapısı

Struct operatör işlevi parametre olarak yeni işlevi yerine bir ayırma hatası rapor için bir özel durum null bir işaretçi döndürmesi gerektiğini belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Açıklamalar

Struct Oluşturucu doğru sürümü seçmek için derleyici yardımcı olur. [nothrow](../standard-library/new-functions.md#nothrow) türünden nesnelerin eşanlamlıdır `std::nothrow_t`.

## <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) ve [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) örnekleri için `std::nothrow_t` işlevi parametre olarak kullanılır.
