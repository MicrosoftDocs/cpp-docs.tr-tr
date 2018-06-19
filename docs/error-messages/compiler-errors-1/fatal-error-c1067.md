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
ms.openlocfilehash: 89ac7084e92f7f2ed496a4c1572e94a4fa46862f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229098"
---
# <a name="fatal-error-c1067"></a>Önemli hata C1067
Derleyici sınırı: türü bir kayıtta boyutu 64K sınırı aşıldı  
  
 Bir simge 247 karakteri aşan bir düzenlenmiş adı varsa, bu hata oluşabilir.  Çözmek için sembol adını kısaltın.  
  
 Derleyici hata ayıklama bilgileri oluşturduğunda, kaynak kodunda karşılaşılan türlerini tanımlamak için tür kayıtları yayar.  Örneğin, türü kayıtları basit yapılar ve işlevlerin bağımsız değişken listeleri içerir.  Bu tür kayıtların bazıları büyük listeleri olabilir.  
  
 Herhangi bir tür kaydının boyutu 64K sınırı yoktur.  Bu 64 K sınır aşılırsa, bu hata meydana gelir.  
  
 C1067 uzun adları birçok sembolleriyle varsa veya bir sınıf, yapı ve birleşim çok fazla sayıda üye sahipse da oluşabilir.