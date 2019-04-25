---
title: back_inserter işlevi
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: 82df6b06389fa9f1c3ab83fa7b1da3bab092c68d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209448"
---
# <a name="backinserter-function"></a>back_inserter işlevi

Belirli bir koleksiyondaki sonunda öğe eklemek için kullanılan bir yineleyici döndürür.

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
Bir şablon türü parametresine.

*v*<br/>
Altta yatan seçki erişim sağlayan bir arabirim işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bir yineleyici.

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Windows::Foundation:: Collections

## <a name="see-also"></a>Ayrıca bkz.

[Windows::Foundation::Collections Ad Alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
