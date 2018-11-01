---
title: Bağlayıcı Araçları Hatası LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 137aa15dd9dad4b08d52af55da60a9cdf8b58055
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662078"
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277

Nesne kaydı pgd'de (dosya adı) bulunamadı

Kullanırken [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), giriş .lib, def veya .obj dosyaları birinin yolu, bunlar bulundu /LTCG:PGINSTRUMENT sırasında yolundan farklı. Bu değişikliği LIB ortam değişkeni sonra /LTCG:PGINSTRUMENT açıklanması. Giriş dosyalarının tam yolunu .pgd dosyasında depolanır.

/LTCG:PGOPTIMIZE girişleri /LTCG:PGINSTRUMENT aşaması için aynı olmasını gerektirir.

Bu uyarıyı çözmek için şunlardan birini yapın:

- /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın.

- LIB ortam değişkeni /LTCG:PGINSTRUMENT çalıştırdığınızda neler olduğu için değiştirin.

Geçici bir çözüm LNK1277 /LTCG:PGUPDATE kullanarak iş önerilmez.