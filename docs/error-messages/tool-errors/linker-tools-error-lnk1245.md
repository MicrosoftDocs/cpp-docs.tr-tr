---
title: Bağlayıcı Araçları Hatası LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 19e3f820b5bd7fdd8eac2f7b5a96fb5923ae0b92
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183806"
---
# <a name="linker-tools-error-lnk1245"></a>Bağlayıcı Araçları Hatası LNK1245

geçersiz ' alt sistem ' alt sistemi belirtildi; /SUBSYSTEM WINDOWS, WINDOWSCE veya CONSOLE olmalıdır

[/clr](../../build/reference/clr-common-language-runtime-compilation.md) nesnesini derlemek için kullanıldı ve şu koşullardan biri doğru:

- Özel bir giriş noktası tanımlandı ([/Entry](../../build/reference/entry-entry-point-symbol.md)), bu şekilde bağlayıcı bir alt sistemi çıkarmıyor.

- [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) bağlayıcı seçeneğine/clr nesneleri için geçerli olmayan bir değer geçirildi.

Her iki durumda da çözüm,/SUBSYSTEM bağlayıcı seçeneğinde geçerli bir değer belirtmektir.
