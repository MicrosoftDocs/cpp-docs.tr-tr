---
title: Komut satırı uyarısı D9025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9025
dev_langs:
- C++
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 822d1ac0cc1e6b3e728d43b816e7a0a15eee9958
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063703"
---
# <a name="command-line-warning-d9025"></a>Komut Satırı Uyarısı D9025

'Seçenek2' ile ' Seçenek1' geçersiz kılma

*Seçenek1* seçeneği belirtildi ancak ardından tarafından geçersiz kılınmıştır *Seçenek2*. *Seçenek2* seçeneği kullanıldı.

İki seçenek çelişkili ya da uyumsuz yönergeleri belirtirseniz, belirtilen veya komut satırında sağa görselinin seçeneğinde kapsanan yönergesi kullanılır.

Bu uyarı geliştirme ortamından derlenirken alın ve gelen çakışan seçenekler nereden geldiğini emin değilseniz, aşağıdakileri göz önünde bulundurun:

- Bir seçenek, kod veya projenin proje ayarlarında belirtilebilir. Derleyicinin bakarsanız [komut satırı özellik sayfaları](../../ide/command-line-property-pages.md) ve çakışan seçenekleri görürseniz **tüm seçenekleri** seçenekleri, projenin özellik sayfalarında, aksi takdirde seçenekleri ayarlanmıştır alan kaynak kodunda ayarlanır.

     Seçenekler projenin özellik sayfalarındaki ayarlarsanız, derleyicinin önişlemci özellik sayfasında (Çözüm Gezgini'nde Seçili proje düğümü) arayın.  Burada ayarlayın, emin olmak için her kaynak kodu dosyası (Çözüm Gezgini'nde) önişlemci özellik sayfası ayarları denetle seçeneğini görmüyorsanız var. eklenmez.

     Seçenekler, kod içinde ayarlarsanız kodda veya windows üstbilgileri ayarlayabilirsiniz.  Önceden işlenmiş dosya oluşturma deneyebilirsiniz ([/P](../../build/reference/p-preprocess-to-a-file.md)) ve sembolü aratın.