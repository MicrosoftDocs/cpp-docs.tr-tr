---
title: Bağlayıcı Araçları Hatası LNK1277
ms.date: 11/04/2016
f1_keywords:
- LNK1277
helpviewer_keywords:
- LNK1277
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
ms.openlocfilehash: 7c00fb32e4b36eff119195efbb34d536d80df6a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183663"
---
# <a name="linker-tools-error-lnk1277"></a>Bağlayıcı Araçları Hatası LNK1277

nesne kaydı PGD 'de bulunamadı (dosya adı)

[/LTCG: PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, Input. lib, def veya. obj dosyalarından birinin yolu,/LTCG: PGINSTRUMENT sırasında bulundukları yoldan farklıdır. Bu,/LTCG: PGıNSTRUMAFTER LIB ortam değişkeninde bir değişiklik tarafından açıklanabilir. Giriş dosyalarının tam yolu. pgd dosyasında depolanır.

/LTCG: PGOPTIMIZE, girişlerin/LTCG: PGıNSTRUMENT aşamasına özdeş olmasını gerektirir.

Bu uyarıyı çözmek için aşağıdakilerden birini yapın:

- /LTCG: PGıNSTRUMRUN, tüm test çalıştırmalarını Yinele ve/LTCG: PGOPTIMIZE ' i çalıştırın.

- LIB ortam değişkenini,/LTCG: PGıNSTRUMI çalıştırdığınızda olduğu gibi değiştirin.

/LTCG: PGUPDATE kullanarak LNK1277 'te geçici bir çözüm yapmanız önerilmez.
