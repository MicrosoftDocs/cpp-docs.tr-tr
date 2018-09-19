---
title: Önemli hata C1509 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 837ab5b7cf76b724726c6c52fbfe974d4da6ca85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033140"
---
# <a name="fatal-error-c1509"></a>Önemli hata C1509

Derleyici sınırı: 'function' işlevinde çok fazla sayıda özel durum işleyicisi durumları. işlevi basitleştirin

Kod özel durum işleyicisi durumlar (32.768 durumları) bir iç sınırı aşıyor.

En yaygın nedeni işlevin sınıfın kullanıcı tanımlı değişkenler aritmetik işleçler ve karmaşık bir ifade içermesidir.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. İfadeler için geçici değişken ortak alt ifadeler atayarak basitleştirin.

1. İşlevi, daha küçük işlevlere bölün.