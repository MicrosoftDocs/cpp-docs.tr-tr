---
title: to_vector işlevi
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: 4fa4e9c620519cc6bb2f96d346ded88b6cc826ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404630"
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

## <a name="see-also"></a>Ayrıca bkz.

[Windows::Foundation::Collections Ad Alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
