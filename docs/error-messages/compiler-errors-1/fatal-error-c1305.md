---
description: 'Daha fazla bilgi edinin: önemli hata C1305'
title: Önemli hata C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 100046d5ad7c6fa943358063d3d3cb21ffa00e5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267904"
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305

' pgd_file ' profil veritabanı farklı bir mimari için

Başka bir platform için/LTCG: PGıNSTRUMENT işleminden oluşturulan bir. pgd dosyası [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) öğesine geçirildi. [Profil temelli iyileştirmeler](../../build/profile-guided-optimizations.md) x86 ve x64 platformları için kullanılabilir. Ancak, bir platform için/LTCG: PGıNSTRUMENT ile oluşturulan bir. pgd dosyası, farklı bir platform için bir/LTCG: PGOPTIMIZE öğesine giriş olarak geçerli değildir.

Bu hatayı çözmek için, aynı platformda/LTCG: PGıNSTRUMENT ve/LTCG: PGOPTIMIZE ile oluşturulan bir. pgd dosyasını geçirin.
