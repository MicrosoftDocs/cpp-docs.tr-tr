---
title: Derleyici Hatası C2585 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ec7b1e9c1e5e7894740cc80f9c030fa1ee26ec0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028850"
---
# <a name="compiler-error-c2585"></a>Derleyici Hatası C2585

'type ' açık dönüştürme belirsiz

Tür dönüştürme, birden fazla sonuç üretebilir.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Birden çok devralma göre bir sınıf veya yapı türü dönüştürme. Dönüştürme işlevi veya işleç türü aynı temel sınıfın birden çok kez devralınırsa, kapsam çözümleme kullanmalısınız (`::`) Dönüştürmedeki devralınan sınıflar belirtmek için.

1. Bir dönüştürme operatörünün ve bir oluşturucu aynı dönüştürme yapma tanımlanmadı.