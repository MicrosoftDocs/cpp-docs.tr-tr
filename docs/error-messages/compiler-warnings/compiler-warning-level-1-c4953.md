---
title: Derleyici Uyarısı (düzey 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 1948342e1ff97c38ca3a44694dc7e7d399d96825
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384159"
---
# <a name="compiler-warning-level-1-c4953"></a>Derleyici Uyarısı (düzey 1) C4953

> Alınanın '*işlevi*' profili bu yana profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir

Kullanırken [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), derleyici sonra derlendiğini bir giriş modülü algılandı `/LTCG:PGINSTRUMENT` ve bir işlev (*işlevi*) düzenlenebilir ve burada mevcut test çalışmaları tanımlanan bir aday olarak işlev satır içi kullanım. Ancak, sonuç olarak modülü yeniden derlemeden işlev adayı olmayacak satır içi kullanım.

Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmek için `/LTCG:PGINSTRUMENT`, tüm test Yinele çalıştırır ve çalıştırma `/LTCG:PGOPTIMIZE`.

Bu uyarı ile ilgili bir hata varsa geçecekti `/LTCG:PGOPTIMIZE` kullanılmış.