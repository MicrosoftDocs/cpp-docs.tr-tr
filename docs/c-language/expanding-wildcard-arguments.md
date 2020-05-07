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

**Microsoft'a Özgü**

C programını çalıştırdığınızda, komut satırında dosya adı ve yol bağımsız değişkenlerini belirtmek için iki joker karakter (soru işareti (?) ve yıldız işareti (*)) kullanabilirsiniz.

Varsayılan olarak, komut satırı bağımsız değişkenlerinde joker karakterler genişletilmez. Normal bağımsız değişken vektör `argv` yükleme yordamını, Setargv. obj veya Wsetargv. obj dosyasıyla bağlantı kurarak joker karakterleri genişletmenizi sağlayan bir sürümle değiştirebilirsiniz. Programınız bir `main` işlev kullanıyorsa, Setargv. obj ile bağlayın. Programınız bir `wmain` işlev kullanıyorsa, Wsetargv. obj ile bağlayın. Bunların her ikisi de eşdeğer davranışa sahiptir.

Setargv. obj veya Wsetargv. obj ile bağlantı için, **/Link** seçeneğini kullanın. Örneğin:

**CL example. c/link Setargv. obj**

Joker karakterler, işletim sistemi komutlarıyla aynı şekilde genişletilir. (Joker karakterler hakkında bilginiz yoksa, işletim sistemi Kullanıcı Kılavuzumuza bakın.)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı Seçenekleri](../c-runtime-library/link-options.md)<br/>
[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
