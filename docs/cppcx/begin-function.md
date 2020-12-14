---
description: ': BEGIN Function hakkında daha fazla bilgi'
title: Begin Işlevi
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: ae59a4b4344da520d86c216f4c9979953e16753c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302770"
---
# <a name="begin-function"></a>Begin Işlevi

Belirtilen arabirim parametresi tarafından erişilen bir koleksiyonun başlangıcını gösteren bir yineleyici döndürür.

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
Şablon türü parametresi.

*Yönetim*<br/>
Bir \<T> \<T> IVector \<T> veya ıvectorview arabirimi tarafından erişilen vector veya vectorview nesnelerinin bir koleksiyonu \<T> .

*i*<br/>
Iiterable arabirimi tarafından erişilen rasgele Windows Çalışma Zamanı nesneleri koleksiyonu \<T> .

### <a name="return-value"></a>Dönüş Değeri

Koleksiyonun başlangıcına işaret eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk iki şablon işlevi yineleyiciler döndürür ve üçüncü şablon işlevi bir giriş yineleyicisi döndürür.

Begin tarafından döndürülen VectorIterator nesnesi, VectorProxy türünde öğeleri depolayan bir proxy Yineleyici \<T> . Ancak, proxy nesnesi neredeyse hiçbir şekilde Kullanıcı koduna görünmez. Daha fazla bilgi için bkz. [Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Ayrıca bkz.

[Windows:: Foundation:: Collections ad alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
