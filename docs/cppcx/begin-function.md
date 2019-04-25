---
title: begin işlevi
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: 1b95e4d32321aadf7de65ecb25109fbecd9eb614
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258297"
---
# <a name="begin-function"></a>begin işlevi

Belirtilen arabirim parametresi tarafından erişilebilen bir koleksiyon başına gösteren bir yineleyici döndürür.

## <a name="syntax"></a>Sözdizimi

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Bir şablon türü parametresine.

*v*<br/>
Vektör koleksiyonunu\<T > ya da VectorView\<T > bir Ivector tarafından erişilen nesneler\<T > ya da IVectorView\<T > arabirimini.

*i*<br/>
Bir Iıterable tarafından erişilen rastgele Windows çalışma zamanı nesnelerinin bir koleksiyonunu\<T > arabirimini.

### <a name="return-value"></a>Dönüş Değeri

Koleksiyon başına gösteren bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk iki şablon işlevi Yineleyicilerin dönün ve üçüncü şablon işlevi bir giriş yineleyici döndürür.

Tarafından döndürülen nesne başlamak VectorIterator VectorProxy türünde öğeler depolayan bir ara sunucu yineleyici olduğunu\<T >. Ancak, proxy neredeyse hiç kullanıcı kodu tarafından nesnedir. Daha fazla bilgi için [koleksiyonları (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Windows::Foundation:: Collections

## <a name="see-also"></a>Ayrıca bkz.

[Windows::Foundation::Collections Ad Alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
