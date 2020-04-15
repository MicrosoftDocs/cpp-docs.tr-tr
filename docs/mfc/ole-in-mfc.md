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
ms.openlocfilehash: 2594531df63bcd62cdaec44fbc3668ea68990922
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366893"
---
# <a name="ole-in-mfc"></a>MFC'de OLE

Bu makaleler, MFC kullanarak OLE programlamanın temellerini açıklar. MFC, OLE kullanan programları yazmanın en kolay yolunu sağlar:

- OLE görsel düzenleme (yerinde etkinleştirme) kullanmak için.

- OLE kapsayıcıları veya sunucuları olarak çalışmak için.

- Sürükle ve bırak işlevselliğini uygulamak için.

- Tarih ve saat verileriyle çalışmak için.

- Dışa aktarılan DLL işlev giriş noktaları, OLE/COM arabirim giriş noktaları ve pencere yordam giriş noktaları da dahil olmak üzere MFC modüllerinin durum verilerini yönetmek için.

[Ayrıca Otomasyon](../mfc/automation.md)kullanabilirsiniz.

> [!NOTE]
> OLE terimi, OLE kapsayıcıları, OLE sunucuları, OLE öğeleri, yerinde etkinleştirme (veya görsel düzenleme), izciler, sürükle ve bırakma ve menü birleştirme dahil olmak üzere bağlantı ve katıştırma ile ilişkili teknolojileri gösterir. Active terimi Bileşen Nesne Modeli (COM) ve ActiveX denetimleri gibi COM tabanlı nesneler için geçerlidir. OLE Otomasyon artık Otomasyon olarak adlandırılıyor.

## <a name="in-this-section"></a>Bu Bölümde

[OLE Arka Plan](../mfc/ole-background.md)<br/>
OLE'yi tartışır ve nasıl çalıştığı hakkında kavramsal bilgiler sağlar.

[Etkinleştirme](../mfc/activation-cpp.md)<br/>
OLE öğelerini düzenlemede etkinleştirme rolünü açıklar.

[Kapsayıcılar](../mfc/containers.md)<br/>
OLE'de kapsayıcıları kullanmaya bağlantılar sağlar.

[Veri Nesneleri ve Veri Kaynakları](../mfc/data-objects-and-data-sources-ole.md)<br/>
Sınıfların ve sınıfların `COleDataObject` kullanımını tartışan konulara bağlantılar sağlar. `COleDataSource`

[Sürükleme ve Bırakma](../mfc/drag-and-drop-ole.md)<br/>
OLE ile kopyalama ve yapıştırma kullanarak tartışır.

[OLE Menüleri ve Kaynakları](../mfc/menus-and-resources-ole.md)<br/>
MFC OLE belge uygulamalarında menülerin ve kaynakların kullanımını açıklar.

[Kayıt](../mfc/registration.md)<br/>
Sunucu yükleme ve başlatma yı tartışır.

[Sunucular](../mfc/servers.md)<br/>
Kapsayıcı uygulamaları tarafından kullanılmak üzere OLE öğelerinin (veya bileşenlerinin) nasıl oluşturulacaklarını açıklar.

[Izci](../mfc/trackers.md)<br/>
Kullanıcıların OLE `CRectTracker` istemci öğeleriyle etkileşimkurmasını sağlamak için grafik arabirimi sağlayan sınıf hakkında bilgi sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[Bağlantı Noktaları](../mfc/connection-points.md)<br/>
MFC sınıflarını `CCmdTarget` kullanarak bağlantı noktalarının (eski adıyla OLE bağlantı `CConnectionPoint`noktaları) nasıl uygulanacağını açıklar ve.

[Konteyner/Sunucu COM Bileşenleri](../mfc/containers-advanced-features.md)<br/>
İsteğe bağlı gelişmiş özellikleri varolan kapsayıcı uygulamalarına dahil etmek için gereken adımları açıklar.

[Bileşen Nesne Modeli](/windows/win32/com/the-component-object-model)<br/>
MFC olmadan OLE kullanarak açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../mfc/mfc-concepts.md)
