---
title: Derleyici Uyarısı (düzey 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: 560705edeb0bbdd6be760736a8d4a19d914133d2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174576"
---
# <a name="compiler-warning-level-1-c4952"></a>Derleyici Uyarısı (düzey 1) C4952

> '*Function*': '*pgd_file*' program veritabanında profil verileri bulunamadı

[/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, derleyici, `/LTCG:PGINSTRUMENT` sonra yeniden derlenen bir giriş modülü algıladı ve yeni bir işlev (*işlev*) var.

Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı çözmek için `/LTCG:PGINSTRUMENT`çalıştırın, tüm test çalıştırmalarını yineleyin ve `/LTCG:PGOPTIMIZE`çalıştırın.

`/LTCG:PGOPTIMIZE` kullanılmışsa bu uyarı bir hata ile değiştirilmelidir.
