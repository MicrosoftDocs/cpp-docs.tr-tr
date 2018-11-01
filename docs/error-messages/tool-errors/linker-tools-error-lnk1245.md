---
title: Bağlayıcı Araçları Hatası LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 4cf9a6c4356872b727a10a360396e51e38928b29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505488"
---
# <a name="linker-tools-error-lnk1245"></a>Bağlayıcı Araçları Hatası LNK1245

Geçersiz 'alt sistem belirtilmedi;' alt sistemi / SUBSYSTEM WINDOWS, WINDOWSCE veya KONSOL olmalıdır

[/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) nesne derlemek için kullanılan ve aşağıdaki koşullar doğru:

- Özel giriş noktası tanımlanmış ([/Entry](../../build/reference/entry-entry-point-symbol.md)), yani bir subsystem bağlayıcı çıkarılamadı.

- Bir değer geçildi [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) bağlayıcı seçeneği, / CLR nesneler için geçerli değil.

Her iki durum için çözüm/Subsystem bağlayıcı seçeneği için geçerli bir değer belirtmek içindir.