---
title: Komut Satırı Uyarısı D9025
ms.date: 11/04/2016
f1_keywords:
- D9025
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
ms.openlocfilehash: e7090dda72868ad7ee4d5f8e4f1ba6a0ad121c98
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822476"
---
# <a name="command-line-warning-d9025"></a>Komut Satırı Uyarısı D9025

'Seçenek2' ile ' Seçenek1' geçersiz kılma

*Seçenek1* seçeneği belirtildi ancak ardından tarafından geçersiz kılınmıştır *Seçenek2*. *Seçenek2* seçeneği kullanıldı.

İki seçenek çelişkili ya da uyumsuz yönergeleri belirtirseniz, belirtilen veya komut satırında sağa görselinin seçeneğinde kapsanan yönergesi kullanılır.

Bu uyarı geliştirme ortamından derlenirken alın ve gelen çakışan seçenekler nereden geldiğini emin değilseniz, aşağıdakileri göz önünde bulundurun:

- Bir seçenek, kod veya projenin proje ayarlarında belirtilebilir. Derleyicinin bakarsanız [komut satırı özellik sayfaları](../../build/reference/command-line-property-pages.md) ve çakışan seçenekleri görürseniz **tüm seçenekleri** seçenekleri, projenin özellik sayfalarında, aksi takdirde seçenekleri ayarlanmıştır alan kaynak kodunda ayarlanır.

   Seçenekler projenin özellik sayfalarındaki ayarlarsanız, derleyicinin önişlemci özellik sayfasında (Çözüm Gezgini'nde Seçili proje düğümü) arayın.  Burada ayarlayın, emin olmak için her kaynak kodu dosyası (Çözüm Gezgini'nde) önişlemci özellik sayfası ayarları denetle seçeneğini görmüyorsanız var. eklenmez.

   Seçenekler, kod içinde ayarlarsanız kodda veya windows üstbilgileri ayarlayabilirsiniz.  Önceden işlenmiş dosya oluşturma deneyebilirsiniz ([/P](../../build/reference/p-preprocess-to-a-file.md)) ve sembolü aratın.