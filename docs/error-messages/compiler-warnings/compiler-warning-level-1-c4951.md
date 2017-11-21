---
title: "Derleyici Uyarısı (düzey 1) C4951 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4951
dev_langs: C++
helpviewer_keywords: C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: efb4b4a283964230d191962db40c4d061a039dfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4951"></a>Derleyici Uyarısı (düzey 1) C4951
'function' profili itibaren kullanılmıyor işlevi profil verileri, toplanan veriler, düzenlenebilir  
  
 Bir işlev için bir giriş modülünde düzenlenen [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md), böylece profil verileri artık geçerli değil. Giriş modülü sonra derlendiğini **/LTCG:PGINSTRUMENT** ve bir işleve sahiptir (***işlevi***) farklı bir akış modülünde zamanında olandan denetimi ile **/LTCG:PGINSTRUMENT**  işlemi.  
  
 Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözümlemek **/LTCG:PGINSTRUMENT**, tüm test yineleme çalıştırır ve Çalıştır **/LTCG:PGOPTIMIZE**.  
  
 Bu uyarı ile bir hata durumunda değiştirilmesi **/LTCG:PGOPTIMIZE** kullanılan.