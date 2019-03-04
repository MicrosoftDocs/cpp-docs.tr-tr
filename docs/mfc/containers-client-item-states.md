---
title: 'Kapsayıcılar: İstemci öğesi durumları'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
ms.openlocfilehash: 1453ba3f96e49cefc9014a93ebcfbcfe5c6bc905
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273680"
---
# <a name="containers-client-item-states"></a>Kapsayıcılar: İstemci öğesi durumları

Bu makalede, yaşam sürelerinin başlarında istemci öğesi geçtiği farklı durumları açıklanmaktadır.

Bu, etkin, değişiklik, oluşturup kaydettikten gibi bir istemci öğesi çeşitli durumları arasında geçirir. Her öğenin durum değişikliklerini framework çağrıların zaman [COleClientItem::OnChange](../mfc/reference/coleclientitem-class.md#onchange) ile **OLE_CHANGED_STATE** bildirim. Bir değerdir ikinci parametre `COleClientItem::ItemState` sabit listesi. Aşağıdakilerden biri olabilir:

- *COleClientItem::emptyState*

- *COleClientItem::loadedState*

- *COleClientItem::openState*

- *COleClientItem::activeState*

- *COleClientItem::activeUIState*

Boş bir durumda, istemci öğesi henüz tamamen bir öğe değil. Bellek için ayrıldı, ancak, henüz OLE öğesinin verilerle başlatılmadı. Bu istemci öğesi olan içinde yapılan bir çağrıyla oluşturulduğunda durumdur **yeni** ancak henüz tipik iki aşamalı oluşturma ikinci adım gerçekleştirmedi.

İkinci adımda yapılan bir çağrıyla gerçekleştirilen `COleClientItem::CreateFromFile` veya başka bir `CreateFrom` *xxxx* işlevi öğesi tamamen oluşturuldu. OLE verilerden (bir dosya ya da Pano gibi diğer bazı kaynak) ile ilişkili `COleClientItem`-türetilmiş bir nesneye. Şimdi öğeyi yüklü durumda.

Bir öğenin sunucunun penceresinde açılan yerine, kapsayıcının belge yerinde açılır, açık (veya tamamen açık) durumdadır. Bu durumda, geçici tarama genellikle öğe başka bir yerde etkin olduğunu belirtmek için kapsayıcının pencere öğesinde gösterimini üzerinden çizilir.

Bir öğenin yerinde etkinleştirildiğinde, genellikle yalnızca arabimini kısaca, etkin duruma aracılığıyla. Ardından, sunucu, menüleri, araç çubukları ve diğer kullanıcı arabirimi bileşenleri kapsayıcının değerlerle birleştirildi UI etkin duruma girer. Bu kullanıcı arabirimi bileşenleri varlığını etkin duruma kullanıcı Arabirimi etkin durumdan ayırır. Aksi takdirde, etkin duruma kullanıcı Arabirimi etkin duruma benzer. Sunucunun geri destekliyorsa, sunucuya yüklenmedi veya açık durumuna ulaşana kadar OLE öğesinin geri alma-durum bilgilerini korumak için gereklidir.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](../mfc/containers.md)<br/>
[Etkinleştirme](../mfc/activation-cpp.md)<br/>
[Kapsayıcılar: İstemci öğesi bildirimleri](../mfc/containers-client-item-notifications.md)<br/>
[İzleyiciler](../mfc/trackers.md)<br/>
[CRectTracker Sınıfı](../mfc/reference/crecttracker-class.md)
