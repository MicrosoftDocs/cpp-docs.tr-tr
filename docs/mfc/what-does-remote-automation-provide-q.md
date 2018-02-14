---
title: "Uzaktan Otomasyon Neler Sağlar? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Remote Automation, DCOM
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4a82b26a1e6c208a584dfd19ebfd4530b4bdf76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="what-does-remote-automation-provide"></a>Uzaktan Otomasyon Neler Sağlar?
Uzak Otomasyon sağlar çağrılacak programları `IDispatch` başka bir makineden uygulamalarında. Otomasyon tarafından özellikle gereken diğer arabirimleri de destekler **IEnumVARIANT** koleksiyonu desteği. Herhangi bir COM arabirimi dağıtma kabiliyeti sağlamaz (dışında **IUnknown**, Elbette) ve isteğe bağlı olarak normal Otomasyon gibi Automation tarafından desteklenen veri türleri için sıralama desteği içerir.  
  
 Bu tesisler kümesinin bir programa yöntemleri ve özellikleri koleksiyonları veya erişilebilir ağ düğüm üzerinde çalışan bir nesnenin başka Otomasyon nesneleri döndüren dahil olmak üzere, erişim sağlar. İstemci makine uygun bir yazılım ayrıca çalışıyorsa sunucusunun (Bu yalnızca 32-bit ve 64-bit istemciler için çalışır ve kullanmaz rağmen olayları, kavramsal olarak benzer Otomasyon özellikleri kullanarak yeniden istemciye geri arama mümkündür aynı mekanizmayı).  
  
 Uzaktan Otomasyon sunucusu olarak çalıştırılabilir olacak şekilde bir uygulama için bir yürütülebilir dosya uygulanmalıdır (diğer bir deyişle, "yerel sunucu" yerine "InProc sunucu" olarak).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan Otomasyon nerelerde uygundur](where-does-remote-automation-fit-in-q.md)   
 [DCOM Geçmişi](../mfc/history-of-dcom.md)
