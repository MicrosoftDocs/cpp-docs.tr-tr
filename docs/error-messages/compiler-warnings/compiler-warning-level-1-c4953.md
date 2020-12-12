---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4953'
title: Derleyici Uyarısı (düzey 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 1f10f757297bd4b0e71ec5246024a3ce7a313689
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327932"
---
# <a name="compiler-warning-level-1-c4953"></a>Derleyici Uyarısı (düzey 1) C4953

> Profil verileri toplandıktan sonra ınlinee '*Function*' düzenlendi, profil verileri kullanılmadı

[/LTCG: PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)kullanılırken, derleyici daha sonra yeniden derlenmiş bir giriş modülü algıladı `/LTCG:PGINSTRUMENT` ve düzenlenmiş bir işlev (*işlev*) ve var olan test çalıştırıldığında işlevi satır içi bir aday olarak tanımladı. Ancak, modülün yeniden derlenmesi sonucu olarak, işlev artık satır içi bir aday olmayacaktır.

Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı çözmek için, çalıştırın `/LTCG:PGINSTRUMENT` , tüm test çalıştırmalarını yineleyin ve çalıştırın `/LTCG:PGOPTIMIZE` .

Bu uyarı, kullanıldıysa bir hata ile değiştirilmelidir `/LTCG:PGOPTIMIZE` .
