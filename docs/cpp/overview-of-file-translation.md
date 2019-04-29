---
title: Dosya Çevirisine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
ms.openlocfilehash: cb8a8fea2411e4eb7de78545f70021f3617b0f52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325149"
---
# <a name="overview-of-file-translation"></a>Dosya Çevirisine Genel Bakış

C++ programları, C programlarında olduğu gibi bir veya daha fazla dosyadan oluşur. Bu dosyaların her biri, aşağıdaki kavramsal sırayla çevrilir (gerçek sıra "gibi" kuralını izler: çeviri bu adımlar uygulanmış gibi gerçekleşmelidir):

1. Sözcük temelli belirteç oluşturma. Karakter eşleme ve üç harf işleme, satır birleştirme ve belirteç oluşturma bu çeviri aşamasında gerçekleştirilir.

1. Ön işleme. Bu çeviri aşaması, tarafından başvurulan yedek kaynak dosyalarını getirir `#include` yönergeleri, "dize haline getirme" ve "yönergeleri karakterleştirme" işler ve belirteç yapıştırma ve makro genişletme işlemlerini gerçekleştirir (bkz [önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) içinde *önişlemci başvurusu* daha fazla bilgi için). Ön işleme aşamasının sonucu, birlikte bir "çeviri birimini" tanımlayan belirteçler dizisidir.

   Önişlemci yönergeleri her zaman sayı işareti ile başlayan (**#**) karakteri (yani satırdaki ilk boşluk olmayan karakter sayı işareti olmalıdır). Belirli bir satırda yalnızca bir önişlemci yönergesi görünebilir. Örneğin:

    ```cpp
    #include <iostream>  // Include text of iostream in
                         //  translation unit.
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty
                         //  text string).
    ```

1. Kod oluşturma. Bu çeviri aşaması, nesne kodu oluşturmak için ön işleme aşamasında oluşturulan belirteçleri kullanır.

   Bu aşamada, kaynak kodunun sözdizimsel ve semantik denetimi gerçekleştirilir.

Bkz: [çeviri aşamaları](../preprocessor/phases-of-translation.md) içinde *önişlemci başvurusu* daha fazla bilgi için.

C++ önişlemcisi, ANSI C önişlemcisinin kesin bir üst kümesidir, ancak C++ önişlemcisi birkaç örnekte farklılık gösterir. Aşağıdaki listede, ANSI C ve C++ önişlemcileri arasındaki birkaç farklılık açıklanmaktadır:

- Tek satırlı yorumlar desteklenir. Bkz: [açıklamaları](../cpp/comments-cpp.md) daha fazla bilgi için.

- Önceden tanımlanmış bir makro `__cplusplus`, yalnızca C++ için tanımlanır. Bkz: [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md) içinde *önişlemci başvurusu* daha fazla bilgi için.

- C önişlemcisi C++ işleçlerini tanımaz: **.** <strong>\*</strong>, **->** <strong>\*</strong>, ve **::**. Bkz: [işleçleri](../cpp/cpp-built-in-operators-precedence-and-associativity.md) ve [ifadeleri](../cpp/expressions-cpp.md), işleçler hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)
