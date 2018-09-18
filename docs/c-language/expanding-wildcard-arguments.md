---
title: Joker karakter bağımsız değişkenlerini genişletme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d78b23f81b72d04e9299616b0273bc97bb7a4e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078159"
---
# <a name="expanding-wildcard-arguments"></a>Joker Karakter Bağımsız Değişkenlerini Genişletme

**Microsoft'a özgü**

C programını çalıştırdığınızda, iki joker karakter kullanabilirsiniz — soru işareti (?) ve yıldız işareti (*); dosya adı ve yol bağımsız değişkenlerini komut satırında belirtmek için.

Varsayılan olarak, joker karakterler komut satırı bağımsız değişkenlerinde genişletilmiş değil. Normal bir bağımsız değişken vektör değiştirebilirsiniz `argv` yükleme yordamı bir sürümle joker karakterler setargv.obj ya da wsetargv.obj dosyasıyla bağlayarak genişletin. Programınızı kullanıyorsa bir `main` setargv.obj bağlantıyla işlevi. Programınızı kullanıyorsa bir `wmain` wsetargv.obj bağlantıyla işlevi. Bunların her ikisi de eşdeğer davranışa sahip.

Setargv.obj veya wsetargv.obj bağlamak için kullanın **/link** seçeneği. Örneğin:

**cl example.c/Link setargv.obj**

Joker karakter, işletim sistemi komutları aynı şekilde genişletilir. (Joker karakter olarak alışkın değilseniz, işletim sistemi Kullanım Kılavuzu'na bakın.)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlantı Seçenekleri](../c-runtime-library/link-options.md)<br/>
[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)