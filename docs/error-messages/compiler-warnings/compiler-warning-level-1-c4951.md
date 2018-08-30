---
title: Derleyici Uyarısı (düzey 1) C4951 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e26c4bc176a54f063a3f9bce2faf451a9c0406f0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204241"
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951

> '*işlevi*' profili beri işlevi profil verileri, veri toplanmıştır düzenlenip düzenlenmediğini gösterir

Bir işlev için bir giriş modülünde düzenlenmiş [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), böylece profil verileri artık geçerli değil. Giriş modülü sonra derlendiğini **/LTCG:PGINSTRUMENT** ve bir işlev (*işlevi*) farklı bir modülde zamanında olandan denetim akışı ile **/LTCG:PGINSTRUMENT**  işlemi.

Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmek için **/LTCG:PGINSTRUMENT**, tüm test Yinele çalıştırır ve çalıştırma **/LTCG:PGOPTIMIZE**.

Bu uyarı ile ilgili bir hata varsa geçecekti **/LTCG:PGOPTIMIZE** kullanılmış.