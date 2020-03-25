---
title: Önemli hata C1305
ms.date: 11/04/2016
f1_keywords:
- C1305
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
ms.openlocfilehash: 6ad00eb3d95e9f09d4f84daefb7e2a87fd1a3abf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203365"
---
# <a name="fatal-error-c1305"></a>Önemli hata C1305

' pgd_file ' profil veritabanı farklı bir mimari için

Başka bir platform için/LTCG: PGıNSTRUMENT işleminden oluşturulan bir. pgd dosyası [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) öğesine geçirildi. [Profil temelli iyileştirmeler](../../build/profile-guided-optimizations.md) x86 ve x64 platformları için kullanılabilir. Ancak, bir platform için/LTCG: PGıNSTRUMENT ile oluşturulan bir. pgd dosyası, farklı bir platform için bir/LTCG: PGOPTIMIZE öğesine giriş olarak geçerli değildir.

Bu hatayı çözmek için, aynı platformda/LTCG: PGıNSTRUMENT ve/LTCG: PGOPTIMIZE ile oluşturulan bir. pgd dosyasını geçirin.
