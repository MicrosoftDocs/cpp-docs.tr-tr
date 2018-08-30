---
title: Derleyici Uyarısı (düzey 1) C4953 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e53808d4ad97bad4eccdf81b0a863277f8f7796
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194638"
---
# <a name="compiler-warning-level-1-c4953"></a>Derleyici Uyarısı (düzey 1) C4953

> Alınanın '*işlevi*' profili bu yana profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir

Kullanırken [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), derleyici sonra derlendiğini bir giriş modülü algılandı `/LTCG:PGINSTRUMENT` ve bir işlev (*işlevi*) düzenlenebilir ve burada mevcut test çalışmaları tanımlanan bir aday olarak işlev satır içi kullanım. Ancak, sonuç olarak modülü yeniden derlemeden işlev adayı olmayacak satır içi kullanım.

Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmek için `/LTCG:PGINSTRUMENT`, tüm test Yinele çalıştırır ve çalıştırma `/LTCG:PGOPTIMIZE`.

Bu uyarı ile ilgili bir hata varsa geçecekti `/LTCG:PGOPTIMIZE` kullanılmış.