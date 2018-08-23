---
title: Issame::Value sabiti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame::value
dev_langs:
- C++
helpviewer_keywords:
- value constant
ms.assetid: ee72deff-54a2-4482-9967-49a86d07f834
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 299ee0f1c2a892a3219c2337e01d629eadec8a82
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581000"
---
# <a name="issamevalue-constant"></a>IsSame::value Sabiti

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

## <a name="remarks"></a>Açıklamalar

Bir türden diğerine aynı olup olmadığını belirtir.

**değer** olduğu **true** şablon parametreleri aynı ise ve **false** şablon parametreleri farklıysa.

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[IsSame Yapısı](../windows/issame-structure.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)