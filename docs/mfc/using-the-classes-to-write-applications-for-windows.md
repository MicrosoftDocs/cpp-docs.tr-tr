---
title: Windows uygulamaları yazmak için sınıfları kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9907424a583cc16f170890a739fa7ece8cc93ead
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075131"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>Windows Uygulamaları Yazmak için Sınıfları Kullanma

Birlikte ele alındığında, "Windows işletim sistemi için bir uygulama derleme bir uygulama çerçevesi," Microsoft Foundation Class (MFC) Kitaplığı'ndaki sınıfları oluşturur. Framework çok genel düzeyde, bir uygulama çatısı tanımlar ve çatıyı yerleştirilebilir standart kullanıcı arabirimi uygulamalarını sağlar. Bunları, uygulamanıza özgü olan iskelet geri kalanı doldurmak için işinizi programcısı olarak olan. Avantajlı bir başlangıç çok kapsamlı başlangıç uygulaması dosyalarını oluşturmak için MFC Uygulama Sihirbazı'nı kullanarak alabilirsiniz. Microsoft Visual C++ kaynak düzenleyicileri kodu ve sınıf kitaplığı için bu öğeleri bağlanmak için Sınıf Görünümü komutları görsel tasarım, kullanıcı arabirimi öğeleri için uygulamaya özgü mantığı uygulamak için kullanın.

Win32 platformları dahil olmak üzere Microsoft Windows 95 ve daha sonra programlama ve Windows NT sürüm 3.51 sürümü ve sonraki sürüm 3.0 ve sonraki MFC framework'ün destekler. Çoklu iş parçacığı kullanımı MFC Win32 desteği içerir. Kullanım sürüm 1.5*x* 16-bit programlama yapmanız gerekiyorsa.

Bu makaleler ailesi uygulama çerçevesi geniş kapsamlı bir bakış sunar. Ayrıca, uygulamanızı ve nasıl oluşturulduğunu oluşturan büyük nesneleri keşfediyor. Aşağıdaki makalelerde ele alınan konulara arasında aşağıda verilmiştir:

- [Framework](../mfc/framework-mfc.md).

- İşçi çerçevesi ve kodunuz, açıklandığı arasında bölünmesi [Framework'te derleme](../mfc/building-on-the-framework.md).

- [Uygulama sınıfı](../mfc/cwinapp-the-application-class.md), uygulama düzeyinde işlevselliğini kapsüller.

- Nasıl [belge şablonları](../mfc/document-templates-and-the-document-view-creation-process.md) oluşturup belgeler ve bunların ilişkili görünümler yönetmek ve windows çerçeve.

- Sınıf [CWnd](../mfc/window-objects.md), tüm windows kök taban sınıfı.

- [Grafik nesneler](../mfc/graphic-objects.md)kalemler ve fırçalar gibi.

Framework'ün diğer bölümleri şunlardır:

- [Pencere nesneleri: genel bakış](../mfc/window-objects.md)

- [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)

- [CObject, MFC'de kök taban sınıfı](../mfc/using-cobject.md)

- [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

- [İletişim Kutuları](../mfc/dialog-boxes.md)

- [Denetimler](../mfc/controls-mfc.md)

- [Denetim Çubukları](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [Bellek Yönetimi](../mfc/memory-management.md)

   Windows işletim sistemi için uygulamalar yazma bir avantajını sunarak yanı sıra, MFC de özellikle bağlama ve katıştırma teknoloji OLE kullanan uygulamalar yazmak kolaylaşır. Uygulamanızı bir OLE görsel kapsayıcı, bir OLE görsel düzenleme sunucusu veya her ikisi de düzenleme yapabileceğiniz ve böylece diğer uygulamalar, uygulamanız nesneleri kullanın veya bile uzaktan sürücü Otomasyon ekleyebilirsiniz.

- [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

   OLE denetim Geliştirme Seti (CDK) artık framework ile tamamen tümleşiktir. Bu makalede ailesi ile MFC ActiveX denetimi geliştirme genel bir bakış sağlar. (ActiveX denetimlerini eski adı OLE denetimleri bilinirdi.)

- [Veritabanı programlama](../data/data-access-programming-mfc-atl.md)

   MFC Ayrıca iki veri yazma erişimi basitleştirin ve veritabanı sınıfları kümesi sağlayan uygulamalar. ODBC veritabanı sınıfları kullanarak, bir açık veritabanı bağlantısı (ODBC) sürücüsü aracılığıyla veritabanlarına bağlanmak, kayıtları tabloları seçin ve kayıt bilgileri görüntüleme bir ekrandaki formu. Veri erişim nesnesi (DAO) sınıflarını kullanarak, Microsoft Jet veritabanı altyapısı veya ODBC veri kaynakları gibi dış (Jet dışı) veri kaynakları, veritabanları ile çalışabilir.

   Ayrıca, MFC, Unicode kullanan uygulamalar yazmak için tam olarak etkinleştirilir ve çok baytlı karakter kümeleri (MBCS), özellikle çift baytlı karakter kümeleri (DBCS).

MFC belge genel bir kılavuz için bkz [genel MFC konuları](../mfc/general-mfc-topics.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)

