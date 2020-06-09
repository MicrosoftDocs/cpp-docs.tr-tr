---
title: OLE Arka Planı
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, about OLE
ms.assetid: 5f654eb5-66b1-40c9-9215-bb85356a67f8
ms.openlocfilehash: 96ece9a2a5be6ea29c95e17e81f6ce4adbfd4c0b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624173"
---
# <a name="ole-background"></a>OLE Arka Planı

OLE, kullanıcıların öğeleri veya birden çok uygulama tarafından oluşturulan "nesneleri" içeren belgeler oluşturmalarına ve düzenlemesine izin veren bir mekanizmadır.

> [!NOTE]
> OLE ilk olarak nesne bağlama ve ekleme için bir kısaltmıştı. Ancak, artık OLE olarak adlandırılır. OLE 'nin bağlama ve ekleme ile ilgili olmayan bölümleri artık etkin teknolojinin bir parçasıdır.

Geçmişte bileşik belgeler olarak adlandırılan OLE belgeleri, çeşitli veri türlerini veya bileşenleri sorunsuzca tümleştirin. Ses klipleri, elektronik tablolar ve bit eşlemler, OLE belgelerinde bulunan bileşenlerin tipik örnekleridir. Uygulamanızdaki OLE destekleme, kullanıcılarınızın farklı uygulamalar arasında geçiş yapma konusunda endişelenmeden OLE belgelerini kullanmasına izin verir; OLE, sizin için geçiş yapar.

Kapsayıcı belge içinde öğeleri oluşturmak için bileşik belgeler ve bir sunucu uygulaması veya bileşen uygulaması oluşturmak üzere bir kapsayıcı uygulaması kullanırsınız. Yazdığınız herhangi bir uygulama bir kapsayıcı, sunucu veya her ikisi de olabilir.

OLE, uygulamalar arasında sorunsuz etkileşim amacını karşılayan birçok farklı kavram içerir. Bu alanlara aşağıdakiler dahildir:

- Bağlama ve Katıştırma

   Bağlama ve katıştırma, başka bir uygulamada oluşturulmuş bir OLE belgesi içinde oluşturulan öğeleri depolamanın iki yöntemi vardır. İkisi arasındaki farklılıklar hakkında genel bilgi için [OLE arka planı: bağlama ve ekleme](ole-background-linking-and-embedding.md)makalesine bakın. Daha ayrıntılı bilgi için bkz. Makaleler [kapsayıcılar](containers.md) ve [sunucular](servers.md).

- Yerinde etkinleştirme (görsel düzenlemeler)

   Kapsayıcı belge bağlamında gömülü bir öğenin etkinleştirilmesi yerinde etkinleştirme veya görsel düzenlemeler olarak adlandırılır. Kapsayıcı uygulamasının arabirimi, katıştırılmış öğeyi oluşturan bileşen uygulamasının özelliklerini içerecek şekilde değişir. Öğenin gerçek verileri, bağlantıyı içeren uygulamanın bağlamı dışında ayrı bir dosyada bulunduğundan bağlantılı öğeler hiçbir yerde etkinleştirilmez. Yerinde etkinleştirme hakkında daha fazla bilgi için [etkinleştirme](activation-cpp.md)makalesine bakın.

   > [!NOTE]
   > Bağlama ve ekleme ve yerinde etkinleştirme, OLE görsel düzenlemenin ana özelliklerini sağlar.

- Otomasyon Otomasyonu, bir uygulamanın başka bir uygulamayı kullanmasına izin verir. Çalışan uygulama bir Otomasyon istemcisi olarak bilinir ve çalıştırılmakta olan uygulama bir Otomasyon sunucusu ya da otomasyon bileşeni olarak bilinir. Otomasyon hakkında daha fazla bilgi için bkz. Makale [Otomasyonu istemcileri](automation-clients.md) ve [Otomasyon sunucuları](automation-servers.md).

   > [!NOTE]
   > Otomasyon hem OLE hem de Active Technology bağlamlarında çalışmaktadır. Herhangi bir nesneyi COM 'a göre otomatikleştirebilirsiniz.

- Bileşik Dosyalar

   Bileşik dosyalar, OLE uygulamaları için bileşik belgelerin yapılandırılmış depolanmasını kolaylaştıran standart bir dosya biçimi sağlar. Bileşik bir dosya içinde, depolama alanları dizinlerin birçok özelliğine sahiptir ve akışlar birçok dosya özelliğine sahiptir. Bu teknoloji, yapılandırılmış depolama olarak da adlandırılır. Bileşik dosyalar hakkında daha fazla bilgi için bkz. [kapsayıcı: bileşik dosyalar](containers-compound-files.md).

- Tekdüzen Veri Aktarımı

   Tekdüzen Veri Aktarımı (UDT), verilerin aktarılması için seçilen gerçek yöntemden bağımsız olarak, verilerin standart bir biçimde gönderilmesine ve alınmasına izin veren bir arabirim kümesidir. UDT, sürükle ve bırak ile veri aktarımlarının temelini oluşturur. UDT artık, pano ve dinamik veri değişimi (DDE) gibi mevcut Windows veri aktarımı için temel görevi görür. UDT hakkında daha fazla bilgi için bkz. [veri nesneleri ve veri kaynakları (OLE)](data-objects-and-data-sources-ole.md).

- Sürükleme ve Bırakma

   Sürükle ve bırak, uygulamalar arasında veri aktarmak için kullanımı kolay, doğrudan işleme tekniğidir. bir uygulamadaki pencereler arasında, hatta bir uygulamadaki tek bir pencere içinde. Aktarılacak veriler seçilir ve istenen hedefe sürüklenir. Sürükleyip bırakma, tek düzen veri aktarımına dayalıdır. Sürükle ve bırak hakkında daha fazla bilgi için [sürükle ve bırak](drag-and-drop-ole.md)makalesine bakın.

- Bileşen nesne modeli

   Bileşen nesne modeli (COM), OLE nesneleri birbirleriyle iletişim kurduğunda kullanılan altyapıyı sağlar. MFC OLE sınıfları programcı için COM 'yi basitleştirir. Com, etkin teknolojinin bir parçasıdır, çünkü COM nesneleri hem OLE hem de etkin teknolojiden oluşur. COM hakkında daha fazla bilgi için bkz. [Etkin Şablon kitaplığı (ATL)](../atl/active-template-library-atl-concepts.md) konuları.

Daha önemli OLE konularından bazıları aşağıdaki makalelerde ele alınmıştır:

- [OLE Arka Planı: Bağlama ve Katıştırma](ole-background-linking-and-embedding.md)

- [OLE Arka Planı: Kapsayıcılar ve Sunucular](ole-background-containers-and-servers.md)

- [OLE Arka Planı: Uygulama Stratejileri](ole-background-implementation-strategies.md)

- [OLE Arka Planı: MFC Uygulaması](ole-background-mfc-implementation.md)

Yukarıdaki makalelerde bulunmayan genel OLE bilgileri için MSDN 'de OLE aratın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE](ole-in-mfc.md)
