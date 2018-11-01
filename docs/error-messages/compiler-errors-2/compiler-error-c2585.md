---
title: Derleyici Hatası C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 812ab15aacd1f6a215c6a5beb7781983859fe858
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593264"
---
# <a name="compiler-error-c2585"></a>Derleyici Hatası C2585

'type ' açık dönüştürme belirsiz

Tür dönüştürme, birden fazla sonuç üretebilir.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Birden çok devralma göre bir sınıf veya yapı türü dönüştürme. Dönüştürme işlevi veya işleç türü aynı temel sınıfın birden çok kez devralınırsa, kapsam çözümleme kullanmalısınız (`::`) Dönüştürmedeki devralınan sınıflar belirtmek için.

1. Bir dönüştürme operatörünün ve bir oluşturucu aynı dönüştürme yapma tanımlanmadı.