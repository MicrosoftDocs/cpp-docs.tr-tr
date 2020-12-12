---
description: 'Hakkında daha fazla bilgi için: makefile içindeki komutlar'
title: Derleme Görevleri Dosyası Komutları
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: a4f3c6d3cc9b5d567548d7b3f2bd7679d492ebf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179089"
---
# <a name="commands-in-a-makefile"></a>Derleme Görevleri Dosyası Komutları

Bir açıklama bloğu veya çıkarım kuralı, bağımlılık güncel değilse çalıştırılacak bir komut bloğunu belirtir. NMAKE,/S, değilse, çalıştırmadan önce her komutu görüntüler **. SESSIZ**, **! CMDSWITCHES** veya \@ kullanılır. Bir açıklama bloğunun arkasından bir komut bloğu yoksa, NMAKE eşleşen bir çıkarım kuralı arar.

Bir komut bloğu, her biri kendi satırı üzerinde bir veya daha fazla komut içerir. Bağımlılık veya kural ile komutlar bloğu arasında boş satır bulunamaz. Ancak, yalnızca boşluk veya sekme içeren bir satır görünebilir; Bu satır, null bir komut olarak yorumlanır ve hata oluşmaz. Komut satırları arasında boş satırlara izin verilir.

Bir komut satırı, bir veya daha fazla boşluk veya sekme ile başlar. Yeni satır karakteri tarafından izlenen ters eğik çizgi (\), komutta boşluk olarak yorumlanır; bir komutun sonraki satıra devam etmesi için satırın sonunda bir ters eğik çizgi kullanın. NMAKE, boşluk veya sekme dahil olmak üzere başka bir karakter varsa ters eğik çizgiyi Yorumlar ve ters eğik çizgiyi izler.

Önünde noktalı virgül (;) bir bağımlılık çizgisi veya çıkarım kuralında görünebilir, bu, bir komut bloğunun takip edilip edilmeyeceğini belirtir:

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Komut değiştiriciler](command-modifiers.md)

[Dosya adı parçaları söz dizimi](filename-parts-syntax.md)

[Derleme görevleri dosyasındaki satır içi dosyalar](inline-files-in-a-makefile.md)

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
