---
title: bidirectional_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: c8296ddf30c0e2a3d34e69cbf079c0477e0e8b7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661519"
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag Yapısı

Bir dönüş türü sağlayan sınıf `iterator_category` çift yönlü yineleyiciyi temsil eden bir işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilirsiniz, böylece şablon işlevi, yineleyici bağımsız en belirgin kategorisini bulması gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator`>:: **iterator_category** yineleyicinin davranışını tanımlar en belirgin kategori etiketi olarak tanımlanması gerekir.

Aynı türdür **yineleyici** \< **Iter**>:: **iterator_category** olduğunda `Iter` bir çift yönlü hizmet verebilen bir nesneyi tanımlar Yineleyici.

## <a name="example"></a>Örnek

Bkz: [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek `bidirectional_iterator_tag`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[forward_iterator_tag Yapısı](../standard-library/forward-iterator-tag-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
