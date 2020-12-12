---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1277'
title: Bağlayıcı Araçları Hatası LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 82a71878d30088bd018c4e54216d53228efe949d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193740"
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277

nesne kaydı PGD 'de bulunamadı (dosya adı)

[/LTCG: PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, Input. lib, def veya. obj dosyalarından birinin yolu,/LTCG: PGINSTRUMENT sırasında bulundukları yoldan farklıdır. Bu,/LTCG: PGıNSTRUMAFTER LIB ortam değişkeninde bir değişiklik tarafından açıklanabilir. Giriş dosyalarının tam yolu. pgd dosyasında depolanır.

/LTCG: PGOPTIMIZE, girişlerin/LTCG: PGıNSTRUMENT aşamasına özdeş olmasını gerektirir.

Bu uyarıyı çözmek için aşağıdakilerden birini yapın:

- /LTCG: PGıNSTRUMRUN, tüm test çalıştırmalarını Yinele ve/LTCG: PGOPTIMIZE ' i çalıştırın.

- LIB ortam değişkenini,/LTCG: PGıNSTRUMI çalıştırdığınızda olduğu gibi değiştirin.

/LTCG: PGUPDATE kullanarak LNK1277 'te geçici bir çözüm yapmanız önerilmez.
