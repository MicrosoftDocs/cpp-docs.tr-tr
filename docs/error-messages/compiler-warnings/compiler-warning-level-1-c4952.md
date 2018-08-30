---
title: Derleyici Uyarısı (düzey 1) C4952 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f62f4c18380d89eb516a5fa49ef63e92ab79a6f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207157"
---
# <a name="compiler-warning-level-1-c4952"></a>Derleyici Uyarısı (düzey 1) C4952

> '*işlevi*': program veritabanında profil verileri bulunamadı '*pgd_file*'

Kullanırken [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), derleyici sonra derlendiğini bir giriş modülü algılandı `/LTCG:PGINSTRUMENT` ve yeni bir işlev (*işlevi*) mevcut.

Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmek için `/LTCG:PGINSTRUMENT`, tüm test Yinele çalıştırır ve çalıştırma `/LTCG:PGOPTIMIZE`.

Bu uyarı ile ilgili bir hata varsa geçecekti `/LTCG:PGOPTIMIZE` kullanılmış.