---
title: Joker Karakter Bağımsız Değişkenlerini Genişletme
ms.date: 11/04/2016
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
ms.openlocfilehash: f1fb964fe98223fb7187b83c7101027ed1f9cbea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233823"
---
# <a name="expanding-wildcard-arguments"></a>Joker Karakter Bağımsız Değişkenlerini Genişletme

**Microsoft'a özgü**

C programını çalıştırdığınızda, iki joker karakter kullanabilirsiniz — soru işareti (?) ve yıldız işareti (*); dosya adı ve yol bağımsız değişkenlerini komut satırında belirtmek için.

Varsayılan olarak, joker karakterler komut satırı bağımsız değişkenlerinde genişletilmiş değil. Normal bir bağımsız değişken vektör değiştirebilirsiniz `argv` yükleme yordamı bir sürümle joker karakterler setargv.obj ya da wsetargv.obj dosyasıyla bağlayarak genişletin. Programınızı kullanıyorsa bir `main` setargv.obj bağlantıyla işlevi. Programınızı kullanıyorsa bir `wmain` wsetargv.obj bağlantıyla işlevi. Bunların her ikisi de eşdeğer davranışa sahip.

Setargv.obj veya wsetargv.obj bağlamak için kullanın **/link** seçeneği. Örneğin:

**cl example.c/Link setargv.obj**

Joker karakter, işletim sistemi komutları aynı şekilde genişletilir. (Joker karakter olarak alışkın değilseniz, işletim sistemi Kullanım Kılavuzu'na bakın.)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı Seçenekleri](../c-runtime-library/link-options.md)<br/>
[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
