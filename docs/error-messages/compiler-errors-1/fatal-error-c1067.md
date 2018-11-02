---
title: Önemli hata C1067
ms.date: 11/04/2016
f1_keywords:
- C1067
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
ms.openlocfilehash: f8fe301e25d9ecb5cc67397f9537e0bbd86c0627
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595630"
---
# <a name="fatal-error-c1067"></a>Önemli hata C1067

Derleyici sınırı: bir tür kaydının boyutu 64K sınırı aşıldı

Bir sembol 247 karakter aşan düzenlenmiş bir ada sahipse, bu hata oluşabilir.  Çözümlemek için sembol adını kısaltın.

Derleyici hata ayıklama bilgileri oluşturur, kaynak kodunda karşılaşılan türleri tanımlamak için tür kayıtları gösterir.  Örneğin, basit yapılar ve İşlevler bağımsız değişken listeleri türü kayıtları içerir.  Bu tür kayıtların bazıları büyük listeler olabilir.

Herhangi bir tür kaydının boyutuna 64K sınırı yoktur.  Bu 64 K sınırı aşılırsa, bu hata meydana gelir.

C1067, uzun adlara sahip fazla sembol veya bir sınıf, yapı veya birleşim çok fazla sayıda üye var. da meydana gelebilir.