---
title: output_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::output_iterator_tag
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
ms.openlocfilehash: 942e2214f42f97e262d4daf7836e8b6ced0e0ab2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453014"
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag Yapısı

Bir çıkış yineleyicisini temsil eden işlev için `iterator_category` dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

struct output_iterator_tag {};

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini bulması gerekir. `Iterator` **:: İterator_category** türündeki her Yineleyici `iterator_traits`için, <  `Iterator` > yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Tür, bir çıkış yineleyicisi olarak işlev görebilecek bir nesne açıkladığı `Iter` zaman **Yineleyici** \< **Iter**>  **:: iterator_category** ile aynıdır.

Bu etiket, diğer Yineleyici etiketlerinde olduğu `value_type` gibi `difference_type` , ya da Yineleyici için parametreli değildir, çünkü çıkış yineleyiciler bir `value_type` veya `difference_type`olarak değil.

## <a name="example"></a>Örnek

' [](../standard-library/iterator-traits-struct.md) Nin `iterator_tag`nasıl kullanılacağına ilişkin bir örnek için bkz. iterator_traits veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
