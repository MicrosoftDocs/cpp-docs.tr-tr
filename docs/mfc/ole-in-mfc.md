---
description: Daha fazla bilgi için bkz. MFC 'de OLE
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
ms.openlocfilehash: 125a2ad8e900747d859c03b57df33f2e7e5f1c28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244101"
---
# <a name="ole-in-mfc"></a>MFC'de OLE

Bu makalelerde, MFC kullanarak OLE programlamanın temelleri açıklanmaktadır. MFC, OLE kullanan programları yazmanın en kolay yolunu sağlar:

- OLE görsel düzenlemesini (yerinde etkinleştirme) kullanmak için.

- OLE kapsayıcıları veya sunucuları olarak çalışmak için.

- Sürükle bırak işlevini uygulamak için.

- Tarih ve saat verileriyle çalışma.

- İçe aktarılmış DLL işlev giriş noktaları, OLE/COM arabirimi giriş noktaları ve pencere yordamı giriş noktaları dahil olmak üzere MFC modüllerinin durum verilerini yönetmek için.

[Otomasyon](automation.md)da kullanabilirsiniz.

> [!NOTE]
> OLE terimi, OLE kapsayıcıları, OLE sunucuları, OLE öğeleri, yerinde etkinleştirme (ya da görsel düzenlemeler), trackatmalar, sürükle ve bırak ve menü birleştirme dahil olmak üzere bağlama ve ekleme ile ilişkili teknolojileri gösterir. Etkin terim, bileşen nesne modeli (COM) ve ActiveX denetimleri gibi COM tabanlı nesneler için geçerlidir. OLE Otomasyonu artık Otomasyon olarak adlandırılır.

## <a name="in-this-section"></a>Bu Bölümde

[OLE arka planı](ole-background.md)<br/>
OLE ' i açıklar ve nasıl çalıştığı hakkında kavramsal bilgiler sağlar.

[Etkinleştirme](activation-cpp.md)<br/>
OLE öğelerini düzenlemede etkinleştirmenin rolünü açıklar.

[Kapsayıcılar](containers.md)<br/>
OLE içinde kapsayıcıları kullanmak için bağlantılar sağlar.

[Veri nesneleri ve veri kaynakları](data-objects-and-data-sources-ole.md)<br/>
Ve sınıflarının kullanımını tartışan konuların bağlantılarını sağlar `COleDataObject` `COleDataSource` .

[Sürükleme ve Bırakma](drag-and-drop-ole.md)<br/>
OLE ile kopyalama ve yapıştırmayı kullanmayı açıklar.

[OLE menüleri ve kaynakları](menus-and-resources-ole.md)<br/>
MFC OLE belge uygulamalarında menülerin ve kaynakların kullanımını açıklar.

[Kaydını](registration.md)<br/>
Sunucu yüklemeyi ve başlatmayı açıklar.

[Sunucular](servers.md)<br/>
Kapsayıcı uygulamalar tarafından kullanılmak üzere OLE öğeleri (veya bileşenleri) oluşturmayı açıklar.

[İzleyiciler](trackers.md)<br/>
`CRectTracker`KULLANıCıLARıN OLE istemci öğeleriyle etkileşime geçmesini sağlamak için grafiksel bir arabirim sağlayan sınıfı hakkında bilgi sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[Bağlantı noktaları](connection-points.md)<br/>
MFC sınıflarını ve kullanarak bağlantı noktalarının (eski adıyla OLE bağlantı noktaları) nasıl uygulanacağını açıklar `CCmdTarget` `CConnectionPoint` .

[Kapsayıcı/sunucu COM bileşenleri](containers-advanced-features.md)<br/>
Mevcut kapsayıcı uygulamalarına isteğe bağlı gelişmiş özellikler eklemek için gereken adımları açıklar.

[Bileşen nesne modeli](/windows/win32/com/the-component-object-model)<br/>
MFC olmadan OLE kullanımını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)
