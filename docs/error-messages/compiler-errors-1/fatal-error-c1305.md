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
ms.openlocfilehash: 4beb1140d161b8cbe54cab40dcc72899c976edc3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048753"
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305

'pgd_file' profil veritabanı farklı bir mimari için olan

Başka bir platform geçildi için /LTCG:PGINSTRUMENT işlemi oluşturulmasına neden olan bir .pgd dosyası [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) . [Profil temelli iyileştirmeler](../../build/reference/profile-guided-optimizations.md) x86 ve x64 platformlar için kullanılabilir. Ancak, tek bir platform için bir /LTCG:PGINSTRUMENT işlemi ile oluşturulan bir .pgd dosyası geçersiz bir /LTCG:PGOPTIMIZE farklı bir platform için giriş olarak.

Bu hatayı gidermek için yalnızca /LTCG:PGINSTRUMENT /LTCG:PGOPTIMIZE bulunan aynı platform için oluşturulan bir .pgd dosyası geçirin.