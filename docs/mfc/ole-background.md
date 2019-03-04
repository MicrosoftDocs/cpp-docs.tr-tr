---
title: OLE Arka Planı
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
ms.openlocfilehash: 2501373c2ff5904343a6522e4fb18663f5de3843
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294427"
---
# <a name="ole-background"></a>OLE Arka Planı

OLE öğeleri ya da "nesneler" içeren belgeleri oluşturmak ve düzenlemek kullanıcılara bir mekanizma birden çok uygulama tarafından oluşturulur.

> [!NOTE]
>  OLE nesne bağlama ve katıştırma kısaltması başlangıçta oluştu. Bununla birlikte, artık OLE adlandırılır. OLE bağlama ve katıştırma için ilgili olmayan bölümleri artık etkin teknoloji bir parçasıdır.

OLE belgeleri, bileşik belgeler, daha önce çağırılır, çeşitli türlerdeki veri veya bileşenleri sorunsuzca tümleştirin. Ses klipleri yürütmesini sağlayan, elektronik tablolar ve bit eşlemler OLE belgelerde bulunan bileşenler için tipik örnekleridir. OLE uygulamanızda destekleyen OLE belgeleri farklı uygulamalar arasında geçiş hakkında endişelenmeden kullanmalarına olanak sağlar; OLE geçişi sizin için yapar.

Bileşik belgeler oluşturmak için bir kapsayıcı uygulaması ve bir sunucu uygulaması veya bileşen uygulama kapsayıcı belge öğeleri oluşturmak için kullanırsınız. Yazdığınız herhangi bir uygulama bir kapsayıcı, bir sunucu veya her ikisi de olabilir.

OLE uygulamaları arasında sorunsuz etkileşim hedefe hepsi birçok farklı kavramları kullanmaktadır. Bu alanlar şunları içerir:

- Bağlama ve katıştırma

   Bağlama ve katıştırma başka bir uygulamada oluşturulan bir OLE belgesi içinde oluşturulan öğelerini depolamak için iki yöntemlerdir. İkisi arasındaki farklar hakkında genel bilgi için bkz [OLE arka planı: Bağlama ve katıştırma](../mfc/ole-background-linking-and-embedding.md). Daha ayrıntılı bilgi için makalelerine bakın [kapsayıcıları](../mfc/containers.md) ve [sunucuları](../mfc/servers.md).

- Yerinde etkinleştirme (görsel düzenleme)

   Bağlam içinde gömülü bir öğe kapsayıcı belgesinin etkinleştirme yerinde etkinleştirme veya görsel düzenleme adı verilir. Kapsayıcı uygulamasının arabirimi gömülü bir öğe oluşturan bileşen uygulama özelliklerini değiştirir. Öğe için gerçek veri bağlantısı içeren bir uygulama bağlamında dışında ayrı bir dosyada bulunduğundan bağlantılı öğeleri hiçbir zaman yerinde etkinleştirilir. Yerinde etkinleştirme hakkında daha fazla bilgi için bkz [etkinleştirme](../mfc/activation-cpp.md).

   > [!NOTE]
   > Bağlama ve katıştırma ve yerinde etkinleştirme OLE görsel düzenleme ana özellikleri sağlar.

- Bir uygulamayı başka bir uygulama sürücü Otomasyon Otomasyonu sağlar. Sürüş uygulama bir otomasyon istemci olarak bilinir ve odaklı uygulamayı Otomasyon sunucusu ya da Otomasyon bileşeni bilinir. Makaleleri Otomasyonu hakkında daha fazla bilgi için bkz. [Otomasyon istemcileri](../mfc/automation-clients.md) ve [otomasyon sunucuları](../mfc/automation-servers.md).

   > [!NOTE]
   > Otomasyon OLE hem etkin teknoloji bağlamlarında çalışır. Herhangi bir nesne üzerinde COM tabanlı otomatik hale getirebilirsiniz

- Bileşik dosyalar

   Bileşik dosyalar bileşik belge OLE uygulamaları için yapılandırılmış depolama basitleştiren bir standart dosya biçimi sağlayın. Bileşik bir dosya içindeki Pano'yu dizinleri özelliklerinin çoğu ve birçok özellik dosyalarının akışları sahiptir. Bu teknoloji, yapılandırılmış depolama olarak da adlandırılır. Bileşik dosyalar hakkında daha fazla bilgi için bkz [kapsayıcıları: Bileşik dosyalar](../mfc/containers-compound-files.md).

- Tekdüzen veri aktarımı

   Tekdüzen veri aktarımı (UDT) gönderilen ve alınan verileri aktarmak için seçilen yöntemin gerçek bağımsız olarak standart bir biçimde izin arabirimleri kümesidir. UDT forms tarafından temel veri aktarımları sürükleyip bırakın. UDT artık Pano ve dinamik veri değişimine (DDE) gibi mevcut Windows veri aktarımı için temel olarak görev yapar. UDT hakkında daha fazla bilgi için bkz [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md).

- Sürükleme ve Bırakma

   Sürükle ve bırak arasında windows uygulama içinde veya bir uygulamadaki tek bir pencere içinde bile, uygulamalar arasında veri aktarmak için kullanımı kolay, doğrudan işleme bir yöntem olduğundan. Aktarılacak veriler seçilen ve istenen hedefe sürüklediğiniz. Sürükle ve bırak Tekdüzen veri aktarımını dayanır. Sürükleme ve bırakma hakkında daha fazla bilgi için bkz [sürükle ve bırak](../mfc/drag-and-drop-ole.md).

- Bileşen Nesne modeli

   Bileşen Nesne Modeli (COM) OLE nesneleri birbirleri ile iletişim kurarken kullanılan altyapı sağlar. MFC OLE sınıfları, COM programcısı için basitleştirin. COM nesneleri temelini oluşturan OLE hem etkin teknoloji olduğundan COM etkin teknoloji bir parçasıdır. COM hakkında daha fazla bilgi için bkz: [Etkin Şablon kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md) konuları.

Daha da önemlisi OLE konuların bazıları aşağıdaki makalelerde ele alınmıştır:

- [OLE arka planı: Bağlama ve katıştırma](../mfc/ole-background-linking-and-embedding.md)

- [OLE arka planı: Kapsayıcılar ve sunucular](../mfc/ole-background-containers-and-servers.md)

- [OLE arka planı: Uygulama stratejileri](../mfc/ole-background-implementation-strategies.md)

- [OLE arka planı: MFC uygulaması](../mfc/ole-background-mfc-implementation.md)

Yukarıdaki makalelerinde bulunamadı genel OLE bilgi için MSDN'de OLE arayın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)
