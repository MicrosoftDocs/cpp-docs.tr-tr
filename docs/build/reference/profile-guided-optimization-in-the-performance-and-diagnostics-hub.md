---
title: Profil temelli iyileştirme performans ve tanılama hub'ı | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: dc3a1914-dbb6-4401-bc63-10665a8c8943
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8a586ef48f87f90dd5f191f9fcaea6f30af5c56
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="profile-guided-optimization-in-the-visual-studio-2013-performance-and-diagnostics-hub"></a>Profil temelli iyileştirme Visual Studio 2013 performans ve tanılama hub'ı

Profil temelli iyileştirme Visual C++ performans ve tanılama hub'ı eklenti için Visual Studio 2013 kullanıyorsanız, geliştiriciler için profil temelli iyileştirme deneyimi kolaylaştırır. Yapabilecekleriniz [eklentiyi karşıdan](http://go.microsoft.com/fwlink/p/?LinkId=327915) Visual Studio Web sitesinden. Eklentisi, Visual Studio'nun daha yeni sürümleri desteklenmez.

Profil temelli iyileştirme (PGO) yardımcı olur şekilde, kullanıcılar için en iyi duruma getirilir x86 hem x64 yerel uygulamalar derlemeleri oluşturma etkileşim. PGO olan çok adımlı bir işlemi: profil oluşturma için izlenmiş olan bir uygulama yapı oluşturmak ve ardından "eğitim." gerçekleştirin Diğer bir deyişle, ortak kullanıcı etkileşim senaryoları Araçlı uygulamayı çalıştırın. Yakalanan profil oluşturma verileri Kaydet ve yeniden bütün program iyileştirmesi kılavuza sonuçları kullanarak uygulamanızı derleyin. Bu adımları ayrı ayrı Visual Studio'da veya komut satırında gerçekleştirebileceğiniz rağmen eklenti PGO merkezi hale getirir ve işlemini basitleştirir. Eklenti PGO tüm gerekli seçenekleri ayarlar, her adımda size rehberlik eder, analiz gösterir ve boyutu veya hızı için her işlevi en iyi duruma getirmek için yapı yapılandırmak için sonuçları kullanır. Eklenti PGO Ayrıca uygulama eğitim yeniden çalıştırmak ve kodunuzu değiştirmek gibi yapı en iyi duruma getirme verileri güncelleştirmek kolaylaştırır.

## <a name="prerequisites"></a>Önkoşullar

