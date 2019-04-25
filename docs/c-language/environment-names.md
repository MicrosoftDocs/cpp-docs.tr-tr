---
title: Ortam Adları
ms.date: 11/04/2016
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
ms.openlocfilehash: 43e1254b4c1ee61a92fbb6499d9396e8b15a3047
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234133"
---
# <a name="environment-names"></a>Ortam Adları

**ANSI 4.10.4.4** ortam adları ve tarafından kullanılan ortam listesi değiştirilmesi için yöntem kümesi [getenv](../c-runtime-library/reference/getenv-wgetenv.md) işlevi

Ortam adları kümesini sınırsızdır.

Bir C programının içinden gelen ortam değişkenlerini değiştirmek için çağrı [_putenv](../c-runtime-library/reference/putenv-wputenv.md) işlevi. Windows komut satırında ortam değişkenlerini değiştirmek için SET komutunu kullanma (LIB gibi ayarlama D:\ = KİTAPLIKLAR).

Yalnızca işletim sistemi komut kabuğu, konak kopyasını (cmd çalıştırıldığı sürece bir C programının kümeden ortam değişkenleri var EXE veya Command.COM'DUR). Örneğin, satır

```
system( SET LIB = D:\LIBS );
```

bir komut kabuğunu (cmd kopyasını çalıştırmanız EXE) LIB ortam değişkenini ayarlamak ve çıkma cmd ikincil kopyası C programına döndürür EXE. Bu kopyasını CMD'yi çıkılıyor EXE geçici ortam değişkeni LIB'e kaldırır.

Benzer şekilde, tarafından yapılan değişiklikleri `_putenv` yalnızca program sonlanana kadar son işlev.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)
