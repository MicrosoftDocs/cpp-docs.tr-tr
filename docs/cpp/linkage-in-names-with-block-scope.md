---
title: "Blok kapsamlı Adlardaki | Microsoft Docs"
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
- block scope [C++]
- external linkage, scope linkage rules
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0549538ba2af256d3a98b83dcb691327e387de9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linkage-in-names-with-block-scope"></a>Blok Kapsamlı Adlardaki Bağlantı
Blok kapsam içeren adlar (yerel adları) için aşağıdaki bağlantı kuralları geçerlidir:  
  
-   Adları bildirilen `extern` bunlar daha önce olarak bildirilen sürece dış bağlantı sahip **statik**.  
  
-   Blok kapsamı içeren diğer tüm adların, hiçbir bağlantısı yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program ve bağlantı](../cpp/program-and-linkage-cpp.md)