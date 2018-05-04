---
title: Blok kapsamlı Adlardaki | Microsoft Docs
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
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab7758e962c028c4746836e470ee43eaab510f9e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="linkage-in-names-with-block-scope"></a>Blok Kapsamlı Adlardaki Bağlantı
Blok kapsam içeren adlar (yerel adları) için aşağıdaki bağlantı kuralları geçerlidir:  
  
-   Adları bildirilen `extern` bunlar daha önce olarak bildirilen sürece dış bağlantı sahip **statik**.  
  
-   Blok kapsamı içeren diğer tüm adların, hiçbir bağlantısı yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program ve Bağlantı](../cpp/program-and-linkage-cpp.md)