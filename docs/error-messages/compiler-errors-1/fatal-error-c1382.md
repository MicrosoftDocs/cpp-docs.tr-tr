---
title: Önemli hata C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: 2b7f6fd878f0d0ba6cde19a3a316a01c390e954a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228570"
---
# <a name="fatal-error-c1382"></a>Önemli hata C1382

'obj' oluşturulmasının üzerinden PCH dosya 'dosyası yeniden oluşturuldu. Lütfen bu nesneyi yeniden oluşturun

Kullanırken [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), derleyici gösteren bir CIL .obj daha yeni bir .pch dosyası algılandı. CIL'i .obj dosyasındaki bilgiler güncel değil. Bir nesneyi yeniden oluşturun.

C1382 ile derleme yaparsanız da gerçekleşebilir **/Yc**, ancak ayrıca birden çok kaynak kod dosyaları için derleyici geçirin.  Çözümlemek için kullanmayın **/Yc** birden çok kaynak kodu dosyaları için derleyici geçerken.  Daha fazla bilgi için [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md).