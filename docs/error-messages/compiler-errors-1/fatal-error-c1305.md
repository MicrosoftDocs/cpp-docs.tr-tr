---
title: "Önemli hata C1305 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1305
dev_langs: C++
helpviewer_keywords: C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cf4a9025b8d441ae42b7de7605594fda60dc5603
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305
Profil 'pgd_file' için farklı bir mimari veritabanıdır  
  
 Başka bir platform geçirilmedi için /LTCG:PGINSTRUMENT işlemi oluşturulan bir .pgd dosya [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profil temelli iyileştirmeler](../../build/reference/profile-guided-optimizations.md) x86 için kullanılabilir ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] platformlar. Ancak, bir platform için bir /LTCG:PGINSTRUMENT işlemi ile oluşturulan bir .pgd dosyası geçerli değil /LTCG:PGOPTIMIZE farklı bir platform için giriş olarak.  
  
 Bu hatayı gidermek için yalnızca aynı platformunda /LTCG:PGOPTIMIZE /LTCG:PGINSTRUMENT ile oluşturulan bir .pgd dosyası geçirin.