---
title: "Bağlayıcı seçeneklerini ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b64b1dfd342598735124940d01b1bb4939242e10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-linker-options"></a>Bağlayıcı Seçeneklerini Ayarlama
Bağlayıcı seçenekleri içinde veya geliştirme ortamı dışındaki ayarlayabilirsiniz. Her bağlayıcı seçeneği konuda geliştirme ortamında nasıl ayarlanabilir anlatılmaktadır. Bkz: [bağlayıcı seçenekleri](../../build/reference/linker-options.md) tam listesi için.  
  
 Geliştirme ortamı dışında bağlantı çalıştırdığınızda, bir veya daha fazla yollarla giriş belirtebilirsiniz:  
  
-   Üzerinde [komut satırı](../../build/reference/linker-command-line-syntax.md)  
  
-   Kullanarak [komut dosyaları](../../build/reference/link-command-files.md)  
  
-   İçinde [ortam değişkenleri](../../build/reference/link-environment-variables.md)  
  
 BAĞLANTI ilk işlemleri seçenekleri seçenekleri komut satırında belirtilen bunlar sırasıyla ve komut dosyaları ve ardından bağlantıyı ortam değişkeninde belirtilen. Bir seçenek farklı bağımsız değişkenlerle yineleniyorsa işlediği son olaydan önceliklidir.  
  
 Seçenekler tüm yapı için geçerlidir; hiçbir seçenek belirli giriş dosyalara uygulanabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)