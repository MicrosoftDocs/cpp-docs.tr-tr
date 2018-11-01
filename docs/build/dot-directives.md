---
title: Nokta Yönergeleri
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
ms.openlocfilehash: 18688afedfe076ea2e4485471ffbe92dc2e09a2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542876"
---
# <a name="dot-directives"></a>Nokta Yönergeleri

Nokta yönergeleri bir satırın başında bir açıklama bloğu dışında belirtin. Nokta yönergeleri başlayan bir nokta (. ) ve iki nokta (:) tarafından izlenir. Boşluk ve sekme izin verilir. Nokta yönerge adları büyük küçük harfe duyarlı ve büyük.

|Yönergesi|Amaç|
|---------------|-------------|
|**. YOKSAY:**|Derleme görevleri dosyası sonuna belirtilen bir yerden komutları tarafından döndürülen sıfır olmayan bir çıkış kodlarını dikkate almaz. Varsayılan olarak, bir komut sıfır olmayan çıkış kodu döndürürse NMAKE durdurur. Hata denetimi geri yüklemek için kullanmak **! CMDSWITCHES**. Tek bir komut için çıkış kodu yoksaymak için tire (-) değiştiricisini kullanın. Tüm dosyası için çıkış kodları yoksaymak için kullanma / ediyorum.|
|**. DEĞERLİ:** *hedefleri*|Korur *hedefleri* güncelleştirmek için komutları durdurulduysa MFC'yi; dosyayı silerek kesme komutu işler disk üzerinde etkisi yoktur. Hedef adları, bir veya daha fazla boşluk veya sekme ile ayırın. CTRL + C ya da CTRL + BREAK tarafından bir derleme kesintiye uğrarsa varsayılan olarak, bir hedef NMAKE siler. Her kullanımının **. DEĞERLİ** tüm görevleri için; geçerli toplu birden çok belirtimleri.|
|**. SESSİZ:**|Derleme görevleri dosyası sonuna belirtilen bir yerden yürütülen komutlar görüntülenmesini bastırır. Varsayılan olarak, NMAKE çağırdığı komutları görüntüler. Yankı geri yüklemek için kullanmak **! CMDSWITCHES**. Tek bir komutun Yankı engellemek için kullanın **@** değiştiricisi. Tüm bir dosyada Yankı bastırmak için kullanma/S.|
|**. SONEKLERİ:** `list`|Çıkarım kuralı eşlemek için uzantıları listeler. Aşağıdaki uzantılar dahil etmek için önceden tanımlanmış: .exe .obj .asm .c .cpp .cxx .bas .cbl sunulabilen .pas .res .rc .f .f90|

Değiştirilecek **. SONEKLERİ** listesi sırası veya yeni bir liste belirtmek için listeyi temizlemek ve yeni bir ayar belirtin. Listesini temizlemek için iki noktadan sonra hiçbir uzantı belirtin:

```
.SUFFIXES :
```

Daha fazla sonek listenin sonuna eklemek için belirtin.

```
.SUFFIXES : suffixlist
```

Burada *suffixlist* ek sonekler, bir veya daha fazla boşluk veya sekme ile ayrılmış bir listesi verilmiştir. Geçerli ayarını görmek için **. SONEKLERİ**, parametresini ile NMAKE çalıştırma

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Başvurusu](../build/nmake-reference.md)