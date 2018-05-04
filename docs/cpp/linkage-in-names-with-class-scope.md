---
title: Sınıf kapsamlı Adlardaki | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9eb58f87e998fbe1eeeb9b26eb0da75046a9079d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="linkage-in-names-with-class-scope"></a>Sınıf Kapsamlı Adlardaki Bağlantı
Aşağıdaki bağlantı kuralları, sınıf kapsamına sahip adlar için geçerlidir:  
  
-   Statik sınıf üyelerinin dış bağlantısı vardır.  
  
-   Sınıf üyesi işlevlerinin dış bağlantısı vardır.  
  
-   Numaralandırıcılar ve `typedef` adlarının bağlantısı yoktur.  
  
 **Microsoft özel**  
  
-   `friend` işlevleri olarak bildirilen işlevlerin dış bağlantısı olması gerekir. Statik bir işlevin `friend` olarak bildirilmesi, bir hata oluşturur.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program ve Bağlantı](../cpp/program-and-linkage-cpp.md)