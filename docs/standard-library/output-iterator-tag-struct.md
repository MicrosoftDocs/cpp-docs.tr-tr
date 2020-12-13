---
description: 'Hakkında daha fazla bilgi edinin: output_iterator_tag struct'
title: output_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::output_iterator_tag
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
ms.openlocfilehash: 1bd97f88dc7ae68976920cf006cd10115b16b2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340911"
---
# <a name="output_iterator_tag-struct"></a>output_iterator_tag Yapısı

Bir `iterator_category` Çıkış yineleyicisini temsil eden işlev için dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Syntax

struct output_iterator_tag {} ;

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini bulması gerekir. :: İterator_category türündeki her Yineleyici için `Iterator` , `iterator_traits` <  `Iterator` >   yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Tür **Yineleyici** \< **Iter**> **:: iterator_category** , `Iter` Çıkış yineleyicisi olarak kullanılabilecek bir nesneyi açıklar.

Bu etiket, `value_type` `difference_type` diğer Yineleyici etiketlerinde olduğu gibi, ya da Yineleyici için parametreli değildir, çünkü çıkış yineleyiciler bir veya olarak değil `value_type` `difference_type` .

## <a name="example"></a>Örnek

' Nin nasıl kullanılacağına ilişkin bir örnek için bkz. [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) `iterator_tag` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
