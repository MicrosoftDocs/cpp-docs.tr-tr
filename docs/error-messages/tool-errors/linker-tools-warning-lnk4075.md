---
title: "Bağlayıcı araçları uyarısı LNK4075 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4075
dev_langs: C++
helpviewer_keywords: LNK4075
ms.assetid: f39ad3f9-c263-4cf0-9d70-259fc56ac96d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8c3330e637ae0e0dce5e875fcc349c6deefcf27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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