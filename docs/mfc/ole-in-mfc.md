---
title: MFC'de OLE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e43484e5f30191c604f43a2280a8deab6eddd93c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434953"
---
# <a name="ole-in-mfc"></a>MFC'de OLE

Bu makaleler, MFC kullanarak OLE programlamanın temellerini açıklar. MFC OLE kullanan programlar yazmak için en kolay yolu sağlar:

- OLE görsel düzenleme (yerinde etkinleştirme) kullanılacak.

- OLE kapsayıcıları veya sunucuları çalışacak şekilde.

- Sürükle ve bırak işlevselliğini uygulamak için.

- Tarih ve saat verilerle çalışmak için.

- MFC Durum verilerini yönetmek için modüller de dahil olmak üzere, DLL işlev giriş noktaları, OLE/COM arabirimi giriş noktaları ve pencere yordamı giriş noktaları dışarı.

Ayrıca [Otomasyon](../mfc/automation.md).

> [!NOTE]
>  Terim OLE OLE kapsayıcıları, OLE sunucuları, OLE öğeleri, yerinde etkinleştirme (veya görsel düzenleme), bağlama ve katıştırma, ile ilişkili teknolojilerini izleyicileri, sürükle ve bırak gösterir ve menü birleştirme. ActiveX denetimleri gibi terimi Bileşen Nesne Modeli (COM) ve COM tabanlı nesne etkin olarak uygulanır. OLE Otomasyonu, Otomasyon artık çağrılır.

## <a name="in-this-section"></a>Bu Bölümde

[OLE Arka Planı](../mfc/ole-background.md)<br/>
OLE açıklanır ve nasıl çalıştığı hakkında kavramsal bilgiler verilmektedir.

[Etkinleştirme](../mfc/activation-cpp.md)<br/>
OLE öğelerini düzenleme etkinleştirme rolünü açıklar.

[Kapsayıcılar](../mfc/containers.md)<br/>
OLE kapsayıcıları kullanımına ilişkin bağlantılar sağlar.

[Veri nesneleri ve veri kaynakları](../mfc/data-objects-and-data-sources-ole.md)<br/>
Kullanımını açıklayan konulara bağlantılar sağlar `COleDataObject` ve `COleDataSource` sınıfları.

[Sürükleme ve Bırakma](../mfc/drag-and-drop-ole.md)<br/>
Kopyalama ve yapıştırma OLE ile kullanımını açıklar.

[OLE menüleri ve kaynakları](../mfc/menus-and-resources-ole.md)<br/>
Menüler ve kaynaklar MFC OLE belge uygulamaları içinde kullanılmasını açıklar.

[Kayıt](../mfc/registration.md)<br/>
Sunucu yükleme ve başlatma ele alır.

[Sunucular](../mfc/servers.md)<br/>
OLE öğeleri (veya bileşenleri) kullanmak için kapsayıcı uygulamalar tarafından oluşturmayı açıklar.

[İzleyiciler](../mfc/trackers.md)<br/>
Hakkında bilgi sağlar `CRectTracker` OLE istemci öğeleri ile etkileşim kurmak kullanıcıları etkinleştirmek için bir grafik arabirim sağlar sınıfını.

## <a name="related-sections"></a>İlgili Bölümler

[Bağlantı Noktaları](../mfc/connection-points.md)<br/>
(Eski adıyla OLE bağlantı noktaları da bilinir) bağlantı noktalarının uygulanacağı açıklanmaktadır MFC sınıflarını kullanarak `CCmdTarget` ve `CConnectionPoint`.

[Kapsayıcı/sunucu COM bileşenleri](../mfc/containers-advanced-features.md)<br/>
Mevcut kapsayıcı uygulamalarınızı isteğe bağlı gelişmiş özellikler eklemek gereken adımları açıklar.

[Bileşen Nesne modeli](/windows/desktop/com/the-component-object-model)<br/>
OLE MFC olmadan kullanmayı açıklar.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)

