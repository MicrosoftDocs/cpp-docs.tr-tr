---
title: "Kapsayıcılar: İstemci öğesi durumları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bcc43d4e8b32a8766eef7c50e45bece569ef5c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-item-states"></a>Kapsayıcılar: İstemci Öğesi Durumları
Bu makalede, bir istemci öğesi ömrü geçtiği farklı durumlara açıklanmaktadır.  
  
 Oluşturulan, etkin, değişiklik, kaydedilmiş ve gibi bir istemci öğesi birkaç durumları arasında aktarır. Her öğenin durumunu, framework çağrıları değiştiğinde [COleClientItem::OnChange](../mfc/reference/coleclientitem-class.md#onchange) ile `OLE_CHANGED_STATE` bildirim. Bir değerdir ikinci parametre **COleClientItem::ItemState** numaralandırması. Aşağıdakilerden biri olabilir:  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 Boş durumunda bir istemci madde henüz tamamen bir öğe değil. Bellek için ayrıldı, ancak bunu henüz OLE öğesi'nin verilerle başlatılmadı. Bu istemci öğesi olduğundan, bir çağrıyla oluşturulduğunda durumdur **yeni** henüz tipik iki aşamalı oluşturma ikinci adım geçmemiştir ancak.  
  
 İkinci adımda çağrısıyla gerçekleştirilen `COleClientItem::CreateFromFile` veya başka bir **CreateFrom***xxxx* işlevi, öğe tamamen oluşturuldu. OLE verilerden (bir dosyayı veya başka bir kaynaktan, Pano gibi) ile ilişkili `COleClientItem`-türetilmiş bir nesne içermelidir. Şimdi öğesi yüklü durumda.  
  
 Bir öğe sunucunun pencerede açıldı yerine, kapsayıcının belge yerinde açılan Aç (veya tam olarak açık) durumda değil. Bu durumda, geçici tarama genellikle öğesi başka bir yerde etkin olduğunu belirtmek için kapsayıcının pencere öğesinde gösterimini üzerinden çizilir.  
  
 Bir öğe yerinde etkinleştirildiğinde, bunu, genellikle yalnızca geçirir kısaca, etkin durumdaki aracılığıyla. Ardından, sunucu menülerini, araç çubukları ve diğer kullanıcı arabirimi bileşenlerini kapsayıcısının olanla birleştirildi UI etkin durumuna girer. Bu kullanıcı arabirimi bileşenlerini varlığını etkin durumdaki kullanıcı Arabirimi etkin durumundan ayırır. Aksi durumda, etkin durumdaki kullanıcı Arabirimi etkin durumu benzer. Sunucunun geri alma destekliyorsa, sunucunun yüklenmedi veya açık durumu ulaşana kadar OLE öğesi'nin geri alma işlemi durum bilgilerini korumak için gereklidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Etkinleştirme](../mfc/activation-cpp.md)   
 [Kapsayıcılar: İstemci öğesi bildirimleri](../mfc/containers-client-item-notifications.md)   
 [İzleyicileri](../mfc/trackers.md)   
 [CRectTracker Sınıfı](../mfc/reference/crecttracker-class.md)
