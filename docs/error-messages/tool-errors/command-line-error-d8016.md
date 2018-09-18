---
title: Komut satırı hatası D8016 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8016
dev_langs:
- C++
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee16542b2f0cf9842e351813ed2e0b0d22cccaa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056995"
---
# <a name="command-line-error-d8016"></a>Komut Satırı Hatası D8016

'Seçenek1' ve 'Seçenek2' komut satırı seçenekleri uyumsuz

Komut satırı seçenekleri birlikte belirtilemez.

Gibi ortam değişkenlerini, CL, seçeneği belirtimleri için denetleyin.

**/ CLR** gelir **/eha**, ve diğer belirtemezsiniz **/EH** derleyici seçeneğiyle **/CLR**. Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

Visual C++ 6.0 proje güncelleştirdikten sonra D8016 alabilirsiniz: Proje Sihirbazı güncellemeyi sağlayabilir **/RTC** projedeki her kaynak kodu dosyası için kılan **/RTC** proje için ayarlama.  Çözümlemek için değiştirme **/RTC** her kaynak kodu dosyasında proje için varsayılan ayar olarak ayarlamak, yani proje ayarı **/RTC** her dosya için geçerli olur.

Bkz: [/RTC (çalışma zamanı hata denetimleri)](../../build/reference/rtc-run-time-error-checks.md) değiştirme hakkında bilgi için **/RTC** özellik ayarı.