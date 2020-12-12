---
description: 'Daha fazla bilgi edinin: nokta yönergeleri'
title: Nokta Yönergeleri
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
ms.openlocfilehash: 41b13d5f0f0f0a04ee47a9958be76c384617fe5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192869"
---
# <a name="dot-directives"></a>Nokta Yönergeleri

Bir satır başlangıcında bir açıklama bloğunun dışında nokta yönergeleri belirtin. Nokta yönergeleri noktayla başlar (. ) ve ardından iki nokta üst üste (:). Boşluklara ve sekmelere izin verilir. Nokta yönergesi adları büyük/küçük harfe duyarlıdır ve büyük harfle yazılır.

|Deki|Amaç|
|---------------|-------------|
|**. Yoksay**|Komut dosyası tarafından döndürülen sıfır olmayan çıkış kodlarını yok sayar, belirtilen konumdan derleme görevleri dosyasının sonuna kadar belirtilir. Varsayılan olarak, bir komut sıfır dışında bir çıkış kodu döndürürse nmake durursa. Hata denetimini geri yüklemek için kullanın **! CMDANAHTARLARÝ**. Tek bir komutun çıkış kodunu yoksaymak için Dash (-) değiştiricisini kullanın. Dosyanın tamamına ait çıkış kodlarını yoksaymak için/Ikullanın.|
|**. Değerli:** *hedefler*|Güncelleştirme komutları durdurulmuşsa, diskteki *hedefleri* korur; bir komut dosyayı silerek bir kesmeyi işlediğinde, hiçbir etkisi olmaz. Hedef adlarını bir veya daha fazla boşluk veya sekme ile ayırın. Varsayılan olarak, bir derleme CTRL + C veya CTRL + BREAK ile kesintiye uğrarsa NMAKE bir hedef siler. Her kullanımı **. Daha değerli,** derleme görevleri dosyasının tamamına uygulanır; birden çok belirtim birikimlidir.|
|**. KATıLıMı**|Yürütülen komutların, derleme görevleri dosyasının sonuna kadar belirtildiği yerden görüntülenmesini önler. Varsayılan olarak NMAKE, çağırdığı komutları görüntüler. Yankıyı geri yüklemek için kullanın **! CMDANAHTARLARÝ**. Tek bir komutun yankısını gizlemek için **@** değiştiricisini kullanın. Tüm bir dosyanın yankısını gizlemek için/S. komutunu kullanın.|
|**. SONEKLER:**`list`|Çıkarım kuralı eşleştirmesi için uzantıları listeler; Aşağıdaki uzantıları içerecek şekilde önceden tanımlanmıştır:. exe. obj. asm. c. cpp. cxx. bas. CBL. for. pas. res. rc. f. f90|

Öğesini değiştirmek için **. SONEK** listesi sırası veya yeni bir liste belirtmek için listeyi temizleyin ve yeni bir ayar belirtin. Listeyi temizlemek için, iki nokta üst üste işaretinden sonra uzantı belirtmeyin:

```
.SUFFIXES :
```

Listenin sonuna ek sonekler eklemek için şunu belirtin

```
.SUFFIXES : suffixlist
```

burada, *soneklist* , bir veya daha fazla boşluk ya da sekme ile ayrılmış ek sonekler listesidir. Geçerli ayarını görmek için **. SON ekler**, NMAKE with/pçalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
