---
title: C++ Komut Satırı İşlemini Özelleştirme
ms.date: 11/04/2016
f1_keywords:
- _setenvp
- _setargv
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
ms.openlocfilehash: da1b3bdd6392b144f9315add4c19de14c1d14d41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582695"
---
# <a name="customizing-c-command-line-processing"></a>C++ Komut Satırı İşlemini Özelleştirme

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Programınızı komut satırı bağımsız değişkenlerini almaz, komut satırı işlemeyi gerçekleştiren yordamı kullanımını gizleme tarafından az miktarda alan kaydedebilirsiniz. Bu yordamı çağrılır `_setargv` ve açıklanan [joker karakter genişletmesi](../cpp/wildcard-expansion.md). Kullanımını engellemek için dosya içeren bir şey yapan bir yordam tanımlamak `main` işlev ve adlandırın `_setargv`. Çağrı `_setargv` ardından tanımınızı tarafından sağlanıyorsa `_setargv`, ve kitaplık sürümü yüklü değil.

Benzer şekilde, hiçbir zaman ortam tablosuna aracılığıyla erişiyorsanız `envp` bağımsız değişken yerine kullanılacak boş kendi yordamınızı sağlayabilir `_setenvp`, ortam işleme yordamı. Olduğu gibi `_setargv` işlevi `_setenvp` olarak bildirilmelidir **extern "C"**.

Programınızı çağrıları yapabileceğiniz `spawn` veya `exec` C Çalışma Zamanı Kitaplığı'ndaki yordamlara ailesi. Bu durumda, bu yordam bir ortam ana işlemden alt işleme geçmek için kullanıldığından, ortam işleme yordamı göndermeme değil.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)