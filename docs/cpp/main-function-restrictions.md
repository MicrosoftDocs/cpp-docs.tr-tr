---
title: "Main işlevi kısıtlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Main
dev_langs: C++
helpviewer_keywords: main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a94844a0d5636c58a764114ed6f413923d69950
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="main-function-restrictions"></a>main İşlevi Kısıtlamaları
Birkaç kısıtlamaları uygulamak **ana** diğer C++ işlevleri için geçerli olmayan işlevi. **Ana** işlevi:  
  
-   Aşırı yüklenemez (bkz [işlev aşırı yüklemesi](function-overloading.md)).  
  
-   Olarak bildirilemez **satır içi**.  
  
-   Olarak bildirilemez **statik**.  
  
-   Alınan adresi olamaz.  
  
-   Çağrılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)