Gerekir [eklenti PGO karşıdan](http://go.microsoft.com/fwlink/p/?LinkId=327915) ve performans ve tanılama hub'ı kullanmadan önce Visual Studio'da yükleyin.

## <a name="walkthrough-using-the-pgo-plug-in-to-optimize-an-app"></a>İzlenecek yol: bir uygulamayı iyileştirmek için eklenti PGO kullanma

İlk olarak, Visual Studio ile temel bir Win32 masaüstü uygulaması oluşturacaksınız. En iyi duruma getirmek istediğiniz yerel bir uygulama zaten varsa, bunu kullanın ve bu adımı atlayın.

### <a name="to-create-an-app"></a>Bir uygulama oluşturmak için

1. Menü çubuğunda seçin **dosya**, **yeni**, **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda, genişletin **yüklü**, **şablonları**, **Visual C++** ve ardından  **MFC**.

1. Orta bölmede seçin **MFC uygulaması**.

1. Proje için bir ad belirtin — örneğin, **SamplePGOProject**— içinde **adı** kutusu. Seçin **Tamam** düğmesi.

1. Üzerinde **genel bakış** sayfasında **MFC Uygulama Sihirbazı'nı** iletişim kutusunda, seçin **son** düğmesi.

Ardından, yayın PGO yapı ve eğitim adımlar için hazır, uygulamanızın derleme yapılandırmasını ayarlayın.

### <a name="to-set-the-build-configuration"></a>Derleme yapılandırması ayarlamak için

1. Menü çubuğunda seçin **yapı**, **Configuration Manager**.

1. İçinde **Configuration Manager** iletişim kutusunda, seçin **etkin çözüm yapılandırması** açılan düğmesine ve select **sürüm**. Seçin **Kapat** düğmesi.

Performans ve tanılama hub'ı açın — menü çubuğunda seçin **Çözümle**, **performans ve tanılama**. Bu proje türü için kullanılabilir olan araçlarına sahip bir tanılama oturumu sayfasını açar.

![Performans ve tanılama hub'ı PGO](../../build/reference/media/pgofig0hub.png "PGOFig0Hub")

İçinde **kullanılabilen Araçlar**seçin **profil temelli iyileştirme** onay kutusu. Seçin **Başlat** eklenti PGO başlamak için Başlat.

![PGO giriş sayfası](../../build/reference/media/pgofig1start.png "PGOFig1Start")

**Profil temelli iyileştirme** sayfasını, uygulamanızın performansını artırmak için eklenti kullandığı adımları açıklar. Seçin **Başlat** düğmesi.

![PGO araçları sayfa](../../build/reference/media/pgofig2instrument.png "PGOFig2Instrument")

İçinde **Araçları** bölümünde, kullandığınız **eğitim başlangıçta etkin** seçeneği, uygulamanızın başlatma aşaması eğitim bir parçası olarak dahil edilip edilmeyeceğini seçin. Bu seçenek seçilmezse, eğitim verileri eğitim açıkça etkinleştirinceye kadar çalışan Araçlı uygulamada kayıtlı değil.

Seçin **Gereci** özel bir derleyici seçenekleri kümesiyle ve uygulamanızı oluşturmak için düğmesi. Derleyici araştırma yönergeleri oluşturulan kodda ekler. Bu yönergeler eğitim aşamasında profil oluşturma verilerini kaydeder.

![PGO Araçlı derleme sayfa](../../build/reference/media/pgofig3build.PNG "PGOFig3Build")

Uygulamanızın Araçlı yapı tamamlandıktan sonra uygulamayı otomatik olarak başlatılır.

Derleme sırasında hatalar veya uyarılar meydana gelirse, bunları düzeltin ve ardından **yeniden derleme** Araçlı derleme yeniden başlatmak için.

Uygulamanızı başlatıldığında, kullanabileceğiniz **Başlat eğitim** ve **duraklatma eğitim** içinde bağlar **eğitim** zaman bilgi profil kaydedilen denetlemek için bölüm. Kullanabileceğiniz **durdurmak uygulama** ve **uygulamayı Başlat** bağlantılar durdurun ve uygulamayı yeniden başlatın.

![PGO eğitim sayfa](../../build/reference/media/pgofig4training.PNG "PGOFig4Training")

Eğitim sırasında eklenti PGO kodu en iyi duruma gerekiyor profil bilgilerini Yakalanacak kullanıcı senaryolarınızı gidin. Eğitim tamamladıktan sonra uygulamanızı kapatın veya seçin **durdurmak uygulama** bağlantı. Seçin **Çözümle** analiz adımın başlamak için Başlat.

Analiz tamamlandığında, **analiz** bölümü kullanıcı senaryosu eğitim aşamasında yakalanan profil bilgilerini raporunu gösterir. Hangi çoğu ve geçen en uzun süre adlı uygulamanızı işlevleri incelemek için bu raporu kullanın. Eklenti PGO bilgileri hızı için en iyi duruma getirmek için hangi uygulama çalışır ve hangi boyutu için en iyi duruma getirme belirlemek için kullanır. Eklenti PGO eğitim sırasında kaydedilen kullanıcı senaryoları için en küçük, hızlı uygulaması oluşturmak için yapı iyileştirmeler yapılandırır.

![PGO analizi sayfası](../../build/reference/media/pgofig5analyze.png "PGOFig5Analyze")

Eğitim beklenen profil bilgilerini yakalanmış durumunda seçebileceğiniz **Değişiklikleri Kaydet** gelecekteki derlemeleri en iyi duruma getirme projenizde çözümlenen profil verileri kaydetmek için. Profil verileri at ve eğitim baştan baştan başlamak için tercih **Yinele eğitim**.

Projenizde profil veri dosyasını kaydettiğiniz bir **PGO eğitim verilerini** klasör. Bu veriler, uygulamanızda derleyici derleme iyileştirme ayarlarını denetlemek için kullanılır.

![Çözüm Gezgini'nde PGO veri dosyası](../../build/reference/media/pgofig6data.png "PGOFig6Data")

Çözümleme sonrasında, eklenti PGO seçerek uygulamanızı derleme sırasında en iyi duruma getirmek için profil verileri kullanılacak projenizdeki derleme seçenekleri ayarlar. Aynı profil verileri ile uygulamanızı oluşturmak ve değiştirmek devam edebilirsiniz. Uygulama yapılandırıldığında, yapı çıktı kaç işlevleri ve yönergeleri profil verileri kullanarak getirildi bildirir.

![PGO çıkış tanılama](../../build/reference/media/pgofig7diagnostics.png "PGOFig7Diagnostics")

Geliştirme sırasında önemli kod değişiklik yaparsanız, en iyi iyileştirmeler almak için uygulamanızı yeniden eğitme gerekebilir. Derleme çıktı yüzde 80'den küçük işlevleri veya yönergeleri profil verileri kullanarak getirildi bildirdiğinde, uygulamanızın yeniden eğitme öneririz.