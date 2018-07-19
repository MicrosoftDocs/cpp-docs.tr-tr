---
title: Main işlevi kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3114f1ef379495f36f4231dbad6fd41ac145bcfe
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941752"
---
# <a name="main-function-restrictions"></a>main İşlevi Kısıtlamaları
Birkaç kısıtlama `main` başka bir C++ işlevi için geçerli olmayan bir işlev. `main` İşlevi:  
  
-   Aşırı yüklenemez (bkz [işlev aşırı yüklemesi](function-overloading.md)).  
  
-   Olarak bildirilemez **satır içi**.  
  
-   Olarak bildirilemez **statik**.  
  
-   Alınan adresi olamaz.  
  
-   Çağrılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)