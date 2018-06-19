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
ms.openlocfilehash: 3cb1cf19d0fc4152fbb458d684972bb5a4418f37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227153"
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305
Profil 'pgd_file' için farklı bir mimari veritabanıdır  
  
 Başka bir platform geçirilmedi için /LTCG:PGINSTRUMENT işlemi oluşturulan bir .pgd dosya [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profil temelli iyileştirmeler](../../build/reference/profile-guided-optimizations.md) x86 için kullanılabilir ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] platformlar. Ancak, bir platform için bir /LTCG:PGINSTRUMENT işlemi ile oluşturulan bir .pgd dosyası geçerli değil /LTCG:PGOPTIMIZE farklı bir platform için giriş olarak.  
  
 Bu hatayı gidermek için yalnızca aynı platformunda /LTCG:PGOPTIMIZE /LTCG:PGINSTRUMENT ile oluşturulan bir .pgd dosyası geçirin.