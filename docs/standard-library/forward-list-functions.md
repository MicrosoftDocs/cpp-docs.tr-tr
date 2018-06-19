---
title: '&lt;forward_list&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 4585b1998309d7c17c8f02e2b0597cb595b2c4a3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844848"
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; işlevleri

||
|-|
|[Değiştirme](#swap)|

## <a name="swap"></a>  Değiştirme

İki iletme liste öğelerini değiş tokuş eder.

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`left`|Türünde bir nesne `forward_list`.|
|`right`|Türünde bir nesne `forward_list`.|

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yürütür `left.swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[<forward_list>](../standard-library/forward-list.md)<br/>
