---
title: Önemli hata C1128
ms.date: 11/04/2016
f1_keywords:
- C1128
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
ms.openlocfilehash: bb1d9af10084d6b3e75325450c7f13ea1683ee2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661233"
---
# <a name="fatal-error-c1128"></a>Önemli hata C1128

bölüm sayısı nesne dosyası biçimi sınırını aştı: / bigobj ile derleyin

Bir .obj dosyası izin verilen bölüm, bir COFF nesne dosyası biçimi sınırlama sayısı aşıldı.

Bu bölümde sınırlama ulaşmasını kullanmanın sonucu olabilir [/Gy](../../build/reference/gy-enable-function-level-linking.md) ve hata ayıklama derlemesi; **/Gy** işlevleri kendi COMDAT bölüme gitmek neden olur. Hata ayıklama yapısında, hata ayıklama bilgisi bölümünde her COMDAT işlevi yoktur.

Çok fazla satır içi işlevleri olduğunda C1128 de neden olabilir.

Bu hatayı düzeltmek için kaynak dosyanızı çoklu kaynak kodu dosyalarına bölmek, olmadan derleme **/Gy**, ya da derleme  [ /bigobj (bölüm sayısını arttırma içinde. Obj dosyası)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  İle derlenmiyor varsa **/Gy**, en iyi duruma getirme ayrı ayrı belirtmeniz gerekecektir beri **/O2** ve **/O1** hem de kapsıyor **/Gy**.

Mümkünse, hata ayıklama bilgileri olmadan derleyin.

Ayrı kaynak kodu dosyalarını belirli şablonları örneklemeleri olan gerekebilir yerine derleyici sahip, yayma bunları.

Kod taşırken C1128 büyük olasılıkla ilk x64 kullanılırken görünür derleyici ve daha sonra çok x86 ile derleyici. x64 derlenen her bir işlev ile ilişkili en az 4 bölüme sahip olacak **/Gy** veya satır içine alınmış şablonları veya satır içi sınıfı: pdata, kodu ve hata ayıklama bilgisi ve büyük olasılıkla xdata.  X86 pdata olmaz.