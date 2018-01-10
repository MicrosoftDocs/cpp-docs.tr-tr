---
title: "Komut değiştiriciler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 610725bf52522cd5041d2f6dcadb422bf942458a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="command-modifiers"></a>Komut Değiştiriciler
İsteğe bağlı alanları veya sekmelerle ayrılmış bir komutu, önceki bir veya daha fazla komut değiştiriciler belirtebilirsiniz. Komutlarla olduğu gibi değiştiricileri girintili gerekir.  
  
|Değiştirici|Amaç|  
|--------------|-------------|  
|@*komutu*|Komutun görüntülenmesini engeller. Görüntü komutları tarafından gizlenen değil. Varsayılan olarak, yürütülen tüm komutlar NMAKE görüntülemektedir. Tüm makefile görüntülenmesine /S kullanın; kullanmak **. Sessiz** derleme görevleri dosyası kısmı için görüntüleme gizlemek için.|  
|**-**[`number` ]*komutu*|Hata denetleme kapatır *komutu*. Varsayılan olarak, bir komutu sıfır olmayan çıkış kodu döndürdüğünde NMAKE durur. IF -`number` olan kullanıldığında, NMAKE çıkış kodu aşarsa durdurur `number`. Boşluk veya sekmeler arasında çizgi bulunamaz ve *numarası.* En az bir boşluk veya sekme arasında görünmelidir `number` ve *komutu*. Hata için tüm derleme görevleri dosyası denetimini devre dışı bırakmak üzere /I kullanın; kullanmak **. Yoksay** hata derleme görevleri dosyası bir parçası için denetimi devre dışı bırakmak için.|  
|**!** *komutu*|Yürütür *komutu* bağımlı her dosya için *komutu* kullanan  **$ \* \***  (tüm bağımlı dosyaları bağımlılık) veya **$?** (tüm bağımlı dosyaları hedef daha sonraki bir zaman damgasına sahip bağımlılık).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)