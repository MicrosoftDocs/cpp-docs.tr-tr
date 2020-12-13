---
description: 'Daha fazla bilgi edinin: önemli hata C1067'
title: Önemli hata C1067
ms.date: 11/04/2016
f1_keywords:
- C1067
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
ms.openlocfilehash: ef50719740de99f85e7e94f99cf0e14531608b22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344425"
---
# <a name="fatal-error-c1067"></a>Önemli hata C1067

Derleyici sınırı: bir tür kaydının boyutuyla ilgili 64K sınırı aşıldı

Bu hata, bir sembol 247 karakterden daha fazla düzenlenmiş bir ada sahipse oluşabilir.  Çözümlemek için sembol adını kısaltın.

Derleyici hata ayıklama bilgilerini oluşturduğunda, kaynak kodunda karşılaşılan türleri tanımlamak için tür kayıtlarını yayar.  Örneğin, tür kayıtları, işlevlerin basit yapılarını ve bağımsız değişken listelerini içerir.  Bu tür kayıtlardan bazıları büyük listeler olabilir.

Herhangi bir tür kaydının boyutuyla ilgili 64K sınırı vardır.  Bu 64K sınırı aşılırsa, bu hata oluşur.

C1067, uzun adlara sahip çok sayıda sembol varsa veya bir sınıf, yapı ya da Union çok fazla üyeye sahipse da oluşabilir.
