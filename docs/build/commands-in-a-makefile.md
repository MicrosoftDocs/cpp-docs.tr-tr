---
title: Derleme Görevleri Dosyası Komutları
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: 8b640e8a7a1773e69792453de6cb70bcb09c988f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668240"
---
# <a name="commands-in-a-makefile"></a>Derleme Görevleri Dosyası Komutları

Açıklama bloğu veya çıkarım kuralı bloğunu güncel olmayan bir bağımlılıktır çalıştırılacak komutları belirtir. NMAKE görüntüler her komut, çalıştırmadan önce sürece /S, **. Sessiz**, **! CMDSWITCHES**, veya \@ kullanılır. Açıklama bloğu komutları bloğu tarafından uyulmazsa NMAKE için eşleşen bir çıkarma kuralı arar.

Bir komut bloğu her biri kendi satırında bir veya daha fazla komut içerir. Boş bir satır, bağımlılık veya kural ve komutları blok arasında görünebilir. Ancak, yalnızca boşluk veya sekme içeren bir satır görünebilir; Bu satır null bir komut olarak yorumlanır ve herhangi bir hata oluşur. Boş satırlar arasında komut satırları izin verilir.

Bir komut satırı, bir veya daha fazla boşluk veya sekme ile başlar. Bir yeni satır karakteri ve ardından bir eğik çizgi (\), komut bir boşluk olarak yorumlanır; ters eğik çizgi bir satırın sonunda bir komut sonraki satırın üzerine devam etmek için kullanın. NMAKE yorumlar ters eğik çizgi gerçek anlamda bir boşluk veya sekme gibi başka bir karakter ters eğik çizgi izliyorsa.

Bir komut noktalı virgül (;) tarafından öncesinde bir bağımlılık satırı veya çıkarım kuralı, komutları bloğunu izleyen olup olmadığını görünebilir:

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Komut değiştiriciler](../build/command-modifiers.md)

[Filename-parts söz dizimi](../build/filename-parts-syntax.md)

[Derleme görevleri dosyasındaki satır içi dosyalar](../build/inline-files-in-a-makefile.md)

## <a name="see-also"></a>Ayrıca Bkz.

[NMAKE Başvurusu](../build/nmake-reference.md)