---
title: Bağlayıcı araçları hatası LNK1277 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1277
dev_langs:
- C++
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 542c48bd23b3f84ab301404987c77d964f51823e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082546"
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277

Nesne kaydı pgd'de (dosya adı) bulunamadı

Kullanırken [/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md), giriş .lib, def veya .obj dosyaları birinin yolu, bunlar bulundu /LTCG:PGINSTRUMENT sırasında yolundan farklı. Bu değişikliği LIB ortam değişkeni sonra /LTCG:PGINSTRUMENT açıklanması. Giriş dosyalarının tam yolunu .pgd dosyasında depolanır.

/LTCG:PGOPTIMIZE girişleri /LTCG:PGINSTRUMENT aşaması için aynı olmasını gerektirir.

Bu uyarıyı çözmek için şunlardan birini yapın:

- /LTCG:PGINSTRUMENT çalıştırın, tüm test çalışmalarını Yinele ve /LTCG:PGOPTIMIZE çalıştırın.

- LIB ortam değişkeni /LTCG:PGINSTRUMENT çalıştırdığınızda neler olduğu için değiştirin.

Geçici bir çözüm LNK1277 /LTCG:PGUPDATE kullanarak iş önerilmez.