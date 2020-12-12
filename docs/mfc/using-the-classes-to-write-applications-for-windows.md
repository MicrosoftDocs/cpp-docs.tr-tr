---
description: 'Hakkında daha fazla bilgi edinin: Windows için uygulama yazmak için sınıfları kullanma'
title: Windows Uygulamaları Yazmak için Sınıfları Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
ms.openlocfilehash: b94155b565872b614efa291699cecbaf4770fdaa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322718"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>Windows Uygulamaları Yazmak için Sınıfları Kullanma

Birlikte getirildiğinde, Microsoft Foundation Class (MFC) kitaplığındaki sınıflar, Windows işletim sistemi için bir uygulama oluşturduğunuz bir "uygulama çerçevesi" oluşturur. Çok genel düzeyde, çerçeve bir uygulamanın iskektlerini tanımlar ve iskelet 'e yerleştirilebilecek standart Kullanıcı arabirimi uygulamaları sağlar. Programcı olarak işiniz, uygulamanıza özgü olan şeyler olan iskelet 'in kalanını doldurmanızı sağlar. Çok kapsamlı bir başlangıç uygulamasının dosyalarını oluşturmak için MFC Uygulama Sihirbazı ' nı kullanarak bir baş başlangıç yapabilirsiniz. Kullanıcı arabirimi öğelerinizi görsel olarak tasarlamak için Microsoft Visual C++ kaynak düzenleyicilerini, bu öğeleri koda bağlamak için komutları Sınıf Görünümü ve uygulamaya özgü mantığınızı uygulamak için sınıf kitaplığını kullanabilirsiniz.

MFC çerçevesinin sürüm 3,0 ve üzeri sürümleri, Microsoft Windows 95 ve üzeri ve Windows NT sürümleri ve üzeri 3,51 sürümleri dahil olmak üzere Win32 platformları için programlamayı destekler. MFC Win32 desteği çoklu iş parçacığı içerir. 16 bit programlama yapmanız gerekiyorsa 1,5 *x* sürümünü kullanın.

Bu makale ailesi, uygulama çerçevesi hakkında geniş bir genel bakış sunar. Ayrıca, uygulamanızı oluşturan büyük nesneleri ve bunların nasıl oluşturulduğunu da araştırır. Bu makalelerde ele alınan konular arasında şunlar bulunur:

- [Framework](../mfc/framework-mfc.md).

- Framework [üzerinde oluşturma](../mfc/building-on-the-framework.md)bölümünde açıklandığı gibi, Framework ve kodunuz arasındaki işçilikin bölümü.

- Uygulama düzeyi işlevselliğini kapsülleyen [uygulama sınıfı](../mfc/cwinapp-the-application-class.md).

- [Belge şablonlarının](../mfc/document-templates-and-the-document-view-creation-process.md) belgeleri ve bunlarla ilişkili görünümlerini ve çerçeve pencerelerini nasıl oluşturup yönetmediği.

- Tüm pencerelerin kök taban sınıfı olan [CWnd](../mfc/window-objects.md)sınıfı.

- Kalem ve fırçalar gibi [grafik nesneleri](../mfc/graphic-objects.md).

Framework 'ün diğer bölümleri şunlardır:

- [Pencere nesneleri: genel bakış](../mfc/window-objects.md)

- [İleti işleme ve eşleme](../mfc/message-handling-and-mapping.md)

- [CObject, MFC 'deki kök temel sınıfı](../mfc/using-cobject.md)

- [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

- [İletişim kutuları](../mfc/dialog-boxes.md)

- [Denetimler](../mfc/controls-mfc.md)

- [Denetim çubukları](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [Bellek yönetimi](../mfc/memory-management.md)

   Windows işletim sistemi için uygulama yazma avantajlarından faydalanmanın yanı sıra, MFC özellikle OLE bağlama ve ekleme teknolojisini kullanan uygulamalar yazmayı çok daha kolay hale getirir. Uygulamanızı bir OLE görsel düzenlemesini, bir OLE görsel düzenlemesi sunucusunu veya her ikisini birden yapabilir ve otomasyon ekleyerek diğer uygulamaların uygulamanızdaki nesneleri kullanmasını veya hatta uzaktan kullanılmasını sağlayabilirsiniz.

- [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

   OLE denetim geliştirme seti (CDK) artık çerçevesiyle tamamen tümleşiktir. Bu makalede, MFC ile ActiveX denetim geliştirmeye genel bakış sağlanır. (ActiveX denetimleri daha önce OLE denetimleri olarak bilinirdi.)

- [Veritabanı programlama](../data/data-access-programming-mfc-atl.md)

   MFC Ayrıca veri erişimi uygulamaları yazmayı kolaylaştıran iki veritabanı sınıfı kümesi sağlar. ODBC veritabanı sınıflarını kullanarak, bir açık veritabanı bağlantısı (ODBC) sürücüsü aracılığıyla veritabanlarına bağlanabilir, tablolardan kayıtlar ' ı seçebilir ve kayıt bilgilerini ekran biçiminde görüntüleyebilirsiniz. Veri erişim nesnesi (DAO) sınıflarını kullanarak, ODBC veri kaynakları dahil olmak üzere Microsoft Jet veritabanı altyapısı veya harici (Jet olmayan) veri kaynakları aracılığıyla veritabanlarıyla çalışabilirsiniz.

   Ayrıca, MFC Unicode ve çok baytlı karakter kümeleri (MBCS) kullanan uygulamaları yazmak için tamamen etkinleştirilir, özellikle çift baytlı karakter kümeleri (DBCS).

MFC belgelerine genel bir kılavuz için bkz. [genel MFC konuları](../mfc/general-mfc-topics.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC konuları](../mfc/general-mfc-topics.md)
