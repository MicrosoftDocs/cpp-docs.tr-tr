---
description: 'Hakkında daha fazla bilgi edinin: Command-Line Warning D9025'
title: Komut Satırı Uyarısı D9025
ms.date: 11/04/2016
f1_keywords:
- D9025
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
ms.openlocfilehash: 8cec7bdb5f3816c33d395e8ae93a861a29e94c64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115501"
---
# <a name="command-line-warning-d9025"></a>Komut Satırı Uyarısı D9025

' Seçenek1 ', ' Seçenek2 ' ile geçersiz kılınıyor

*Seçenek1* seçeneği belirtildi, ancak daha sonra *Seçenek2* tarafından geçersiz kılındı. *Seçenek2* seçeneği kullanıldı.

İki seçenek çelişkili veya uyumsuz yönergeler belirtiyorsa, komut satırında en sağdaki seçenekte belirtilen veya belirtilen yönerge kullanılır.

Geliştirme ortamından derlerken bu uyarıyı alırsanız ve çakışan seçeneklerin nereden geldiği konusunda emin değilseniz, aşağıdakileri göz önünde bulundurun:

- Bir seçenek, kodda ya da projenin proje ayarlarında belirtilebilir. Derleyicinin [komut satırı özellik sayfalarına](../../build/reference/command-line-property-pages.md) baktığınızda ve **tüm seçenekler** alanında çakışan seçenekleri görürseniz, seçenekler projenin özellik sayfalarında ayarlanır, aksi takdirde Seçenekler kaynak kodunda ayarlanır.

   Seçenekler projenin özellik sayfalarında ayarlandıysa, derleyicinin Önişlemci Özellik sayfasına bakın (Çözüm Gezgini proje düğümü seçili olarak).  Burada set seçeneğini görmüyorsanız, bu dosyanın bulunmadığından emin olmak için her kaynak kodu dosyası için Önişlemci Özellik sayfası ayarlarını (Çözüm Gezgini) denetleyin.

   Seçenekler kodda ayarlandıysa, kodda veya Windows üst bilgilerinde ayarlanabilir.  Önceden işlenmiş bir dosya ([/p](../../build/reference/p-preprocess-to-a-file.md)) oluşturmayı ve bunu simge için aramayı deneyebilirsiniz.
