---
title: '&lt;liste&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874451"
---
# <a name="ltlistgt-functions"></a>&lt;List&gt; işlevleri

## <a name="swap"></a>Kur

İki listenin öğelerini değiş tokuş eder.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Parametreler

*sol*\
`list` türünün bir nesnesi.

*sağ*\
`list` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi `left.swap(right)`yürütür.
