---
title: forward_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 04d526e7778dc219a8d9a49db40751b4418cc82d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434261"
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag Yapısı

Bir dönüş türü sağlayan sınıf **iterator_category** ileriye doğru yineleyiciyi temsil eden bir işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları algoritması seçimi için etiketler derleme gibi kullanılır. Şablon işlevi, derleme zamanında en verimli algoritması kullanabilmeniz ne yineleyici bağımsız değişkeninin en belirgin kategori mi olduğunu bulmanız gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** yineleyicinin davranışını tanımlar en belirgin kategori etiketi olarak tanımlanması gerekir.

Aynı türdür **yineleyici** \< **Iter**> **:: iterator_category** olduğunda **Iter** açıklayan bir ileriye doğru yineleyici hizmet verebilen bir nesne.

## <a name="example"></a>Örnek

Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek **iterator_tag**s.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[input_iterator_tag Yapısı](../standard-library/input-iterator-tag-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
