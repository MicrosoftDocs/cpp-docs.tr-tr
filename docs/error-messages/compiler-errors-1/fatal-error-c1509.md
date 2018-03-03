---
title: "Önemli hata C1509 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22cb22ea2186b16fd98d2714779b2475c51d15bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1509"></a>Önemli hata C1509
Derleyici sınırı: çok fazla özel durum işleyici durumları işlevinde 'function'. basitleştirmek işlevi  
  
 Kodu özel durum işleyici durumlar (32.768 durumları) bir iç sınırı aşıyor.  
  
 En yaygın nedeni işlevi, kullanıcı tanımlı sınıfı değişkenler aritmetik işleçler ve karmaşık bir ifade içeriyor olabilir.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  İfadeler geçici değişkenlere ortak alt ifadelerin atayarak basitleştirin.  
  
2.  Daha küçük işlevlerini split işlevi.