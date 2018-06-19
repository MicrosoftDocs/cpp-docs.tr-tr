---
title: Bağlayıcı araçları uyarısı LNK4075 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4075
dev_langs:
- C++
helpviewer_keywords:
- LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bd9a4ecdad30a0be2d45300367f6f79a65a6b31
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301040"
---
# <a name="linker-tools-warning-lnk4075"></a>Bağlayıcı Araçları Uyarısı LNK4075
"seçenek" 1 "Seçenek2" belirtimi nedeniyle yoksayılıyor  
  
 İkinci seçenek ilk geçersiz kılar.  
  
 Birbirini dışlayan bağlayıcı seçenekleri belirttiğiniz.  Bağlayıcı seçenekleri inceleyin.  Bağlayıcı seçenekleri Burada belirtilen nasıl projenizi derleme bağlıdır.  
  
-   Geliştirme ortamında oluşturuluyorsa, projeniz için bağlayıcı özellik sayfaları bakın ve her iki bağlayıcı seçenekleri Burada belirtilen bakın.  Bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md) daha fazla bilgi için.  
  
-   Komut satırında derleme var. belirtilen bağlayıcı seçenekleri bakın.  
  
-   Yapı kodlarla yapılandırdıysanız, bu bağlayıcı seçenekler burada belirtilen görmek için komut dosyalarıyla arayın.  
  
 Birbirini dışlayan bağlayıcı seçenekleri Burada belirtilen bulduğunuzda, bağlayıcı seçeneklerden birini kaldırın.  
  
 Belirli bazı örnekler:  
  
-   İle derlenen bir modül bağlarsanız **/zı**, iç bağlayıcı seçeneği gelir /EDITANDCONTINUE ve /OPT:REF, /OPT:ICF veya /INCREMENTAL:NO, ile derlenen bir modül, hiçbir /EDITANDCONTINUE kapsıyor adlı, olur LNK4075 alın.  Bkz: [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md) daha fazla bilgi için.