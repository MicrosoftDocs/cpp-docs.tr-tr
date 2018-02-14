---
title: Uzaktan Otomasyon Nerelerde Uygundur? | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Remote Automation, DCOM
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ad6eef0bbaad7860e7f4310ce283efe18c668eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="where-does-remote-automation-fit-in"></a>Uzaktan Otomasyon Nerelerde Uygundur?
DCOM 1996 yayımlanmıştır ve yalnızca 32-bit ve 64 bit platformları ile kullanılabilir. Microsoft Visual Basic ekibi bileşenlerinden iletişim kurmasına izin vermek için otomasyonu kullanarak olarak Visual Basic her zaman görülen. Kendi uzaktan iletişim bileşenleri kümesi Otomasyon için oluşturulmasını araştırmak Visual Basic 4.0 Enterprise Edition geliştirme ekibi karar dağıtılmış sürüm eksikliği ciddi bir şekilde yeteneklere kurumsal ortamlarda kullanımını sınırlı, bu nedenle OLE ve COM bölümleri Açıkçası, sonucu ile uyumlu olacaktır ve DCOM tarafından kullanılabilir hale geldi zaman yerini emin olmak için bir ana hedef oluştu. Bunlar ardından uzak Otomasyon (RA) 16 bit ve 32-bit Windows platformları için uygulamak için proceeded.  
  
 Uzaktan Otomasyon için belirli bir dil bağlı değildir, ancak Visual C++ 4.2 Enterprise Edition Sürüm kadar yalnızca Visual Basic 4.0 ile geldiği. Uzak Otomasyon tamamen DCOM tarafından birden fazla yolu eklendi olmadığını unutmayın. DCOM Uzaktan Otomasyon yerine uygulamalarınızda kullanma olanağı varsa, bunu yapmanız gerekir. Bununla birlikte, uzak Otomasyon daha uygun olduğu senaryolar vardır:  
  
-   Yerde 16-bit istemciler vardır.  
  
-   Kuruluşunuz bir DCOM etkin sürümü Windows NT veya Windows 95 henüz alındı değil  
  
-   Varolan bir uygulama paketini yükseltiyorsanız, uzak Otomasyon kullanım C++ bileşenlerin bir veya daha fazla Visual Basic bileşenleri yerine için kullanır.  
  
 Uzak otomasyon ve DCOM üzerinden Otomasyon kullanmak için oluşturulanların kullanmak için oluşturulan programlar arasında fark olması ve yapılandırma programları işlemi uzaktan otomasyon ve DCOM arasında geçiş yapmak çok basit yapın. Sonuç olarak, uygulama altyapısının yerinde olduğundan sonra DCOM Uzaktan Otomasyon yükseltme zor değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan Otomasyon neler sağlar](what-does-remote-automation-provide-q.md)   
 [DCOM Geçmişi](../mfc/history-of-dcom.md)
