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
ms.workload: cplusplus
ms.openlocfilehash: 8ba42921f1e192c90e302b437b9a7d1b4e5eb34e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)