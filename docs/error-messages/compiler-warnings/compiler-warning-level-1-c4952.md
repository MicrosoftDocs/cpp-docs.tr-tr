---
title: Derleyici Uyarısı (düzey 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: c2e9b88125655d9ea0abe3e65500b149289ba83b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393291"
---
# <a name="compiler-warning-level-1-c4952"></a>Derleyici Uyarısı (düzey 1) C4952

> '*işlevi*': program veritabanında profil verileri bulunamadı '*pgd_file*'

Kullanırken [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), derleyici sonra derlendiğini bir giriş modülü algılandı `/LTCG:PGINSTRUMENT` ve yeni bir işlev (*işlevi*) mevcut.

Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmek için `/LTCG:PGINSTRUMENT`, tüm test Yinele çalıştırır ve çalıştırma `/LTCG:PGOPTIMIZE`.

Bu uyarı ile ilgili bir hata varsa geçecekti `/LTCG:PGOPTIMIZE` kullanılmış.