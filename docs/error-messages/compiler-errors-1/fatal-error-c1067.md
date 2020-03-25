---
title: Önemli hata C1067
ms.date: 11/04/2016
f1_keywords:
- C1067
helpviewer_keywords:
- C1067
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
ms.openlocfilehash: 3b016790220d409435ff7ea53c6f48899a9e8f1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204353"
---
# <a name="fatal-error-c1067"></a>Önemli hata C1067

Derleyici sınırı: bir tür kaydının boyutuyla ilgili 64K sınırı aşıldı

Bu hata, bir sembol 247 karakterden daha fazla düzenlenmiş bir ada sahipse oluşabilir.  Çözümlemek için sembol adını kısaltın.

Derleyici hata ayıklama bilgilerini oluşturduğunda, kaynak kodunda karşılaşılan türleri tanımlamak için tür kayıtlarını yayar.  Örneğin, tür kayıtları, işlevlerin basit yapılarını ve bağımsız değişken listelerini içerir.  Bu tür kayıtlardan bazıları büyük listeler olabilir.

Herhangi bir tür kaydının boyutuyla ilgili 64K sınırı vardır.  Bu 64K sınırı aşılırsa, bu hata oluşur.

C1067, uzun adlara sahip çok sayıda sembol varsa veya bir sınıf, yapı ya da Union çok fazla üyeye sahipse da oluşabilir.
