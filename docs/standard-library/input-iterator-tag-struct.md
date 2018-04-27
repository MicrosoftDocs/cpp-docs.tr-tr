---
title: input_iterator_tag yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::input_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c2a6384075151c38c3ec57d024e409edccda8bd
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="inputiteratortag-struct"></a>input_iterator_tag Yapısı

Dönüş türü için sağlayan bir sınıf **iterator_category** giriş yineleyici temsil eden bir işlev.

## <a name="syntax"></a>Sözdizimi

Yapı input_iterator_tag {};

## <a name="remarks"></a>Açıklamalar

Kategori etiket sınıflarını algoritması seçimi için etiketler derleme gibi kullanılır. Derleme zamanında en verimli algoritması kullanabilmeleri en özel kategori yineleyici bağımsız değişkeninin değerini bulmak şablon işlevi gerekir. Her yineleyici türü için `Iterator`, `iterator_traits` <  `Iterator` >  **:: iterator_category** yineleyici'nin davranışını tanımlar en özel kategori etiketi olarak tanımlanması gerekir.

Aynı türdür **yineleyici** \< **Iter**> **:: iterator_category** zaman **Iter** açıklayan bir Giriş yineleyici hizmet verebilir nesnesi.

## <a name="example"></a>Örnek

Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) nasıl kullanılacağına ilişkin bir örnek **iterator_tag**s.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
