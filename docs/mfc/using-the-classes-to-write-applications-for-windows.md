---
title: "Windows uygulamaları yazmak için sınıfları kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a8edcabee2f835bd3a3acd0ff3789690764c397
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>Windows Uygulamaları Yazmak için Sınıfları Kullanma
Birlikte ele alındığında, "Windows işletim sistemi için uygulama derleme bir uygulama çerçevesi," Microsoft Foundation Class (MFC) Kitaplığı'nda sınıfları oluşturur. Bir çok genel düzeyde framework uygulamanın çatıyı tanımlar ve çatıyı yerleştirilebilir standart kullanıcı arabirimi uygulamalarını sağlar. İşinizi Programcı olarak çatıyı geri kalanı uygulamanıza özgü olan şeyi olduğu doldurmaktır. Bir başlangıç dosyalarını çok kapsamlı başlangıç uygulaması oluşturmak için MFC Uygulama Sihirbazı'nı kullanarak alabilirsiniz. Microsoft Visual C++ kaynak düzenleyicileri sınıfı görünüm komutları kod ve sınıf kitaplığı konusu öğelerin bağlanmak için kullanıcı arabirimi öğeleri görsel olarak tasarlamak için uygulamaya özgü mantığını uygulamak için kullanın.  
  
 Sürüm 3.0 ve sonraki MFC framework'ün de dahil olmak üzere Microsoft Windows 95 ve daha sonra Win32 platformları için programlama ve Windows NT 3.51 ve sonraki sürümleri destekler. MFC Win32 destek çoklu iş parçacığı içerir. Kullanım sürüm 1.5*x* 16-bit programlama gerçekleştirmeniz gerekiyorsa.  
  
 Bu makaleler ailesi uygulama çerçevesi kapsamlı bir genel bakış sunar. Ayrıca, uygulamanızı ve nasıl oluşturulduğunu oluşturan büyük nesneler araştırır. Bu makalede ele alınan konulardan arasında aşağıda verilmiştir:  
  
-   [Framework](../mfc/framework-mfc.md).  
  
-   İşçi çerçevesi ve kodunuz, açıklandığı gibi arasında bölme [Framework'te derleme](../mfc/building-on-the-framework.md).  
  
-   [Uygulama sınıfı](../mfc/cwinapp-the-application-class.md), uygulama düzeyinde işlevselliği kapsar.  
  
-   Nasıl [belge şablonları](../mfc/document-templates-and-the-document-view-creation-process.md) oluşturmak ve belgeleri ve bunların ilişkili görünümleri yönetme ve çerçeve windows.  
  
-   Sınıf [CWnd](../mfc/window-objects.md), tüm windows kök taban sınıfı.  
  
-   [Grafik nesneleri](../mfc/graphic-objects.md)kalemler ve fırçalar gibi.  
  
 Framework'ün diğer bölümleri içerir:  
  
-   [Pencere nesneleri: genel bakış](../mfc/window-objects.md)  
  
-   [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)  
  
-   [CObject, MFC'de kök taban sınıfı](../mfc/using-cobject.md)  
  
-   [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)  
  
-   [İletişim Kutuları](../mfc/dialog-boxes.md)  
  
-   [Denetimler](../mfc/controls-mfc.md)  
  
-   [Denetim Çubukları](../mfc/control-bars.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Bellek Yönetimi](../mfc/memory-management.md)  
  
     Windows işletim sistemi için uygulamalar yazma bir avantajı vermiş yanı sıra, MFC de özellikle bağlama ve katıştırma teknolojisi OLE kullanan uygulamalar yazmak kolaylaşır. Uygulamanızı bir OLE görsel kapsayıcı, OLE görsel düzenleme sunucusu ya da her ikisini de düzenleme yapabileceğiniz ve böylece diğer uygulamaları nesneleri uygulamanızdan kullanın veya hatta uzaktan sürücü Otomasyon ekleyebilirsiniz.  
  
-   [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)  
  
     OLE denetim Geliştirme Seti (CDK) şimdi framework ile tamamen tümleşiktir. Bu makale ailesi ile MFC ActiveX denetimi geliştirme genel bir bakış sağlar. (ActiveX denetimlerini önceden OLE denetimleri bilinirdi.)  
  
-   [Veritabanı programlama](../data/data-access-programming-mfc-atl.md)  
  
     MFC ayrıca yazma veri erişimi basitleştirmek veritabanı sınıfları iki kümesi sağlayan uygulamalar. ODBC veritabanı sınıflarını kullanma, açık veritabanı bağlantısı (ODBC) sürücüsü aracılığıyla veritabanlarına bağlanmak, seçebilir kayıtları tablolardan ve kayıt bilgilerini görüntülemek bir ekran form. Veri erişim nesnesi (DAO) sınıfları kullanma, Microsoft Jet veritabanı altyapısı veya ODBC veri kaynakları da dahil olmak üzere, dış (Jet dışı) veri kaynakları aracılığıyla veritabanları ile çalışabilirsiniz.  
  
     Ayrıca, Unicode kullanan uygulamaları yazmak için MFC tam olarak etkinleştirilir ve birden çok baytlı karakter kümeleri (MBCS), özellikle çift bayt karakter kümeleri (DBCS).  
  
 MFC belge genel bir kılavuzu için bkz [genel MFC konuları](../mfc/general-mfc-topics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC Konuları](../mfc/general-mfc-topics.md)

