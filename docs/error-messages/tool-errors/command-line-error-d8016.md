---
description: 'Hakkında daha fazla bilgi edinin: Command-Line Error D8016'
title: Komut Satırı Hatası D8016
ms.date: 11/04/2016
f1_keywords:
- D8016
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
ms.openlocfilehash: 2f340cb7574177536310343dc9761058b7b9bc08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115722"
---
# <a name="command-line-error-d8016"></a>Komut Satırı Hatası D8016

' Seçenek1 ' ve ' Seçenek2 ' komut satırı seçenekleri uyumsuz

Komut satırı seçenekleri birlikte belirtilemez.

Seçenek belirtimleri için CL gibi ortam değişkenlerini denetleyin.

**/clr** , **/EHa** anlamına gelir ve **/clr** ile başka bir **/Eh** derleyici seçeneği belirtemezsiniz. Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

Visual C++ 6,0 projesi güncelleştirildikten sonra D8016 alabilirsiniz: Proje Güncelleştirme Sihirbazı işlemi, projedeki her kaynak kodu dosyası için **/RTC** 'yi etkinleştirebilir ve bu da projenin **/RTC** ayarını geçersiz kılar.  Bu sorunu çözmek için, projedeki her bir kaynak kodu dosyası için **/RTC** ayarını varsayılan ayara değiştirin, yani **/RTC** için proje ayarı her dosya için geçerli olacaktır.

**/RTC** özellik ayarını değiştirme hakkında bilgi için bkz. [/RTC (çalışma zamanı hata denetimleri)](../../build/reference/rtc-run-time-error-checks.md) .
