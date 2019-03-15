---
title: Önemli hata C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 988842a0d5e8002ffd1478a2e10a8c88ee971911
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822242"
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305

'pgd_file' profil veritabanı farklı bir mimari için olan

Başka bir platform geçildi için /LTCG:PGINSTRUMENT işlemi oluşturulmasına neden olan bir .pgd dosyası [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profil temelli iyileştirmeler](../../build/profile-guided-optimizations.md) x86 ve x64 platformlar için kullanılabilir. Ancak, tek bir platform için bir /LTCG:PGINSTRUMENT işlemi ile oluşturulan bir .pgd dosyası geçersiz bir /LTCG:PGOPTIMIZE farklı bir platform için giriş olarak.

Bu hatayı gidermek için yalnızca /LTCG:PGINSTRUMENT /LTCG:PGOPTIMIZE bulunan aynı platform için oluşturulan bir .pgd dosyası geçirin.