---
title: "Kapsayıcılar: İstemci öğeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aa80911ff14d329dc483cd6497393c6c5595ef2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-items"></a>Kapsayıcılar: İstemci Öğeleri
Bu makale, istemci öğeleri nelerdir açıklar ve ne sınıfları, uygulamanızın istemci öğelerinden türetilmelidir.  
  
 İstemci, içerdiği ya da bir OLE kapsayıcı uygulamanın belgenin başvurduğu başka bir uygulamaya ait veri öğeleri öğelerdir. İstemci öğeleri verisini belge içinde yer alan katıştırılmış; Bu veri kapsayıcısı belgenin başvurduğu başka bir konumda depolanan bağlanır.  
  
 OLE uygulama belge sınıfında sınıfından türetilen [COleDocument](../mfc/reference/coledocument-class.md) yerine **CDocument**. `COleDocument` Sınıfının devraldığı **CDocument** üzerinde hangi MFC uygulamalarını dayalı belge/görünüm mimarisinin kullanmak için gereken tüm işlevselliği. `COleDocument`Ayrıca bir belgeyi koleksiyonu olarak ele alan bir arabirim tanımlar `CDocItem` nesneleri. Birkaç `COleDocument` üye işlevleri ekleme, alma ve o koleksiyonun öğelerini silme için sağlanır.  
  
 Her kapsayıcı uygulaması en az bir sınıftan türetilmelidir `COleClientItem`. Bu sınıfın nesneleri, OLE belgede bağlı veya katıştırılmış öğeleri temsil eder. Belgeden silinmeden bu nesneleri için bunları içeren belgesinin kullanım ömrü vardır.  
  
 `CDocItem`temel sınıfı olan `COleClientItem` ve `COleServerItem`. Bu iki türetilen sınıfların nesnelerini OLE öğesi ve istemci ve sunucu uygulamaları arasındaki aracılar sırasıyla görevi görür. Belgeye yeni bir OLE öğesi eklenen her zaman MFC çerçevesi, istemci uygulamanızın yeni bir nesne ekler `COleClientItem`-belgenin koleksiyonuna türetilmiş sınıf `CDocItem` nesneleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Kapsayıcılar: Bileşik dosyalar](../mfc/containers-compound-files.md)   
 [Kapsayıcılar: Kullanıcı arabirimi sorunları](../mfc/containers-user-interface-issues.md)   
 [Kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md)   
 [COleClientItem sınıfı](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Sınıfı](../mfc/reference/coleserveritem-class.md)
