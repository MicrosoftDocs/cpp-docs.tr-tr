---
title: Joker karakter bağımsız değişkenlerini genişletme
description: Programlarınızda joker karakter komut satırı bağımsız değişkenlerini işlemek için bağlayıcı seçeneği kullanma.
ms.date: 11/20/2020
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.openlocfilehash: b847a5dd8af577a4e30edcd9bc7fc34add296c17
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483314"
---
# <a name="expanding-wildcard-arguments"></a>Joker karakter bağımsız değişkenlerini genişletme

Joker karakter bağımsız değişkeni genişletmesi Microsoft 'a özgüdür.

C programını çalıştırdığınızda, **`?`** **`*`** komut satırında dosya adı ve yol bağımsız değişkenlerini belirtmek için iki joker karakter, soru işareti () ve yıldız işareti () kullanabilirsiniz.

Varsayılan olarak, komut satırı bağımsız değişkenlerinde joker karakterler genişletilmez. Normal bağımsız değişken vektör `argv` yükleme yordamını, veya dosyasıyla bağlantı kurarak joker karakterleri genişleterek bir sürümle değiştirebilirsiniz *`setargv.obj`* *`wsetargv.obj`* . Programınız bir `main` işlev kullanıyorsa, ile bağlantısını yapın *`setargv.obj`* . Programınız bir `wmain` işlev kullanıyorsa, ile bağlantısını yapın *`wsetargv.obj`* . Bunların her ikisi de eşdeğer davranışa sahiptir. 

Veya ile bağlantı yapmak için *`setargv.obj`* *`wsetargv.obj`* seçeneğini kullanın **`/link`** . Örnek:

**`cl example.c /link setargv.obj`**

Joker karakterler, işletim sistemi komutlarıyla aynı şekilde genişletilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı seçenekleri](../c-runtime-library/link-options.md)\
[`main` işlev ve program yürütme](../c-language/main-function-and-program-execution.md)
