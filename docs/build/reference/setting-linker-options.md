---
title: Bağlayıcı seçeneklerini ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18728994be3f44152a263fb8a6009728e33a42a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374927"
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