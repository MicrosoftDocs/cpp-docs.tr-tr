---
title: input_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 47e0d08f79cfa41c414ac4fcd570ce8fdfbd0b35
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455323"
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag Yapısı

Bir giriş yineleyicisini temsil eden işlev için `iterator_category` dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

struct input_iterator_tag {};

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini bulması gerekir. `Iterator` **:: İterator_category** türündeki her Yineleyici `iterator_traits`için, <  `Iterator` > yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Tür, bir giriş yineleyicisi olarak işlev görebilecek bir nesne açıkladığı `Iter` zaman **Yineleyici** \< **Iter**>  **:: iterator_category** ile aynıdır.

## <a name="example"></a>Örnek

' [](../standard-library/iterator-traits-struct.md) Nin `iterator_tag`nasıl kullanılacağına ilişkin bir örnek için bkz. iterator_traits veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
