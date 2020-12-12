---
description: 'Hakkında daha fazla bilgi edinin: forward_iterator_tag struct'
title: forward_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::forward_iterator_tag
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
ms.openlocfilehash: 9b8b5ea7ff4e7d68c14c892d4ba6ef96f275b7da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324313"
---
# <a name="forward_iterator_tag-struct"></a>forward_iterator_tag Yapısı

İleri Yineleyici temsil eden **iterator_category** işlevi için dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Syntax

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini ne olduğunu bulması gerekir. :: İterator_category türündeki her Yineleyici için `Iterator` , `iterator_traits` <  `Iterator` >   yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Tür, **Yineleyici** \< **Iter**> **:: iterator_category** , bir ileri Yineleyici olarak  işlev görebilecek bir nesne açıkladığı zaman.

## <a name="example"></a>Örnek

**İterator_tag** s 'yi nasıl kullanacağınızı gösteren bir örnek için bkz. [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[input_iterator_tag yapısı](../standard-library/input-iterator-tag-struct.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
