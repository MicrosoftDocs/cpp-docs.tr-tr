---
title: "Önemli hata C1311 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1311
dev_langs: C++
helpviewer_keywords: C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9aeb63e041ddfe26a8fc47afc838f2f5c3ce35d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1311"></a>Önemli hata C1311
COFF biçimi statik olarak 'var' numara miktarında bir adresi ile başlatamıyor  
  
 Değeri derleme zamanında bilinmiyor adres türü dört bayt'tan küçük, depolama alanına sahip bir değişken için statik olarak atanamaz.  
  
 Bu hata, aksi takdirde kodu oluşabilir geçerli C++.  
  
 Aşağıdaki örnek C1311 neden olabilecek bir koşul gösterir.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```