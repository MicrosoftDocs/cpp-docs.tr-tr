---
description: 'Daha fazla bilgi edinin: önemli hata C1084'
title: Önemli hata C1084
ms.date: 11/04/2016
f1_keywords:
- C1084
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
ms.openlocfilehash: 6a3221bb894c0b320642a923d9552a207a2ff9ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145320"
---
# <a name="fatal-error-c1084"></a>Önemli hata C1084

Dosya türü okunamıyor: ' dosya ': ileti

Bu hata genellikle derleyici tarafından yapılan başarısız iç sistem API çağrısının sonucudur. Bu hatayla karşılaşıldığında gösterilen ileti genellikle [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) veya [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage)tarafından oluşturulur.

Aşağıdaki adımların gerçekleştirilmesi C1084 çözümleme konusunda yardımcı olabilir:

- Belirtilen dosyanın var olduğundan emin olun.

- Belirtilen dosyaya erişmek için uygun izinlerin ayarlandığından emin olun.

- Komut satırı sözdiziminin [derleyici Command-Line sözdizimi](../../build/reference/compiler-command-line-syntax.md)altında özetlenen kurallara uyduğundan emin olun.

- **Tmp** ve **Temp** ortam değişkenlerinin doğru ayarlandığından ve bu ortam değişkenlerinin başvurduğu dizinlere erişmek için uygun izinlerin olduğundan emin olun. Ayrıca, **tmp** ve **Temp** ortam değişkenlerinin başvurduğu sürücülerin yeterli miktarda boş alan içerdiğinden emin olun.

- İleti "hatalı dosya numarası" ise, arka planda derlenirken belirtilen dosya ön planda kapanıyor olabilir.

Yukarıdaki tanılamayı gerçekleştirdikten sonra temiz bir derleme gerçekleştirin.
