---
title: "Giriş ve çıkış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35e97e7bbbc04699e813b6890180512043c4e25d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="input-and-output"></a>Girdi ve Çıktı
G/ç işlevleri okuyup dosyalarından ve cihazlar için veri yazma. G/ç işlemleri metin modunda veya ikili mod gerçekleşir. Microsoft çalışma zamanı kitaplığı g/ç işlevleri üç tür vardır:  
  
-   [Akış g/ç](../c-runtime-library/stream-i-o.md) işlevleri veri karakterleri tek tek bir akış ele alın.  
  
-   [Düşük düzey g/ç](../c-runtime-library/low-level-i-o.md) işlevleri çağırma akış g/ç tarafından sağlanan daha düşük düzeyli işlemi için doğrudan işletim sistemi.  
  
-   [Konsol ve g/ç bağlantı noktası](../c-runtime-library/console-and-port-i-o.md) işlevleri okuma veya doğrudan bir konsol (klavye ve ekran) veya bir g/ç bağlantı noktası (örneğin, yazıcı bağlantı noktası) yazma.  
  
    > [!NOTE]
    >  Akışı işlevleri arabelleğe ve alt düzey işlevleri olmayan olduğundan bu iki tür işlev genellikle uyumlu değil. Belirli bir dosya işleme için akış veya alt düzey işlevleri özel olarak kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)