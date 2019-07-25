---
title: forward_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 687e39ce752bc0d4d289421887570dea6870f8f3
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457129"
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag Yapısı

Bir ileri Yineleyici temsil eden **iterator_category** işlevi için dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini ne olduğunu bulması gerekir. `Iterator` **:: İterator_category** türündeki her Yineleyici `iterator_traits`için, <  `Iterator` > yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Bu tür **Yineleyici** \< **iter**>  **:: iterator_category** ile aynıdır, çünkü **Iter** ileri Yineleyici olarak işlev görebilir bir nesne tanımlar.

## <a name="example"></a>Örnek

**İterator_tag**s 'yi nasıl kullanacağınızı gösteren bir örnek için bkz. [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[input_iterator_tag yapısı](../standard-library/input-iterator-tag-struct.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
