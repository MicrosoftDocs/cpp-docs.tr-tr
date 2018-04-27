---
title: bidirectional_iterator_tag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 800968993b874070ccc32baf91e8feec3e01e472
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="bidirectionaliteratortag-struct"></a>bidirectional_iterator_tag Yapısı

Dönüş türü için sağlayan bir sınıf **iterator_category** çift yönlü yineleyici temsil eden bir işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiket sınıflarını algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilmeleri şablon işlevi yineleyici bağımsız değişkeni, en belirgin kategorisini bulması gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator`>:: **iterator_category** yineleyici'nin davranışını tanımlar en özel kategori etiketi olarak tanımlanması gerekir.

Aynı türdür **yineleyici** \< **Iter**>:: **iterator_category** zaman **Iter** için bir nesne açıklar çift yönlü yineleyici görev yapar.

## <a name="example"></a>Örnek

Bkz: [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek `bidirectional_iterator_tag`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[forward_iterator_tag Yapısı](../standard-library/forward-iterator-tag-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
