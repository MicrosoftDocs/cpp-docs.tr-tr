---
description: 'Hakkında daha fazla bilgi edinin: to_vector Işlevi'
title: to_vector Işlevi
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: 77d6bee58a793946f91bc03ba4afed35aa7252cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307593"
---
# <a name="to_vector-function"></a>to_vector Işlevi

`std::vector`Belirtilen IVector veya ıvectorview parametresini temel alan koleksiyonla aynı değer olan değeri döndürür.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü parametresi.

*Yönetim*<br/>
Temel bir Vector veya VectorView nesnesine erişim sağlayan bir IVector veya ıvectorview arabirimi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Ayrıca bkz.

[Windows:: Foundation:: Collections ad alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
