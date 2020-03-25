---
title: Derleyici Uyarısı (düzey 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 46f07227b5df62938cc51a7be4cf4f3595a0d947
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174525"
---
# <a name="compiler-warning-level-1-c4953"></a>Derleyici Uyarısı (düzey 1) C4953

> Profil verileri toplandıktan sonra ınlinee '*Function*' düzenlendi, profil verileri kullanılmadı

[/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, derleyici `/LTCG:PGINSTRUMENT` sonra yeniden derlenen bir giriş modülü algıladı ve düzenlenmiş bir işlev (*işlev*) ve var olan test çalıştırıldığında işlevi satır içi bir aday olarak tanımladı. Ancak, modülün yeniden derlenmesi sonucu olarak, işlev artık satır içi bir aday olmayacaktır.

Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı çözmek için `/LTCG:PGINSTRUMENT`çalıştırın, tüm test çalıştırmalarını yineleyin ve `/LTCG:PGOPTIMIZE`çalıştırın.

`/LTCG:PGOPTIMIZE` kullanılmışsa bu uyarı bir hata ile değiştirilmelidir.
