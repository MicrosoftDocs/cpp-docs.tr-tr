---
title: MFC'de OLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, OLE and
- OLE items
- OLE applications [MFC], about OLE
- OLE [MFC]
- OLE containers [MFC], about OLE
- applications [OLE], about OLE
- OLE component object model (COM)
ms.assetid: 5193479d-1239-4697-aea4-e82f92c707ab
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38b2f6c936ff314f56e4b1868837729ad00efce4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-in-mfc"></a>MFC'de OLE
Bu makaleler MFC kullanma OLE Programlama temelleri açıklanır. MFC OLE kullanan programlar yazmak için en kolay yolu sağlar:  
  
-   OLE görsel düzenleme (yerinde etkinleştirme) kullanmak için.  
  
-   OLE kapsayıcıları veya sunucuları olarak çalışmak için.  
  
-   Sürükle ve bırak işlevi uygulamak için.  
  
-   Tarih ve saat verilerle çalışmak için.  
  
-   MFC durumu verileri yönetmek için DLL işlev giriş noktaları, OLE/COM arabirimi giriş noktaları ve pencere yordamı giriş noktaları dahil olmak üzere modüllerdeki dışarı.  
  
 Aynı zamanda [Otomasyon](../mfc/automation.md) veya [uzaktan Otomasyon](../mfc/remote-automation.md) programınızdan başka bir programın çalışması için.  
  
> [!NOTE]
>  OLE kapsayıcıları, OLE sunucuları, OLE öğeleri, yerinde etkinleştirme (veya görsel düzenleme), bağlama ve katıştırma, ilişkili teknolojilerini izleyicileri, sürükle ve bırak OLE gösterir terim ve menü birleştirme. ActiveX denetimleri gibi terimi etkin Bileşen Nesne Modeli (COM) ve COM tabanlı nesneleri için geçerlidir. OLE Otomasyon şimdi Otomasyon adı verilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [OLE Arka Planı](../mfc/ole-background.md)  
 OLE açıklanır ve nasıl çalıştığı hakkında kavramsal bilgiler verilmektedir.  
  
 [Etkinleştirme](../mfc/activation-cpp.md)  
 OLE öğeleri düzenleme etkinleştirme rolü açıklanmaktadır.  
  
 [Kapsayıcılar](../mfc/containers.md)  
 OLE kapsayıcıları kullanma için bağlantılar sağlar.  
  
 [Veri nesneleri ve veri kaynakları](../mfc/data-objects-and-data-sources-ole.md)  
 Kullanımı ele konulara bağlantılar sağlanır `COleDataObject` ve `COleDataSource` sınıfları.  
  
 [Sürükleme ve Bırakma](../mfc/drag-and-drop-ole.md)  
 Kopyalama ve yapıştırma ile OLE kullanımını açıklar.  
  
 [OLE menüleri ve kaynakları](../mfc/menus-and-resources-ole.md)  
 Menüleri ve kaynakları MFC OLE belge uygulamaları kullanımını açıklar.  
  
 [Kayıt](../mfc/registration.md)  
 Sunucu yükleme ve başlatma açıklanır.  
  
 [Sunucular](../mfc/servers.md)  
 OLE öğeleri (veya bileşenleri) kullanmak için kapsayıcı uygulamalarının tarafından nasıl oluşturulacağını açıklar.  
  
 [İzleyiciler](../mfc/trackers.md)  
 Hakkında bilgi sağlar `CRectTracker` OLE istemci öğeleri ile etkileşim kullanıcılar etkinleştirmek için bir grafik arabirim sağlayan sınıf.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Bağlantı Noktaları](../mfc/connection-points.md)  
 Bağlantı noktaları (önceki adıyla OLE bağlantı noktaları bilinir) uygulamak açıklanmaktadır MFC sınıfları kullanarak `CCmdTarget` ve `CConnectionPoint`.  
  
 [Kapsayıcı/sunucu COM bileşenleri](../mfc/containers-advanced-features.md)  
 İsteğe bağlı Gelişmiş Özellikler varolan kapsayıcı uygulamalarına kavramak gereken adımları açıklar.  
  
 [Bileşen Nesne modeli](http://msdn.microsoft.com/library/windows/desktop/ms694363)  
 OLE MFC olmadan kullanmayı açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)

