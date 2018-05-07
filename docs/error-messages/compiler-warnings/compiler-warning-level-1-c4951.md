---
title: Derleyici Uyarısı (düzey 1) C4951 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c3ebf012338bdf6b90cc943e754056335c6751a4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951
'function' profili itibaren kullanılmıyor işlevi profil verileri, toplanan veriler, düzenlenebilir  
  
 Bir işlev için bir giriş modülünde düzenlenen [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), böylece profil verileri artık geçerli değil. Giriş modülü sonra derlendiğini **/LTCG:PGINSTRUMENT** ve bir işleve sahiptir (***işlevi***) farklı bir akış modülünde zamanında olandan denetimi ile **/LTCG:PGINSTRUMENT**  işlemi.  
  
 Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözümlemek **/LTCG:PGINSTRUMENT**, tüm test yineleme çalıştırır ve Çalıştır **/LTCG:PGOPTIMIZE**.  
  
 Bu uyarı ile bir hata durumunda değiştirilmesi **/LTCG:PGOPTIMIZE** kullanılan.