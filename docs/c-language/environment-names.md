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

**ANSI 4.10.4.4** Bir ortam adı kümesi ve [getenv](../c-runtime-library/reference/getenv-wgetenv.md) işlevi tarafından kullanılan ortam listesini değiştirme yöntemi

Ortam adı kümesi sınırsızdır.

Bir C programının içinden ortam değişkenlerini değiştirmek için [_putenv](../c-runtime-library/reference/putenv-wputenv.md) işlevini çağırın. Windows 'daki komut satırından ortam değişkenlerini değiştirmek için SET komutunu kullanın (örneğin, LıB = D:\ olarak AYARLAYıN) LIBS).

C programı içinden ayarlanan ortam değişkenleri, yalnızca işletim sistemi komut kabuğu 'nun ana bilgisayar kopyası çalıştırıldığı sürece bulunur (CMD. EXE veya COMMAND.COM). Örneğin, satır

```
system( SET LIB = D:\LIBS );
```

komut kabuğu 'nun bir kopyasını çalıştırır (CMD. EXE), LIB ortam değişkenini ayarlayın ve C programına geri dönüp CMD 'nin ikincil kopyasından çıkılıyor. EXE. CMD 'nin bu kopyasından çıkılıyor. EXE, LIB geçici ortam değişkenini kaldırır.

Benzer şekilde, `_putenv` işlev tarafından yalnızca program sonlanana kadar yapılan değişiklikler.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)
