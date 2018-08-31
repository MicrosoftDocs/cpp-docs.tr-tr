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
ms.openlocfilehash: c9e1d883e0c7a2b214842b096fdf697ffc7d0192
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221747"
---
# <a name="command-modifiers"></a>Komut Değiştiriciler
İsteğe bağlı olarak, boşluk veya sekme ile ayrılmış bir komut, önceki bir veya daha fazla komut değiştiriciler belirtebilirsiniz. Komutları gibi değiştiriciler girintili gerekir.  
  
|Değiştirici|Amaç|  
|--------------|-------------|  
|@*Komutu*|Komut görüntülenmesini önler. Ekran komutları tarafından gizlenen değil. Varsayılan olarak, tüm yürütülen komutlar NMAKE görüntülemektedir. /S görünen tüm görevleri için gizlemek için kullanın. kullanma **. Sessiz** görüntülenmesine için derleme görevleri dosyası bir parçası.|  
|**-**\[*sayı*] *komutu*|İçin hata denetimini kapatır *komut*. Varsayılan olarak, bir komut sıfır olmayan çıkış kodu döndürüldüğünde NMAKE durdurur. IF -*numarası* olan kullanıldığında, NMAKE çıkış kodu aşarsa durdurur *numarası*. Boşluk veya sekme çizgi bulunamaz ve *sayı.* En az bir boşluk veya sekme arasında görünmelidir `number` ve *komut*. /I hata tüm görevleri için denetimi devre dışı bırakmak için kullanın. kullanma **. Yoksay** hata derleme görevleri dosyası bir parçası için denetimi devre dışı bırakmak için.|  
|**\!** *Komutu*|Yürütür *komut* bağımlı her dosya için *komut* kullanan <strong>$ \* \*</strong> (bağımlılık içindeki tüm bağımlı dosyaları) veya **$?** (tüm bağımlı dosyaları hedef daha sonraki bir zaman damgasına sahip bağımlılık olarak).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)