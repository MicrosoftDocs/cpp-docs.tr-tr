---
title: C komut satırı işlemini özelleştirme
description: '`main`Çalışma zamanı başlangıç kodunda işlev bağımsız değişkenini ve ortam parametresi işlemeyi gizleme.'
ms.date: 11/19/2020
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
ms.openlocfilehash: fc306172491cd401caeecb3c87c0711f8b4ef911
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483301"
---
# <a name="customizing-c-command-line-processing"></a>C komut satırı işlemini özelleştirme

Programınız komut satırı bağımsız değişkenleri içermiyorsa, az miktarda alan kaydetmek için komut satırı işleme yordamını gizleyebilirsiniz. Kullanımını bastırmak için, *`noarg.obj`* `main` `wmain` **`/link`** derleyici seçeneklerinizde veya **`LINK`** komut satırlarınızın dosyasını (hem hem de için) dahil edin.

Benzer şekilde, ortam tablosuna hiçbir daha bağımsız değişken aracılığıyla erişemiyorsanız *`envp`* , iç ortam işleme yordamını gizleyebilirsiniz. Kullanımını bastırmak için, *`noenv.obj`* `main` `wmain` **`/link`** derleyici seçeneklerinizde veya **`LINK`** komut satırlarınızın dosyasını (hem hem de için) dahil edin.

Çalışma zamanı başlatma bağlayıcı seçenekleri hakkında daha fazla bilgi için bkz. [bağlantı seçenekleri](../c-runtime-library/link-options.md).

Programınız, `spawn` `exec` C çalışma zamanı kitaplığı 'nda veya yordam ailesine çağrı yapabilir. Varsa, bir ortamı üst işlemden alt işleme geçirmek için kullanıldığından, ortam işleme yordamını gizmemelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[`main` işlev ve program yürütme](../c-language/main-function-and-program-execution.md)\
[Bağlantı seçenekleri](../c-runtime-library/link-options.md).
