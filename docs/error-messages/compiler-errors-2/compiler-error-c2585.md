---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2585'
title: Derleyici hatası C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 568e5db1ca160b9fd13596d4f94f646cb4cf0bdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177659"
---
# <a name="compiler-error-c2585"></a>Derleyici hatası C2585

' Type ' öğesine açık dönüştürme belirsiz

Tür dönüştürme birden fazla sonuç verebilir.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Birden çok devralmaya göre bir sınıf veya yapı türünden dönüştürme. Tür, aynı temel sınıfı birden çok kez devralırsa, dönüştürme işlevinin veya işlecinin, `::` devralınan sınıfların hangi dönüşümde kullanılacağını belirtmek için kapsam çözümlemesi () kullanması gerekir.

1. Aynı dönüştürme yapılarak bir dönüştürme işleci ve bir Oluşturucu tanımlandı.
