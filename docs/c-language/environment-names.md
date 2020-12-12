---
description: 'Daha fazla bilgi edinin: ortam adları'
title: Ortam Adları
ms.date: 11/04/2016
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
ms.openlocfilehash: f40da15151385cea4bd581dea8946f50d2b58ea8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213760"
---
# <a name="environment-names"></a>Ortam Adları

**ANSI 4.10.4.4** Bir ortam adı kümesi ve [getenv](../c-runtime-library/reference/getenv-wgetenv.md) işlevi tarafından kullanılan ortam listesini değiştirme yöntemi

Ortam adı kümesi sınırsızdır.

Bir C programının içinden ortam değişkenlerini değiştirmek için [_putenv](../c-runtime-library/reference/putenv-wputenv.md) işlevini çağırın. Windows 'daki komut satırından ortam değişkenlerini değiştirmek için SET komutunu kullanın (örneğin, LıB = D:\ olarak AYARLAYıN) LIBS).

C programı içinden ayarlanan ortam değişkenleri yalnızca işletim sistemi komut kabuğu 'nun ana bilgisayar kopyası çalıştığı sürece bulunur (CMD.EXE veya COMMAND.COM). Örneğin, satır

```
system( SET LIB = D:\LIBS );
```

, komut kabuğu 'nun bir kopyasını (CMD.EXE) çalıştırır, ortam değişkenini ayarlar ve C programına geri dönüp, CMD.EXE ikincil kopyasından çıkılıyor. Bu CMD.EXE kopyasından çıkıldıktan sonra, geçici ortam değişkeni LIB kaldırılır.

Benzer şekilde, `_putenv` işlev tarafından yalnızca program sonlanana kadar yapılan değişiklikler.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Işlevleri](../c-language/library-functions.md)<br/>
[_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)<br/>
[getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)
