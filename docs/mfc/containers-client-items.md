---
description: 'Şu konuda daha fazla bilgi edinin: kapsayıcılar: Istemci öğeleri'
title: 'Kapsayıcılar: İstemci Öğeleri'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: e8aff84e825723b1615a0dbbadf7d5fec6d4cef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310440"
---
# <a name="containers-client-items"></a>Kapsayıcılar: İstemci Öğeleri

Bu makalede, istemci öğelerinin ne olduğu ve uygulamanızın istemci öğelerini hangi sınıflardan türettikleri açıklanmaktadır.

İstemci öğeleri, bir OLE kapsayıcı uygulamasının belgesi tarafından içerilen veya başvurulan başka bir uygulamaya ait olan veri öğeleridir. Verileri belgenin içinde bulunan istemci öğeleri gömülüdür; verileri kapsayıcı belge tarafından başvurulan başka bir konumda depolanan olanlar bağlantılıdır.

Bir OLE uygulamasındaki belge sınıfı, yerine sınıf [ortak belgesinden](reference/coledocument-class.md) türetilir `CDocument` . `COleDocument`Sınıfı, `CDocument` MFC uygulamalarının temel aldığı belge/görünüm mimarisini kullanmak için gereken tüm işlevlerden devralır. `COleDocument` Ayrıca, bir belgeyi bir nesne koleksiyonu olarak ele alan bir arabirim tanımlar `CDocItem` . `COleDocument`Bu koleksiyonun öğelerinin eklenmesi, alınması ve silinmesi için çeşitli üye işlevleri sağlanır.

Her kapsayıcı uygulaması, öğesinden en az bir sınıf türetmelidir `COleClientItem` . Bu sınıfın nesneleri, OLE belgesinde ekli veya bağlanmış öğeleri temsil eder. Bu nesneler, belgeden silinmedikleri takdirde, bunları içeren belgenin ömrü için mevcuttur.

`CDocItem` , ve için temel sınıftır `COleClientItem` `COleServerItem` . Bu iki nesneden türetilmiş sınıfların nesneleri, sırasıyla OLE öğesi ile istemci ve sunucu uygulamaları arasında aracılar olarak davranır. Belgeye her yeni OLE öğesi eklendiğinde, MFC çerçevesi, istemci uygulamanızın türetilmiş sınıfının yeni bir nesnesini `COleClientItem` belgenin nesne koleksiyonuna ekler `CDocItem` .

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](containers.md)<br/>
[Kapsayıcılar: bileşik dosyalar](containers-compound-files.md)<br/>
[Kapsayıcılar: User-Interface sorunları](containers-user-interface-issues.md)<br/>
[Kapsayıcılar: Gelişmiş Özellikler](containers-advanced-features.md)<br/>
[Colet Clienentidıtem sınıfı](reference/coleclientitem-class.md)<br/>
[Cotaserverıtem sınıfı](reference/coleserveritem-class.md)
