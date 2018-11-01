---
title: Derleyici Uyarısı (düzey 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: 73e048aeaa044c35e09539b07d51398829a0fdfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617873"
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951

> '*işlevi*' profili beri işlevi profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir

Bir işlev için bir giriş modülünde düzenlenmiş [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), böylece profil verileri artık geçerli değil. Giriş modülü sonra derlendiğini **/LTCG:PGINSTRUMENT** ve bir işlev (*işlevi*) farklı bir modülde zamanında olandan denetim akışı ile **/LTCG:PGINSTRUMENT**  işlemi.

Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmek için **/LTCG:PGINSTRUMENT**, tüm test Yinele çalıştırır ve çalıştırma **/LTCG:PGOPTIMIZE**.

Bu uyarı ile ilgili bir hata varsa geçecekti **/LTCG:PGOPTIMIZE** kullanılmış.