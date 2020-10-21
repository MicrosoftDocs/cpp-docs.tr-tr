---
title: '&lt;forward_list &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 78b1eaa44ed464de67d8ec45fab3241179bb94b9
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274577"
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
