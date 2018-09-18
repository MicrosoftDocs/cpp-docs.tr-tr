---
title: Önemli hata C1128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1128
dev_langs:
- C++
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a0b0c308811b642e0064304cab0688215ac949a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079654"
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