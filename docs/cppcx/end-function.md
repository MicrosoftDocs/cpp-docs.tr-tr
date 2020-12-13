---
description: 'Daha fazla bilgi edinin: End Işlevi'
title: End Işlevi
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: e29595e7eb403af85abdbfa18782adf1c33c308e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341977"
---
# <a name="end-function"></a>End Işlevi

Belirtilen arabirim parametresi tarafından erişilen bir koleksiyonun sonunun ötesinde işaret eden bir yineleyici döndürür.

## <a name="syntax"></a>Sözdizimi

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon türü parametresi.

*Yönetim*<br/>
Bir \<T> \<T> IVector veya \<T> ıvectorview arabirimi tarafından erişilen bir vektör veya vektörtorview nesneleri koleksiyonu \<T> .

*i*<br/>
Bir ıiterable arabirimi tarafından erişilen nesne Windows Çalışma Zamanı bir koleksiyon \<T> .

### <a name="return-value"></a>Dönüş Değeri

Koleksiyonun sonunun ötesinde işaret eden bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk iki şablon işlevi yineleyiciler döndürür ve üçüncü şablon işlevi bir giriş yineleyicisi döndürür.

Tarafından döndürülen [Platform:: Collections:: VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) nesnesi, `end` türündeki öğeleri depolayan bir proxy Yineleyici `VectorProxy<T>` . Ancak, proxy nesnesi neredeyse hiçbir şekilde Kullanıcı koduna görünmez. Daha fazla bilgi için bkz. [Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Windows:: Foundation:: Collections

## <a name="see-also"></a>Ayrıca bkz.

[Windows:: Foundation:: Collections ad alanı](../cppcx/windows-foundation-collections-namespace-c-cx.md)
