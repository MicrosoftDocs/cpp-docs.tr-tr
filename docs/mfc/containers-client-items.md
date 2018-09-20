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
ms.openlocfilehash: ae9a37aaeb9df3241cf48d3fc62db046682a7a1b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387074"
---
# <a name="containers-client-items"></a>Kapsayıcılar: İstemci Öğeleri

Bu makalede istemci öğeleri nelerdir anlatılmaktadır ve hangi sınıflar, uygulamanızın istemci öğelerinden türetilmelidir.

İstemci öğeleri olan veya bir OLE kapsayıcı uygulamasının belgenin başvurduğu bulunan başka bir uygulamaya ait veri öğelerdir. İstemci öğeleri verisini belgenin içinde yer alan bir parçasıdır; Bu verileri kapsayıcı belgenin başvurduğu başka bir konumda depolanan bağlanır.

Belge sınıfı bir OLE uygulama içindeki sınıftan türetilen [COleDocument](../mfc/reference/coledocument-class.md) yerine `CDocument`. `COleDocument` Sınıfının devraldığı `CDocument` tabanlı uygulamalar üzerinde hangi MFC belge/görünüm mimarisi kullanmak için gerekli tüm işlevleri. `COleDocument` Ayrıca bir belge koleksiyonu olarak değerlendirir bir arabirim tanımlar `CDocItem` nesneleri. Birkaç `COleDocument` üye işlevleri, ekleme, alma, o koleksiyonun öğeleri silme için sağlanır.

Her kapsayıcı uygulaması en az bir sınıftan türetilmelidir `COleClientItem`. Bu sınıfın nesneleri, gömülü veya bağlantılı hale OLE belge öğeleri temsil eder. Belge silinmeden bu nesneler, içeren belge ömrünü için mevcut.

`CDocItem` temel sınıfı olan `COleClientItem` ve `COleServerItem`. Bu iki türetilen sınıfların nesnelerini sırasıyla OLE öğesini ve istemci ve sunucu uygulamaları arasındaki aracılar gibi davranır. Yeni bir OLE öğesi belge için eklenen MFC çerçevesi, istemci uygulamanızın yeni bir nesne ekler `COleClientItem`-türetilmiş sınıf için belgenin koleksiyonunu `CDocItem` nesneleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Kapsayıcılar: Bileşik Dosyalar](../mfc/containers-compound-files.md)<br/>
[Kapsayıcılar: Kullanıcı Arabirimi Sorunları](../mfc/containers-user-interface-issues.md)<br/>
[Kapsayıcılar: Gelişmiş Özellikler](../mfc/containers-advanced-features.md)<br/>
[COleClientItem Sınıfı](../mfc/reference/coleclientitem-class.md)<br/>
[COleServerItem Sınıfı](../mfc/reference/coleserveritem-class.md)
