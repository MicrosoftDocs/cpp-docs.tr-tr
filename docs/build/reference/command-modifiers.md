---
title: Komut Değiştiriciler
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
ms.openlocfilehash: 6131b94a6ee78026b8d5337061a6238df785b64d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823471"
---
# <a name="command-modifiers"></a>Komut Değiştiriciler

İsteğe bağlı olarak, boşluk veya sekme ile ayrılmış bir komut, önceki bir veya daha fazla komut değiştiriciler belirtebilirsiniz. Komutları gibi değiştiriciler girintili gerekir.

|Değiştirici|Amaç|
|--------------|-------------|
|\@*Komutu*|Komut görüntülenmesini önler. Ekran komutları tarafından gizlenen değil. Varsayılan olarak, tüm yürütülen komutlar NMAKE görüntülemektedir. /S görünen tüm görevleri için gizlemek için kullanın. kullanma **. Sessiz** görüntülenmesine için derleme görevleri dosyası bir parçası.|
|**-**\[*number*] *command*|İçin hata denetimini kapatır *komut*. Varsayılan olarak, bir komut sıfır olmayan çıkış kodu döndürüldüğünde NMAKE durdurur. IF -*numarası* olan kullanıldığında, NMAKE çıkış kodu aşarsa durdurur *numarası*. Boşluk veya sekme çizgi bulunamaz ve *sayı.* En az bir boşluk veya sekme arasında görünmelidir `number` ve *komut*. /I hata tüm görevleri için denetimi devre dışı bırakmak için kullanın. kullanma **. Yoksay** hata derleme görevleri dosyası bir parçası için denetimi devre dışı bırakmak için.|
|**\!** *Komutu*|Yürütür *komut* bağımlı her dosya için *komut* kullanan <strong>$ \* \*</strong> (bağımlılık içindeki tüm bağımlı dosyaları) veya **$?** (tüm bağımlı dosyaları hedef daha sonraki bir zaman damgasına sahip bağımlılık olarak).|

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyası Komutları](commands-in-a-makefile.md)
