---
title: output_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::output_iterator_tag
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
ms.openlocfilehash: cb2a59d2c81e6d7cc80de2714ba86476c5fa837f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659318"
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag Yapısı

Bir dönüş türü sağlayan sınıf `iterator_category` çıktı yineleyicisini temsil eden bir işlev.

## <a name="syntax"></a>Sözdizimi

output_iterator_tag yapısı {};

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilirsiniz, böylece en belirgin kategori yineleyici bağımsız değişkeninin bulmak şablon işlevi gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** yineleyicinin davranışını tanımlar en belirgin kategori etiketi olarak tanımlanması gerekir.

Aynı türdür **yineleyici** \< **Iter**> **:: iterator_category** olduğunda `Iter` olarak hizmet verebilen bir nesneyi tanımlayan bir Çıkış yineleyici.

Bu etiket üzerinde parametreli getirilemedi `value_type` veya `difference_type` yineleyici için diğer yineleyici etiketlere sahip olarak, çıkış yineleyicileri ya da sahip olmadığınızdan bir `value_type` veya `difference_type`.

## <a name="example"></a>Örnek

Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek `iterator_tag`s.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
