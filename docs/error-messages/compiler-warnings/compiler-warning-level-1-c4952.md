---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4952'
title: Derleyici Uyarısı (düzey 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: afbc12f6e4e8219c541acd846a3752a331abe827
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327953"
---
# <a name="compiler-warning-level-1-c4952"></a>Derleyici Uyarısı (düzey 1) C4952

> '*Function*': '*pgd_file*' program veritabanında profil verileri bulunamadı

[/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, derleyici, sonrasında `/LTCG:PGINSTRUMENT` yeniden derlenen ve yeni bir işlev (*işlev*) bulunan bir giriş modülü algıladı.

Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı çözmek için, çalıştırın `/LTCG:PGINSTRUMENT` , tüm test çalıştırmalarını yineleyin ve çalıştırın `/LTCG:PGOPTIMIZE` .

Bu uyarı, kullanıldıysa bir hata ile değiştirilmelidir `/LTCG:PGOPTIMIZE` .
