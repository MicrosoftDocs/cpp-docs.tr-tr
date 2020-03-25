---
title: Derleyici hatası C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 57a0cd7a200c5bbb875821eb9e10314d98e58185
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177397"
---
# <a name="compiler-error-c2585"></a>Derleyici hatası C2585

' Type ' öğesine açık dönüştürme belirsiz

Tür dönüştürme birden fazla sonuç verebilir.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Birden çok devralmaya göre bir sınıf veya yapı türünden dönüştürme. Tür, aynı temel sınıfı birden çok kez devralırsa, dönüştürme işlevinin veya işlecinin, devralınan sınıfların hangisinin dönüştürmesinde kullanılacağını belirtmek için kapsam çözümlemesi (`::`) kullanması gerekir.

1. Aynı dönüştürme yapılarak bir dönüştürme işleci ve bir Oluşturucu tanımlandı.
