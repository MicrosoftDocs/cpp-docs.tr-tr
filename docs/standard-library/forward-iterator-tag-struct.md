---
title: forward_iterator_tag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2fa9e405162f0ed56866a5c8e15d894010396e1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag Yapısı

Dönüş türü için sağlayan bir sınıf **iterator_category** iletme yineleyici gösteren işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
struct forward_iterator_tag    : public input_iterator_tag {};
```

## <a name="remarks"></a>Açıklamalar

Kategori etiket sınıflarını algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilmeleri ne yineleyici bağımsız değişkeni en belirli kategorisi olduğunu bulmak şablon işlevi gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** yineleyici'nin davranışını tanımlar en özel kategori etiketi olarak tanımlanması gerekir.

Aynı türdür **yineleyici** \< **Iter**> **:: iterator_category** zaman **Iter** açıklayan bir bir iletme yineleyici hizmet verebilir nesnesi.

## <a name="example"></a>Örnek

Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek **iterator_tag**s.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[input_iterator_tag Yapısı](../standard-library/input-iterator-tag-struct.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
