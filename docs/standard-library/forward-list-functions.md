---
description: 'Hakkında daha fazla bilgi edinin: &lt; forward_list &gt; işlevleri'
title: '&lt;forward_list &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 3f827b777f2e6fa62dd78c7d737d5da84b50610c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324379"
---
# <a name="ltforward_listgt-functions"></a>&lt;forward_list &gt; işlevleri

## <a name="swap"></a><a name="swap"></a> Kur

İki ileri listenin öğelerini değiş tokuş eder.

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`forward_list` türünün bir nesnesi.

*Right*\
`forward_list` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yürütülür `left.swap(right)` .
