---
title: Nokta Yönergeleri
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
ms.openlocfilehash: 2c21e8a18c76331f86a4e8966b4f67c9c9bc9b7d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342818"
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

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
