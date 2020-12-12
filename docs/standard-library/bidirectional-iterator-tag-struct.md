---
description: 'Hakkında daha fazla bilgi edinin: bidirectional_iterator_tag struct'
title: bidirectional_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::bidirectional_iterator_tag
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
ms.openlocfilehash: db8de79c0fa5f9c748d453fcba7443351dcf217d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325565"
---
# <a name="bidirectional_iterator_tag-struct"></a>bidirectional_iterator_tag Yapısı

`iterator_category`Çift yönlü yineleyiciyi temsil eden işlev için dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Syntax

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini bulması gerekir. `Iterator`>:: iterator_category türündeki her Yineleyici için, `iterator_traits` <  `Iterator` yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır. 

Tür **Yineleyici** \< **Iter**> :: **iterator_category** , `Iter` çift yönlü bir yineleyici olarak işlev görebilecek bir nesne tanımlıyor.

## <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz. [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) `bidirectional_iterator_tag` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[forward_iterator_tag yapısı](../standard-library/forward-iterator-tag-struct.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
