---
title: Komut değiştiriciler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3739c053797bdccd08310e17bf669413ead0db48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="command-modifiers"></a>Komut Değiştiriciler
İsteğe bağlı alanları veya sekmelerle ayrılmış bir komutu, önceki bir veya daha fazla komut değiştiriciler belirtebilirsiniz. Komutlarla olduğu gibi değiştiricileri girintili gerekir.  
  
|Değiştirici|Amaç|  
|--------------|-------------|  
|@*komutu*|Komutun görüntülenmesini engeller. Görüntü komutları tarafından gizlenen değil. Varsayılan olarak, yürütülen tüm komutlar NMAKE görüntülemektedir. Tüm makefile görüntülenmesine /S kullanın; kullanmak **. Sessiz** derleme görevleri dosyası kısmı için görüntüleme gizlemek için.|  
|**-**[`number` ]*komutu*|Hata denetleme kapatır *komutu*. Varsayılan olarak, bir komutu sıfır olmayan çıkış kodu döndürdüğünde NMAKE durur. IF -`number` olan kullanıldığında, NMAKE çıkış kodu aşarsa durdurur `number`. Boşluk veya sekmeler arasında çizgi bulunamaz ve *numarası.* En az bir boşluk veya sekme arasında görünmelidir `number` ve *komutu*. Hata için tüm derleme görevleri dosyası denetimini devre dışı bırakmak üzere /I kullanın; kullanmak **. Yoksay** hata derleme görevleri dosyası bir parçası için denetimi devre dışı bırakmak için.|  
|**\!** *komutu*|Yürütür *komutu* bağımlı her dosya için *komutu* kullanan **$ \* \*** (tüm bağımlı dosyaları bağımlılık) veya **$?** (tüm bağımlı dosyaları hedef daha sonraki bir zaman damgasına sahip bağımlılık).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)