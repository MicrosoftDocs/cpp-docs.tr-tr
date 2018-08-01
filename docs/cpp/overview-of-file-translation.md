---
title: Dosya çevirisine genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eec47e9810e0cc846cc351330512256a32f95aac
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406851"
---
# <a name="overview-of-file-translation"></a>Dosya Çevirisine Genel Bakış
C++ programları, C programlarında olduğu gibi bir veya daha fazla dosyadan oluşur. Bu dosyaların her biri, aşağıdaki kavramsal sırayla çevrilir (gerçek sıra "gibi" kuralını izler: çeviri bu adımlar uygulanmış gibi gerçekleşmelidir):  
  
1. Sözcük temelli belirteç oluşturma. Karakter eşleme ve üç harf işleme, satır birleştirme ve belirteç oluşturma bu çeviri aşamasında gerçekleştirilir.  
  
2. Ön işleme. Bu çeviri aşaması, tarafından başvurulan yedek kaynak dosyalarını getirir `#include` yönergeleri, "dize haline getirme" ve "yönergeleri karakterleştirme" işler ve belirteç yapıştırma ve makro genişletme işlemlerini gerçekleştirir (bkz [önişlemci yönergeleri](../preprocessor/preprocessor-directives.md) içinde *önişlemci başvurusu* daha fazla bilgi için). Ön işleme aşamasının sonucu, birlikte bir "çeviri birimini" tanımlayan belirteçler dizisidir.  
  
     Önişlemci yönergeleri her zaman sayı işareti ile başlayan (**#**) karakteri (yani satırdaki ilk boşluk olmayan karakter sayı işareti olmalıdır). Belirli bir satırda yalnızca bir önişlemci yönergesi görünebilir. Örneğin:  
  
    ```cpp 
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3. Kod oluşturma. Bu çeviri aşaması, nesne kodu oluşturmak için ön işleme aşamasında oluşturulan belirteçleri kullanır.  
  
     Bu aşamada, kaynak kodunun sözdizimsel ve semantik denetimi gerçekleştirilir.  
  
 Bkz: [çeviri aşamaları](../preprocessor/phases-of-translation.md) içinde *önişlemci başvurusu* daha fazla bilgi için.  
  
 C++ önişlemcisi, ANSI C önişlemcisinin kesin bir üst kümesidir, ancak C++ önişlemcisi birkaç örnekte farklılık gösterir. Aşağıdaki listede, ANSI C ve C++ önişlemcileri arasındaki birkaç farklılık açıklanmaktadır:  
  
- Tek satırlı yorumlar desteklenir. Bkz: [açıklamaları](../cpp/comments-cpp.md) daha fazla bilgi için.  
  
- Önceden tanımlanmış bir makro `__cplusplus`, yalnızca C++ için tanımlanır. Bkz: [önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md) içinde *önişlemci başvurusu* daha fazla bilgi için.  
  
- C önişlemcisi C++ işleçlerini tanımaz: **.\*** , **-> \***, ve `::`. Bkz: [işleçleri](../cpp/cpp-built-in-operators-precedence-and-associativity.md) ve [ifadeleri](../cpp/expressions-cpp.md), işleçler hakkında daha fazla bilgi.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Sözcük Temelli Kurallar](../cpp/lexical-conventions.md)