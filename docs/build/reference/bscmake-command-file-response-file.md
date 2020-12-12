---
description: 'Şu konuda daha fazla bilgi edinin: BSCMAKE komut dosyası (yanıt dosyası)'
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
ms.openlocfilehash: 4bb321cd7aa705d7e33d0f539ab3e0aa2e3cb8bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187162"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE Komut Dosyası (Yanıt Dosyası)

> [!WARNING]
> BSCMAKE, Visual Studio ile hala yüklü olsa da artık IDE tarafından kullanılmıyor. Visual Studio 2008 ' den itibaren, gezinme ve sembol bilgileri çözüm klasöründeki bir SQL Server. sdf dosyasında otomatik olarak depolanır.

Komut satırı girişinin bir kısmını veya tamamını bir komut dosyasına sağlayabilirsiniz. Aşağıdaki sözdizimini kullanarak komut dosyasını belirtin:

```
BSCMAKE @filename
```

Yalnızca bir komut dosyasına izin verilir. *Dosya adında* bir yol belirtebilirsiniz. *Dosya* adından önce bir at işareti ( **\@** ). BSCMAKE bir uzantı kabul etmez. *Dosya adından* sonra komut satırında ek *sbrfiles* belirtebilirsiniz. Komut dosyası, BSCMAKE girdisini komut satırında belirttiğiniz şekilde içeren bir metin dosyasıdır. Komut satırı bağımsız değişkenlerini bir veya daha fazla boşluk, sekme veya yeni satır karakteri ile ayırın.

Aşağıdaki komut, bir komut dosyası kullanarak BSCMAKE 'i çağırır:

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

[BSCMAKE başvurusu](bscmake-reference.md)
