---
description: 'Hakkında daha fazla bilgi edinin: Komut değiştiriciler'
title: Komut Değiştiriciler
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
ms.openlocfilehash: d17d5f25719dfe5638ca6688105517d385bdf68e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182378"
---
# <a name="command-modifiers"></a>Komut Değiştiriciler

Bir komuttan önce bir veya daha fazla komut değiştiricisi belirtebilir, isteğe bağlı olarak boşluklarla veya sekmeye ayrılabilir. Komutlarda olduğu gibi değiştiriciler de girintili olmalıdır.

|Değiştirici|Amaç|
|--------------|-------------|
|\@*komutundaki*|Komutun görüntülenmesini önler. Komutlara göre görüntüle bastırılmaz. Varsayılan olarak NMAKE tüm yürütülen komutları yankılar. Derleme görevleri dosyasının tamamının görüntülenmesini engellemek için/S kullanın; kullanın **.** Makefile 'ın bir parçası için ekranı bastırmak IÇIN sessiz.|
|**-**\[*sayı*] *komut*|*Komut* için hata denetimini devre dışı bırakır. Varsayılan olarak, bir komut sıfır dışında bir çıkış kodu döndürdüğünde NMAKE durur. Eğer-*Number* kullanılırsa, çıkış kodu *SAYıYı* aşarsa NMAKE durdu. Tire ve sayı arasında boşluk veya sekme bulunamaz *.* And komutuyla en az bir boşluk veya sekme görünmelidir `number` .  Derleme görevleri dosyasının tamamında hata denetimini devre dışı bırakmak için/I kullanın; kullanın **.** Makefile 'ın bir parçası olarak hata denetimini devre dışı bırakmak IÇIN yoksayın.|
|**!** *komutundaki*|*Komut* kullanılıyorsa her bağımlı dosya için *komutu* yürütür <strong>$\*\*</strong> (bağımlılıkta tüm bağımlı dosyalar) veya **$?** (hedeften daha sonraki bir zaman damgasına sahip olan bağımlılıkta tüm bağımlı dosyalar).|

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyasındaki komutlar](commands-in-a-makefile.md)
