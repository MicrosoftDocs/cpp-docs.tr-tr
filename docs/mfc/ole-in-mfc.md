---
title: MFC'de OLE
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
ms.openlocfilehash: 2668d35c24e9d95440a96c5b3eda1fab7bbf3891
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507991"
---
# <a name="ole-in-mfc"></a>MFC'de OLE

Bu makalelerde, MFC kullanarak OLE programlamanın temelleri açıklanmaktadır. MFC, OLE kullanan programları yazmanın en kolay yolunu sağlar:

- OLE görsel düzenlemesini (yerinde etkinleştirme) kullanmak için.

- OLE kapsayıcıları veya sunucuları olarak çalışmak için.

- Sürükle bırak işlevini uygulamak için.

- Tarih ve saat verileriyle çalışma.

- İçe aktarılmış DLL işlev giriş noktaları, OLE/COM arabirimi giriş noktaları ve pencere yordamı giriş noktaları dahil olmak üzere MFC modüllerinin durum verilerini yönetmek için.

[Otomasyon](../mfc/automation.md)da kullanabilirsiniz.

> [!NOTE]
>  OLE terimi, OLE kapsayıcıları, OLE sunucuları, OLE öğeleri, yerinde etkinleştirme (ya da görsel düzenlemeler), trackatmalar, sürükle ve bırak ve menü birleştirme dahil olmak üzere bağlama ve ekleme ile ilişkili teknolojileri gösterir. Etkin terim, bileşen nesne modeli (COM) ve ActiveX denetimleri gibi COM tabanlı nesneler için geçerlidir. OLE Otomasyonu artık Otomasyon olarak adlandırılır.

## <a name="in-this-section"></a>Bu Bölümde

[OLE Arka Planı](../mfc/ole-background.md)<br/>
OLE ' i açıklar ve nasıl çalıştığı hakkında kavramsal bilgiler sağlar.

[Etkinleştirme](../mfc/activation-cpp.md)<br/>
OLE öğelerini düzenlemede etkinleştirmenin rolünü açıklar.

[Kapsayıcılar](../mfc/containers.md)<br/>
OLE içinde kapsayıcıları kullanmak için bağlantılar sağlar.

[Veri nesneleri ve veri kaynakları](../mfc/data-objects-and-data-sources-ole.md)<br/>
`COleDataObject` Ve`COleDataSource` sınıflarının kullanımını tartışan konuların bağlantılarını sağlar.

[Sürükleme ve Bırakma](../mfc/drag-and-drop-ole.md)<br/>
OLE ile kopyalama ve yapıştırmayı kullanmayı açıklar.

[OLE menüleri ve kaynakları](../mfc/menus-and-resources-ole.md)<br/>
MFC OLE belge uygulamalarında menülerin ve kaynakların kullanımını açıklar.

[Kayıt](../mfc/registration.md)<br/>
Sunucu yüklemeyi ve başlatmayı açıklar.

[Sunucular](../mfc/servers.md)<br/>
Kapsayıcı uygulamalar tarafından kullanılmak üzere OLE öğeleri (veya bileşenleri) oluşturmayı açıklar.

[İzleyiciler](../mfc/trackers.md)<br/>
Kullanıcıların OLE istemci öğeleriyle `CRectTracker` etkileşime geçmesini sağlamak için grafiksel bir arabirim sağlayan sınıfı hakkında bilgi sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[Bağlantı Noktaları](../mfc/connection-points.md)<br/>
MFC sınıflarını `CCmdTarget` ve `CConnectionPoint`kullanarak bağlantı noktalarının (eski adıyla ole bağlantı noktaları) nasıl uygulanacağını açıklar.

[Kapsayıcı/sunucu COM bileşenleri](../mfc/containers-advanced-features.md)<br/>
Mevcut kapsayıcı uygulamalarına isteğe bağlı gelişmiş özellikler eklemek için gereken adımları açıklar.

[Bileşen nesne modeli](/windows/win32/com/the-component-object-model)<br/>
MFC olmadan OLE kullanımını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../mfc/mfc-concepts.md)
