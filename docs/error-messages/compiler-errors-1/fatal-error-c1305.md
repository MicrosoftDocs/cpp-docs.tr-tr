---
title: Önemli hata C1305 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90d73003d9f19eb41f9eb34cd47c7b90b1e6164f
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466166"
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305
'pgd_file' profil veritabanı farklı bir mimari için olan  
  
 Başka bir platform geçildi için /LTCG:PGINSTRUMENT işlemi oluşturulmasına neden olan bir .pgd dosyası [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profil temelli iyileştirmeler](../../build/reference/profile-guided-optimizations.md) x86 ve x64 platformlar için kullanılabilir. Ancak, tek bir platform için bir /LTCG:PGINSTRUMENT işlemi ile oluşturulan bir .pgd dosyası geçersiz bir /LTCG:PGOPTIMIZE farklı bir platform için giriş olarak.  
  
 Bu hatayı gidermek için yalnızca /LTCG:PGINSTRUMENT /LTCG:PGOPTIMIZE bulunan aynı platform için oluşturulan bir .pgd dosyası geçirin.