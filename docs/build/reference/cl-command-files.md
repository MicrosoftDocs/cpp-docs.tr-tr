---
title: CL Komut Dosyaları
description: MSVC derleyicisi komut satırı seçeneklerini içeren komut dosyalarını belirtmenize olanak tanır.
ms.date: 07/08/2020
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
ms.openlocfilehash: 6deab4b11dcc6c53beb5b4fa8b014a56020c3420
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180948"
---
# <a name="cl-command-files"></a>CL Komut Dosyaları

Komut dosyası, derleyici seçeneklerini ve dosya adlarını içeren bir metin dosyasıdır. Bu, aksi takdirde [komut satırına](compiler-command-line-syntax.md)yazmanız veya [CL ortam değişkeninin](cl-environment-variables.md)kullanımını belirtmeniz için seçenekler sağlar. CL, bir derleyici komut dosyasını CL ortam değişkeninde ya da komut satırında bağımsız değişken olarak kabul eder. Komut satırının veya CL ortam değişkeninin aksine, bir komut dosyasında birden çok sayıda seçenek ve dosya adı kullanabilirsiniz.

Bir komut dosyası dosya adı CL ortam değişkeni içinde veya komut satırında göründüğünde bir komut dosyasındaki seçenekler ve dosya adları işlenir. Bununla birlikte, **`/link`** seçeneği komut dosyasında görünürse, satırdaki geri kalan tüm seçenekler bağlayıcıya geçirilir. Komut dosyasındaki sonraki satırlardaki seçenekler ve komut dosyası çağrısından sonra komut satırındaki seçenekler, hala derleyici seçenekleri olarak kabul edilir. Seçeneklerin sırasının yorumu nasıl etkilediği hakkında daha fazla bilgi için, bkz. [cl seçenekleri sırası](order-of-cl-options.md).

Bir komut dosyası CL komutunu içermemelidir. Her seçeneğin aynı satırda başlaması ve bitmesi gerekir; **`\`** iki satır arasında bir seçeneği birleştirmek için ters eğik çizgi () kullanamazsınız.

Bir komut dosyası, bir at işareti () tarafından **`@`** ve ardından bir dosya adı ile belirtilir. Dosya adı mutlak veya göreli bir yol belirtebilir.

Örneğin, aşağıdaki komut, yanıt adlı bir dosya içinde ise:

```cmd
/Ot /link LIBC.LIB
```

ve aşağıdaki CL komutunu belirtirsiniz:

```cmd
CL /Ob2 @RESP MYAPP.C
```

CL komutu aşağıdaki gibidir:

```cmd
CL /Ob2 /Ot MYAPP.C /link LIBC.LIB
```

Burada komut satırı ve komut dosyası komutlarının nasıl etkili bir şekilde birleştirildiğini görebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>
[MSVC derleyicisi seçenekleri](compiler-options.md)
