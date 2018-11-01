---
title: Önemli hata C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: efd5b9dd5cdd7ee174bc786c38d9dd841e2ad6ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620017"
---
# <a name="fatal-error-c1509"></a>Önemli hata C1509

Derleyici sınırı: 'function' işlevinde çok fazla sayıda özel durum işleyicisi durumları. işlevi basitleştirin

Kod özel durum işleyicisi durumlar (32.768 durumları) bir iç sınırı aşıyor.

En yaygın nedeni işlevin sınıfın kullanıcı tanımlı değişkenler aritmetik işleçler ve karmaşık bir ifade içermesidir.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. İfadeler için geçici değişken ortak alt ifadeler atayarak basitleştirin.

1. İşlevi, daha küçük işlevlere bölün.