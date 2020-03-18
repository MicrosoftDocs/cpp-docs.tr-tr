---
title: '&lt;forward_list&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 78b1eaa44ed464de67d8ec45fab3241179bb94b9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419100"
---
# <a name="ltforward_listgt-functions"></a>&lt;forward_list&gt; işlevleri

## <a name="swap"></a>Kur

İki ileri listenin öğelerini değiş tokuş eder.

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sol*\
`forward_list` türünün bir nesnesi.

*sağ*\
`forward_list` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `left.swap(right)`yürütür.
