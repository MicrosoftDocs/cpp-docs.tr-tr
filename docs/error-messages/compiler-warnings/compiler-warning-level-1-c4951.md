---
title: "Derleyici Uyarısı (düzey 1) C4951 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 199df135d5d2c00255037e5a1b31db80e2683d4f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951
'function' profili itibaren kullanılmıyor işlevi profil verileri, toplanan veriler, düzenlenebilir  
  
 Bir işlev için bir giriş modülünde düzenlenen [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), böylece profil verileri artık geçerli değil. Giriş modülü sonra derlendiğini **/LTCG:PGINSTRUMENT** ve bir işleve sahiptir (***işlevi***) farklı bir akış modülünde zamanında olandan denetimi ile **/LTCG:PGINSTRUMENT**  işlemi.  
  
 Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözümlemek **/LTCG:PGINSTRUMENT**, tüm test yineleme çalıştırır ve Çalıştır **/LTCG:PGOPTIMIZE**.  
  
 Bu uyarı ile bir hata durumunda değiştirilmesi **/LTCG:PGOPTIMIZE** kullanılan.