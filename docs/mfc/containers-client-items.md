---
title: 'Kapsayıcılar: İstemci Öğeleri'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: ad347c78fb6aa7af94b306a3edb538b9f740c305
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619013"
---
# <a name="containers-client-items"></a>Kapsayıcılar: İstemci Öğeleri

Bu makalede, istemci öğelerinin ne olduğu ve uygulamanızın istemci öğelerini hangi sınıflardan türettikleri açıklanmaktadır.

İstemci öğeleri, bir OLE kapsayıcı uygulamasının belgesi tarafından içerilen veya başvurulan başka bir uygulamaya ait olan veri öğeleridir. Verileri belgenin içinde bulunan istemci öğeleri gömülüdür; verileri kapsayıcı belge tarafından başvurulan başka bir konumda depolanan olanlar bağlantılıdır.

Bir OLE uygulamasındaki belge sınıfı, yerine sınıf [ortak belgesinden](reference/coledocument-class.md) türetilir `CDocument` . `COleDocument`Sınıfı, `CDocument` MFC uygulamalarının temel aldığı belge/görünüm mimarisini kullanmak için gereken tüm işlevlerden devralır. `COleDocument`Ayrıca, bir belgeyi bir nesne koleksiyonu olarak ele alan bir arabirim tanımlar `CDocItem` . `COleDocument`Bu koleksiyonun öğelerinin eklenmesi, alınması ve silinmesi için çeşitli üye işlevleri sağlanır.

Her kapsayıcı uygulaması, öğesinden en az bir sınıf türetmelidir `COleClientItem` . Bu sınıfın nesneleri, OLE belgesinde ekli veya bağlanmış öğeleri temsil eder. Bu nesneler, belgeden silinmedikleri takdirde, bunları içeren belgenin ömrü için mevcuttur.

`CDocItem`, ve için temel sınıftır `COleClientItem` `COleServerItem` . Bu iki nesneden türetilmiş sınıfların nesneleri, sırasıyla OLE öğesi ile istemci ve sunucu uygulamaları arasında aracılar olarak davranır. Belgeye her yeni OLE öğesi eklendiğinde, MFC çerçevesi, istemci uygulamanızın türetilmiş sınıfının yeni bir nesnesini `COleClientItem` belgenin nesne koleksiyonuna ekler `CDocItem` .

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](containers.md)<br/>
[Kapsayıcılar: Bileşik Dosyalar](containers-compound-files.md)<br/>
[Kapsayıcılar: Kullanıcı Arabirimi Sorunları](containers-user-interface-issues.md)<br/>
[Kapsayıcılar: Gelişmiş Özellikler](containers-advanced-features.md)<br/>
[Colet Clienentidıtem sınıfı](reference/coleclientitem-class.md)<br/>
[Cotaserverıtem sınıfı](reference/coleserveritem-class.md)
