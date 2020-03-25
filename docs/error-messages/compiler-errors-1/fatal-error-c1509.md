---
title: Önemli hata C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: 0d1d7255dd64239a6a76bb15a1f309b43eac0d4b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202962"
---
# <a name="fatal-error-c1509"></a>Önemli hata C1509

Derleyici sınırı: ' function ' işlevinde çok fazla özel durum işleyici durumu. basitleşme işlevi

Kod, özel durum işleyici durumlarındaki bir iç sınırı (32.768 durum) aşıyor.

En yaygın neden, işlevin Kullanıcı tanımlı sınıf değişkenlerinin ve aritmetik işleçlerin karmaşık bir ifadesini içermesi olabilir.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Geçici değişkenlere ortak alt ifadeler atayarak ifadeleri kolaylaştırın.

1. İşlevi daha küçük işlevlere Böl.
