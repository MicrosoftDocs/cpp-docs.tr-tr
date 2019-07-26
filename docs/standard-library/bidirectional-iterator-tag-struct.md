---
title: bidirectional_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: bab2664fcb552a72baa032d719cf6b0141ffe525
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456633"
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag Yapısı

Çift yönlü yineleyiciyi temsil eden işlev için `iterator_category` dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini bulması gerekir. `Iterator`Türündeki her Yineleyici için, > `iterator_traits`:: **iterator_category** , <  `Iterator`yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Çift yönlü bir yineleyici olarak işlev görebilecek bir nesne `Iter` açıkladığı için tür **Yineleyici** \< **Iter**>:: **iterator_category** ile aynıdır.

## <a name="example"></a>Örnek

Nasıl [](../standard-library/random-access-iterator-tag-struct.md) kullanacağınızı `bidirectional_iterator_tag`gösteren bir örnek için bkz. random_access_iterator_tag.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[forward_iterator_tag yapısı](../standard-library/forward-iterator-tag-struct.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
