---
description: 'Daha fazla bilgi edinin: önemli hata C1382'
title: Önemli hata C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: fd2b9f48030d558a880a787114848dd0551b68ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276523"
---
# <a name="fatal-error-c1382"></a>Önemli hata C1382

' obj ' oluşturulduktan sonra ' dosya ' PCH dosyası yeniden oluşturuldu. Lütfen bu nesneyi yeniden derleyin

[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, derleyici onu işaret eden bir CIL. obj öğesinden daha yeni bir. pch dosyası algıladı. CıL. obj dosyasındaki bilgiler güncel değil. Nesneyi yeniden derleyin.

C1382, **/Rivc** ile derlerseniz ve ayrıca birden çok kaynak kod dosyasını derleyiciye geçirirseniz de oluşabilir.  Çözümlemek için, birden çok kaynak kodu dosyasını derleyiciye geçirirken **/Yıc** kullanmayın.  Daha fazla bilgi için bkz. [/Rivc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).
