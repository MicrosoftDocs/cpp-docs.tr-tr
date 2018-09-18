---
title: Önemli hata C1382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a5a6ce312c5ef886ef25e8de46e6d3376eded2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030663"
---
# <a name="fatal-error-c1382"></a>Önemli hata C1382

'obj' oluşturulmasının üzerinden PCH dosya 'dosyası yeniden oluşturuldu. Lütfen bu nesneyi yeniden oluşturun

Kullanırken [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), derleyici gösteren bir CIL .obj daha yeni bir .pch dosyası algılandı. CIL'i .obj dosyasındaki bilgiler güncel değil. Bir nesneyi yeniden oluşturun.

C1382 ile derleme yaparsanız da gerçekleşebilir **/Yc**, ancak ayrıca birden çok kaynak kod dosyaları için derleyici geçirin.  Çözümlemek için kullanmayın **/Yc** birden çok kaynak kodu dosyaları için derleyici geçerken.  Daha fazla bilgi için [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).