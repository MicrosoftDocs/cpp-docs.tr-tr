---
title: "Sınıf kapsamlı Adlardaki | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cc10af2fc65de8382d5b8a26ac70cad9b9727e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Program ve bağlantı](../cpp/program-and-linkage-cpp.md)