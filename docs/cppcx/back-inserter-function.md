---
description: 'Hakkında daha fazla bilgi edinin: back_inserter Işlevi'
title: back_inserter Işlevi
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: d2483c9947fbf3a7bc04024221ec6e582e416f84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223587"
---
# <a name="back_inserter-function"></a>back_inserter Işlevi

Belirtilen koleksiyonun sonundaki öğeleri eklemek için kullanılan bir yineleyici döndürür.

## <a name="syntax"></a>Sözdizimi

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü parametresi.

*Yönetim*<br/>
Temel koleksiyona erişim sağlayan bir arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yineleyici.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Ayrıca bkz.

[Windows:: Foundation:: Collections ad alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
