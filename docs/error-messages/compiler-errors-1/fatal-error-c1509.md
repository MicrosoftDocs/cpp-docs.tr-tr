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
ms.openlocfilehash: fec83f6b6138eacc613e560b9da4557079d6677d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198800"
---
# <a name="fatal-error-c1509"></a>Önemli hata C1509
Derleyici sınırı: çok fazla özel durum işleyici durumları işlevinde 'function'. basitleştirmek işlevi  
  
 Kodu özel durum işleyici durumlar (32.768 durumları) bir iç sınırı aşıyor.  
  
 En yaygın nedeni işlevi, kullanıcı tanımlı sınıfı değişkenler aritmetik işleçler ve karmaşık bir ifade içeriyor olabilir.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  İfadeler geçici değişkenlere ortak alt ifadelerin atayarak basitleştirin.  
  
2.  Daha küçük işlevlerini split işlevi.