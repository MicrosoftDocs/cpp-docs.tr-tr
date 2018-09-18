---
title: Önemli hata C1067 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1067
dev_langs:
- C++
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f267e58617fbc68835fd3a387c4b635de4fd0530
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077678"
---
# <a name="fatal-error-c1067"></a>Önemli hata C1067

Derleyici sınırı: bir tür kaydının boyutu 64K sınırı aşıldı

Bir sembol 247 karakter aşan düzenlenmiş bir ada sahipse, bu hata oluşabilir.  Çözümlemek için sembol adını kısaltın.

Derleyici hata ayıklama bilgileri oluşturur, kaynak kodunda karşılaşılan türleri tanımlamak için tür kayıtları gösterir.  Örneğin, basit yapılar ve İşlevler bağımsız değişken listeleri türü kayıtları içerir.  Bu tür kayıtların bazıları büyük listeler olabilir.

Herhangi bir tür kaydının boyutuna 64K sınırı yoktur.  Bu 64 K sınırı aşılırsa, bu hata meydana gelir.

C1067, uzun adlara sahip fazla sembol veya bir sınıf, yapı veya birleşim çok fazla sayıda üye var. da meydana gelebilir.