---
description: 'Daha fazla bilgi için: &lt; List &gt; Functions'
title: '&lt;liste &gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 6a94fcc916db08a510a968b66b0a0dc0cfa9b8e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284713"
---
# <a name="ltlistgt-functions"></a>&lt;liste &gt; işlevleri

## <a name="swap"></a><a name="swap"></a> Kur

İki listenin öğelerini değiş tokuş eder.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Parametreler

*tarafta*\
`list` türünün bir nesnesi.

*Right*\
`list` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlevi yürütülür `left.swap(right)` .
