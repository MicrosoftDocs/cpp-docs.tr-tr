---
title: BSCMAKE Komut Dosyası (Yanıt Dosyası)
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 6be6dae2ef3dd729819a5eccba5e86df479ab5ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587319"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE Komut Dosyası (Yanıt Dosyası)

Kısmını veya tamamını bir komut dosyası komut satırı giriş sağlayabilirsiniz. Aşağıdaki sözdizimini kullanarak bir komut dosyası belirtin:

```
BSCMAKE @filename
```

Yalnızca bir komut dosyası izin verilir. Bir yol belirtebilirsiniz *filename*. Önünde *filename* ile bir at işareti (**\@**). BSCMAKE uzantı varsaymaz. Belirtebileceğiniz ek *sbrfiles* sonra komut satırında *filename*. Komut dosyası komut satırında belirttiğiniz gibi aynı sırada BSCMAKE girişi içeren bir metin dosyasıdır. Komut satırı bağımsız değişkenleri, bir veya daha fazla boşluk, sekme veya yeni satır karakterleri ile ayırın.

BSCMAKE komut dosyası kullanarak aşağıdaki komutu çağırır:

```
BSCMAKE @prog1.txt
```

Örnek komut dosyası aşağıda verilmiştir:

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>Ayrıca Bkz.

[BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)