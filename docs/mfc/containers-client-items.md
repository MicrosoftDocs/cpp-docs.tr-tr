---
title: 'Kapsayıcılar: İstemci öğeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14979f1c5f11e9a229c408e33e7c17d8776a54a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344223"
---
# <a name="containers-client-items"></a>Kapsayıcılar: İstemci Öğeleri
Bu makale, istemci öğeleri nelerdir açıklar ve ne sınıfları, uygulamanızın istemci öğelerinden türetilmelidir.  
  
 İstemci, içerdiği ya da bir OLE kapsayıcı uygulamanın belgenin başvurduğu başka bir uygulamaya ait veri öğeleri öğelerdir. İstemci öğeleri verisini belge içinde yer alan katıştırılmış; Bu veri kapsayıcısı belgenin başvurduğu başka bir konumda depolanan bağlanır.  
  
 OLE uygulama belge sınıfında sınıfından türetilen [COleDocument](../mfc/reference/coledocument-class.md) yerine **CDocument**. `COleDocument` Sınıfının devraldığı **CDocument** üzerinde hangi MFC uygulamalarını dayalı belge/görünüm mimarisinin kullanmak için gereken tüm işlevselliği. `COleDocument` Ayrıca bir belgeyi koleksiyonu olarak ele alan bir arabirim tanımlar `CDocItem` nesneleri. Birkaç `COleDocument` üye işlevleri ekleme, alma ve o koleksiyonun öğelerini silme için sağlanır.  
  
 Her kapsayıcı uygulaması en az bir sınıftan türetilmelidir `COleClientItem`. Bu sınıfın nesneleri, OLE belgede bağlı veya katıştırılmış öğeleri temsil eder. Belgeden silinmeden bu nesneleri için bunları içeren belgesinin kullanım ömrü vardır.  
  
 `CDocItem` temel sınıfı olan `COleClientItem` ve `COleServerItem`. Bu iki türetilen sınıfların nesnelerini OLE öğesi ve istemci ve sunucu uygulamaları arasındaki aracılar sırasıyla görevi görür. Belgeye yeni bir OLE öğesi eklenen her zaman MFC çerçevesi, istemci uygulamanızın yeni bir nesne ekler `COleClientItem`-belgenin koleksiyonuna türetilmiş sınıf `CDocItem` nesneleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kapsayıcıları](../mfc/containers.md)   
 [Kapsayıcılar: Bileşik dosyalar](../mfc/containers-compound-files.md)   
 [Kapsayıcılar: Kullanıcı arabirimi sorunları](../mfc/containers-user-interface-issues.md)   
 [Kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md)   
 [COleClientItem sınıfı](../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Sınıfı](../mfc/reference/coleserveritem-class.md)
