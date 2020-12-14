---
description: 'Hakkında daha fazla bilgi edinin: input_iterator_tag struct'
title: input_iterator_tag Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::input_iterator_tag
helpviewer_keywords:
- input_iterator_tag class
- input_iterator_tag struct
ms.assetid: ad68a4c6-f315-4ce1-8b74-c1fc71bd1577
ms.openlocfilehash: 92bd110af71aecfa632b8e739126698eba457019
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231712"
---
# <a name="input_iterator_tag-struct"></a>input_iterator_tag Yapısı

Bir `iterator_category` giriş yineleyicisini temsil eden işlev için dönüş türü sağlayan bir sınıf.

## <a name="syntax"></a>Syntax

struct input_iterator_tag {} ;

## <a name="remarks"></a>Açıklamalar

Kategori etiketi sınıfları, algoritma seçimi için derleme etiketleri olarak kullanılır. Şablon işlevinin, derleme zamanında en verimli algoritmayı kullanabilmesi için yineleyici bağımsız değişkeninin en belirli kategorisini bulması gerekir. :: İterator_category türündeki her Yineleyici için `Iterator` , `iterator_traits` <  `Iterator` >   yineleyicinin davranışını açıklayan en özel kategori etiketi olacak şekilde tanımlanmalıdır.

Tür **Yineleyici** \< **Iter**> **:: iterator_category** , `Iter` bir giriş yineleyicisi olarak kullanılabilecek bir nesneyi açıklar.

## <a name="example"></a>Örnek

' Nin nasıl kullanılacağına ilişkin bir örnek için bkz. [iterator_traits](../standard-library/iterator-traits-struct.md) veya [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) `iterator_tag` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
