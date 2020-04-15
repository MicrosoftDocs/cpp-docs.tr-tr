---
title: OLE Arka Planı
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
ms.openlocfilehash: f7d65f48c1af678f6626ba7d315ceb735d3e960a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364514"
---
# <a name="ole-background"></a>OLE Arka Planı

OLE, kullanıcıların birden çok uygulama tarafından oluşturulan öğeleri veya "nesneleri" içeren belgeler oluşturmasına ve düzenlemesine olanak tanıyan bir mekanizmadır.

> [!NOTE]
> OLE aslında Nesne Bağlama ve Katıştırma için bir kısaltma ydı. Ancak, şimdi OLE olarak adlandırılır. OLE'nin bağlantı ve katıştırma ile ilgili olmayan bölümleri artık Active teknolojisinin bir parçasıdır.

OLE belgeleri, tarihsel olarak bileşik belgeler olarak adlandırılır, çeşitli veri türlerini veya bileşenleri sorunsuz bir şekilde tümleştirir. Ses klipleri, elektronik tablolar ve bit eşlemler, OLE belgelerinde bulunan bileşenlerin tipik örnekleridir. Uygulamanızda OLE'yi desteklemek, kullanıcılarınızın farklı uygulamalar arasında geçiş yapma endişesi duymadan OLE belgelerini kullanmasına olanak tanır; OLE sizin için anahtarlama yapar.

Bileşik belgeler oluşturmak için bir kapsayıcı uygulaması ve kapsayıcı belge içindeki öğeleri oluşturmak için bir sunucu uygulaması veya bileşen uygulaması kullanın. Yazdığınız herhangi bir uygulama bir kapsayıcı, sunucu veya her ikisi de olabilir.

OLE, tüm uygulamalar arasında sorunsuz etkileşim hedefine doğru çalışan birçok farklı kavramları birleştirir. Bu alanlar şunlardır:

- Bağlama ve Katıştırma

   Bağlama ve katıştırma, başka bir uygulamada oluşturulan bir OLE belgesiiçinde oluşturulan öğeleri depolamak için iki yöntemdir. İkisi arasındaki farklar hakkında genel bilgi için, makale [ole Arka plan bakın: Bağlama ve Katıştırma.](../mfc/ole-background-linking-and-embedding.md) Daha ayrıntılı bilgi için, makaleler [Kapsayıcılar](../mfc/containers.md) ve [Sunucular](../mfc/servers.md)bakın.

- Yerinde Etkinleştirme (Görsel Düzenleme)

   Katıştırılmış bir öğeyi kapsayıcı belgesi bağlamında etkinleştirme, yerinde etkinleştirme veya görsel düzenleme olarak adlandırılır. Kapsayıcı uygulamanın arabirimi, katıştırılmış öğeyi oluşturan bileşen uygulamasının özelliklerini birleştirmek için değişir. Öğenin gerçek verileri bağlantıyı içeren uygulama bağlamından ayrı bir dosyada bulunduğundan, bağlantılı öğeler hiçbir zaman yerinde etkinleştirilmez. Yerinde etkinleştirme hakkında daha fazla bilgi için [Etkinleştirme](../mfc/activation-cpp.md)makalesine bakın.

   > [!NOTE]
   > Bağlama ve katıştırma ve yerinde etkinleştirme OLE görsel düzenlemenin ana özelliklerini sağlar.

- Otomasyon Otomasyonu, bir uygulamanın başka bir uygulamayı yönlendirmesine olanak tanır. Sürüş uygulaması bir otomasyon istemcisi olarak bilinir ve çalıştırılan uygulama bir otomasyon sunucusu veya otomasyon bileşeni olarak bilinir. Otomasyon hakkında daha fazla bilgi [için, makalelerI Otomasyon İstemciler](../mfc/automation-clients.md) ve [Otomasyon Sunucuları](../mfc/automation-servers.md)bakın.

   > [!NOTE]
   > Otomasyon hem OLE hem de Active teknoloji bağlamlarında çalışır. Com'a dayalı herhangi bir nesneyi otomatikleştirebilirsiniz.

- Bileşik Dosyalar

   Bileşik dosyalar, OLE uygulamaları için bileşik belgelerin yapılandırılmış şekilde depolanmasını kolaylaştıran standart bir dosya biçimi sağlar. Bileşik dosya içinde, depolama dizinleri ve akışları birçok özelliklere sahip dosyaların birçok özelliği vardır. Bu teknoloji aynı zamanda yapılandırılmış depolama denir. Bileşik dosyalar hakkında daha fazla bilgi için, makale [Kapsayıcılar bakın: Bileşik Dosyalar](../mfc/containers-compound-files.md).

- Tek Düzen Veri Aktarımı

   Tek düzen Veri Aktarımı (UDT), verilerin aktarılması için seçilen gerçek yöntemden bağımsız olarak, verilerin standart bir şekilde gönderilmesine ve alınmasına olanak tanıyan bir arabirim kümesidir. UDT sürükle ve bırak'a göre veri aktarımlarının temelini oluşturur. UDT artık Pano ve dinamik veri alışverişi (DDE) gibi varolan Windows veri aktarımına temel teşkil etmektedir. UDT hakkında daha fazla bilgi için [Veri Nesneleri ve Veri Kaynakları (OLE) makalesine](../mfc/data-objects-and-data-sources-ole.md)bakın.

- Sürükleme ve Bırakma

   Sürükle ve bırak, uygulamalar arasında, bir uygulama içindeki pencereler arasında ve hatta bir uygulamada tek bir pencere içinde veri aktarmak için kullanımı kolay, doğrudan işleme tekniğidir. Aktarılacak veriler seçilir ve istenilen hedefe sürüklenir. Sürükle ve bırak tek düzen veri aktarımına dayanır. Sürükle ve bırak hakkında daha fazla bilgi için [Sürükle ve Bırak](../mfc/drag-and-drop-ole.md)makalesine bakın.

- Bileşen Nesne Modeli

   Bileşen Nesne Modeli (COM), OLE nesneleri birbiriyle iletişim kurduğunda kullanılan altyapıyı sağlar. MFC OLE sınıfları programcı için COM'u basitleştirir. COM, Hem OLE hem de Active teknolojisinin altında yatan COM nesneleri olduğundan, Active teknolojisinin bir parçasıdır. COM hakkında daha fazla bilgi için [Etkin Şablon Kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md) konularına bakın.

Bazı daha önemli OLE konuları aşağıdaki makalelerde ele alınmıştır:

- [OLE Arka Planı: Bağlama ve Katıştırma](../mfc/ole-background-linking-and-embedding.md)

- [OLE Arka Planı: Kapsayıcılar ve Sunucular](../mfc/ole-background-containers-and-servers.md)

- [OLE Arka Planı: Uygulama Stratejileri](../mfc/ole-background-implementation-strategies.md)

- [OLE Arka Planı: MFC Uygulaması](../mfc/ole-background-mfc-implementation.md)

Yukarıdaki makalelerde bulunmayan genel OLE bilgileri için MSDN'de OLE'yi arayın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)
