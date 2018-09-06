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
ms.openlocfilehash: fd86adc94de90222e0775d89543a4dc25486f74f
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894505"
---
# <a name="command-modifiers"></a>Komut Değiştiriciler

İsteğe bağlı olarak, boşluk veya sekme ile ayrılmış bir komut, önceki bir veya daha fazla komut değiştiriciler belirtebilirsiniz. Komutları gibi değiştiriciler girintili gerekir.

|Değiştirici|Amaç|
|--------------|-------------|
|\@*Komutu*|Komut görüntülenmesini önler. Ekran komutları tarafından gizlenen değil. Varsayılan olarak, tüm yürütülen komutlar NMAKE görüntülemektedir. /S görünen tüm görevleri için gizlemek için kullanın. kullanma **. Sessiz** görüntülenmesine için derleme görevleri dosyası bir parçası.|
|**-**\[*sayı*] *komutu*|İçin hata denetimini kapatır *komut*. Varsayılan olarak, bir komut sıfır olmayan çıkış kodu döndürüldüğünde NMAKE durdurur. IF -*numarası* olan kullanıldığında, NMAKE çıkış kodu aşarsa durdurur *numarası*. Boşluk veya sekme çizgi bulunamaz ve *sayı.* En az bir boşluk veya sekme arasında görünmelidir `number` ve *komut*. /I hata tüm görevleri için denetimi devre dışı bırakmak için kullanın. kullanma **. Yoksay** hata derleme görevleri dosyası bir parçası için denetimi devre dışı bırakmak için.|
|**\!** *Komutu*|Yürütür *komut* bağımlı her dosya için *komut* kullanan <strong>$ \* \*</strong> (bağımlılık içindeki tüm bağımlı dosyaları) veya **$?** (tüm bağımlı dosyaları hedef daha sonraki bir zaman damgasına sahip bağımlılık olarak).|

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyası Komutları](../build/commands-in-a-makefile.md)
