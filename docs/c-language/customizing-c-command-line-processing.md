---
title: C Komut Satırı İşlemini Özelleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
ms.openlocfilehash: 9f7bc78c20aee4b91bf00fefd2615ba1a6611010
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623606"
---
# <a name="customizing-c-command-line-processing"></a>C Komut Satırı İşlemini Özelleştirme

Programınızı komut satırı bağımsız değişkenlerini almaz, komut satırı işlemeyi gerçekleştiren yordamı kullanımını gizleme tarafından az miktarda alan kaydedebilirsiniz. Bu yordamı çağrılır **_setargv** (veya **_wsetargv** geniş karakter ortamında) anlatılan şekilde [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md). Kullanımını engellemek için dosya içeren bir şey yapan bir yordam tanımlamak **ana** işlev ve adlandırın **_setargv** (veya **_wsetargv** geniş karakter ortam). Çağrı **_setargv** veya **_wsetargv** ardından tanımınızı tarafından sağlanıyorsa **_setargv** veya **_wsetargv** , ve kitaplık sürümü yüklü değil.

Benzer şekilde, hiçbir zaman ortam tablosuna aracılığıyla erişiyorsanız `envp` bağımsız değişken yerine kullanılacak boş kendi yordamınızı sağlayabilir **_setenvp** (veya **_wsetenvp**), ortam işleme yordamı.

Programınız için çağrılar yaparsa **_spawn** veya **_exec** C Çalışma Zamanı Kitaplığı'ndaki yordamlara ailesi, size değil bastırmak ortam işleme yordamı geçirmek için bu yordamı kullanıldığından bir Yeni işlem ortamı spawning işlemi.

## <a name="see-also"></a>Ayrıca Bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)