---
title: "OLE arka planı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e40fb7d2e58fa672196853e1edb9d5577c2cb14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background"></a>OLE Arka Planı
OLE öğeleri ya da "nesneler" içeren belgeleri oluşturmak ve düzenlemek kullanıcılara bir mekanizma birden çok uygulama tarafından oluşturulur.  
  
> [!NOTE]
>  OLE özgün nesne bağlama ve katıştırma kısaltması oluştu. Ancak, bunu şimdi OLE bilinir. Bağlama ve katıştırma ilgili olmayan OLE bölümlerini şimdi etkin teknoloji parçasıdır.  
  
 OLE belgeleri, geçmişte bileşik belgeler adlı çeşitli türde veri veya bileşenleri sorunsuz şekilde tümleşir. Ses klipleri, elektronik tablolar ve bit eşlemleri OLE belgelerde bulunan bileşenleri için tipik örnektir. OLE uygulamanızda destekleme farklı uygulamalar arasında geçiş yapma hakkında endişelenmeden OLE belgeleri kullanmalarına olanak sağlar; OLE sizin için geçiş yapar.  
  
 Bileşik belgeler oluşturmak için bir kapsayıcı uygulaması ve bir sunucu uygulaması veya kapsayıcı belge öğeleri oluşturmak için bileşen uygulama kullanın. Yazdığınız herhangi bir uygulama, bir kapsayıcı, bir sunucu veya her ikisi de olabilir.  
  
 OLE tüm uygulamaları arasında sorunsuz etkileşim amacı doğru çalıştığını birçok farklı kavramları içerir. Bu alanlar şunlardır:  
  
 Bağlama ve katıştırma  
 Bağlama ve katıştırma başka bir uygulamada oluşturulan OLE belge içinde oluşturulan öğeleri depolamak için iki yöntemleridir. İkisi arasındaki farklar hakkında genel bilgi için bkz: [OLE arka planı: bağlama ve katıştırma](../mfc/ole-background-linking-and-embedding.md). Daha ayrıntılı bilgi için makalelerine bakın [kapsayıcıları](../mfc/containers.md) ve [sunucuları](../mfc/servers.md).  
  
 Yerinde etkinleştirme (görsel düzenleme)  
 Kapsayıcı belge bağlamında katıştırılmış bir öğe etkinleştirme yerinde etkinleştirme veya görsel düzenleme çağrılır. Kapsayıcı uygulamanın arabirimi katıştırılmış öğesini oluşturan bileşen uygulamanın özelliklerini içerecek şekilde değiştirir. Gerçek veri öğesi için bağlantı içeren bir uygulama bağlamında dışında ayrı bir dosyada içerdiğinden bağlantılı öğeler hiçbir zaman yerinde etkinleştirilir. Yerinde etkinleştirme hakkında daha fazla bilgi için bkz: [etkinleştirme](../mfc/activation-cpp.md).  
  
> [!NOTE]
>  Bağlama ve katıştırma ve yerinde etkinleştirme OLE görsel düzenleme ana özellikler sağlar.  
  
 Otomatikleştirme  
 Başka bir uygulama sürücü bir uygulama sağlar. Yönlendirmeli uygulama bir Otomasyon istemcisi olarak bilinir ve güdümlü uygulama bir Otomasyon sunucusu ya da Otomasyon bileşeni bilinir. Makaleleri Otomasyonu hakkında daha fazla bilgi için bkz: [Otomasyon istemcileri](../mfc/automation-clients.md) ve [otomasyon sunucuları](../mfc/automation-servers.md).  
  
> [!NOTE]
>  Otomasyon OLE ve etkin teknoloji bağlamlarda çalışır. Herhangi bir nesne üzerinde COM tabanlı otomatik hale getirebilirsiniz  
  
 Bileşik dosyalar  
 Bileşik dosyalar bileşik belgeler OLE uygulamaları için yapılandırılmış depolama basitleştiren bir standart dosya biçimi sağlayın. Bileşik dosya içinde depolarını dizinlerin birçok özellik ve dosyaları özelliklerinin çoğu akışları sahiptir. Bu teknoloji, yapılandırılmış depolama olarak da adlandırılır. Bileşik dosyalar hakkında daha fazla bilgi için bkz: [kapsayıcılar: bileşik dosyalar](../mfc/containers-compound-files.md).  
  
 Tekdüzen veri aktarımı  
 Tekdüzen veri aktarımı (UDT), gönderilen ve verileri aktarmak için seçilen gerçek yöntemi bağımsız olarak standart bir şekilde alınan verilerin izin arabirimleri kümesidir. UDT forms tarafından veri temelini aktarır sürükleyin ve bırakın. UDT, şimdi Pano ve dinamik veri değişimi (DDE) gibi var olan Windows veri aktarımı için temel olarak görev yapar. UDT hakkında daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Sürükleme ve Bırakma  
 Sürükle ve bırak windows uygulama içinde veya bir uygulamanın tek bir pencerede içinde bile arasında uygulamalar arasında veri aktarmak için kullanımı kolay, doğrudan düzenlemesi bir teknik olur. Aktarılacak veri seçilir ve istenen hedefe sürüklenebilir. Sürükle ve bırak Tekdüzen veri aktarımını dayanır. Sürükleme ve bırakma hakkında daha fazla bilgi için bkz: [sürükle ve bırak](../mfc/drag-and-drop-ole.md).  
  
 Bileşen Nesne modeli  
 Bileşen Nesne Modeli (COM) OLE nesneleri birbirleri ile iletişim kurarken kullanılan altyapı sağlar. MFC OLE sınıfları için programcı COM basitleştirin. COM nesneleri OLE ve etkin teknoloji temelini oluşturan olduğundan COM etkin teknoloji bir parçasıdır. COM hakkında daha fazla bilgi için bkz: [Etkin Şablon kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md) Konular.  
  
 Daha da önemlisi OLE konuların bazıları aşağıdaki makalelerde ele alınmaktadır:  
  
-   [OLE Arka Planı: Bağlama ve Katıştırma](../mfc/ole-background-linking-and-embedding.md)  
  
-   [OLE Arka Planı: Kapsayıcılar ve Sunucular](../mfc/ole-background-containers-and-servers.md)  
  
-   [OLE Arka Planı: Uygulama Stratejileri](../mfc/ole-background-implementation-strategies.md)  
  
-   [OLE Arka Planı: MFC Uygulaması](../mfc/ole-background-mfc-implementation.md)  
  
 Yukarıdaki makalelerin bulunamadı genel OLE bilgi için MSDN OLE arayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)

