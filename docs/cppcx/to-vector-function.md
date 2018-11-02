---
title: to_vector işlevi
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: a2054e6e787dcf9137a087dd53264c7f98461d69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508959"
---
# <a name="tovector-function"></a>to_vector işlevi

Döndürür bir `std::vector` değeri olan belirtilen Ivector veya IVectorView parametre temel koleksiyon ile aynı.

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon tür parametresi.

*v*<br/>
Temel alınan bir vektör veya VectorView nesneye erişim sağlayan bir Ivector veya IVectorView arabirimi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Windows::Foundation:: Collections

## <a name="see-also"></a>Ayrıca Bkz.

[Windows::Foundation:: Collections Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)