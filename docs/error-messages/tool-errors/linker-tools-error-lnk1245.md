---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1245'
title: Bağlayıcı Araçları Hatası LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 3903651992f8fb79c3a79e4f2afc9d84e70e8126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193909"
---
# <a name="linker-tools-error-lnk1245"></a>Bağlayıcı Araçları Hatası LNK1245

geçersiz ' alt sistem ' alt sistemi belirtildi; /SUBSYSTEM WINDOWS, WINDOWSCE veya CONSOLE olmalıdır

[/clr](../../build/reference/clr-common-language-runtime-compilation.md) nesnesini derlemek için kullanıldı ve şu koşullardan biri doğru:

- Özel bir giriş noktası tanımlandı ([/Entry](../../build/reference/entry-entry-point-symbol.md)), bu şekilde bağlayıcı bir alt sistemi çıkarmıyor.

- [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) bağlayıcı seçeneğine/clr nesneleri için geçerli olmayan bir değer geçirildi.

Her iki durumda da çözüm,/SUBSYSTEM bağlayıcı seçeneğinde geçerli bir değer belirtmektir.
