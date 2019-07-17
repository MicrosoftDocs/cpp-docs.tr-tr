---
title: '&lt;Liste&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268062"
---
# <a name="ltlistgt-functions"></a>&lt;Liste&gt; işlevleri

## <a name="swap"></a> değiştirme

İki listenin öğelerini değiştirir.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Parametreler

*Sol*\
Bir nesne türü `list`.

*sağ*\
Bir nesne türü `list`.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yürütür `left.swap(right)`.
