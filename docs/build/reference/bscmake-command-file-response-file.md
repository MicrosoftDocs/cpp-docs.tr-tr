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
ms.openlocfilehash: 6a55fd616a00aeb3ade229bf7cff8220f86085b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295051"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE Komut Dosyası (Yanıt Dosyası)

> [!WARNING]
> BSCMAKE hala Visual Studio ile yüklenir ancak artık IDE tarafından kullanılır. Visual Studio 2008'den itibaren göz atma ve sembol bilgilerini otomatik olarak bir SQL Server .sdf dosyası çözüm klasöründe depolanır.

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

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE Başvurusu](bscmake-reference.md)
