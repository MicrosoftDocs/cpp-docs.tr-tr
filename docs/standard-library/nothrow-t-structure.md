---
description: 'Daha fazla bilgi edinin: nothrow_t yapısı'
title: nothrow_t Yapısı
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: 974fbe3a1e27da41c6366c62d748426293a54437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338103"
---
# <a name="nothrow_t-structure"></a>nothrow_t Yapısı

Struct, işlevin bir özel durum oluşturmak yerine bir ayırma hatası bildirmek için bir null işaretçi döndürmesi gerektiğini göstermek için New işlecine bir Function parametresi olarak kullanılır.

## <a name="syntax"></a>Syntax

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Açıklamalar

Yapı birimi derleyicinin doğru oluşturucunun sürümünü seçmesini sağlar. [nothrow](../standard-library/new-functions.md#nothrow) , türündeki nesnelerin eşanlamlısıdır `std::nothrow_t` .

## <a name="example"></a>Örnek

İşlev parametresi olarak nasıl kullanıldığına dair örnekler için bkz. [New işleci](../standard-library/new-operators.md#op_new) ve [New New&#91;&#93;](../standard-library/new-operators.md#op_new_arr) `std::nothrow_t` .
