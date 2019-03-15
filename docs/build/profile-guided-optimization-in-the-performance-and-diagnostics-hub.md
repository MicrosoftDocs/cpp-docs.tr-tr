---
title: Performans ve Tanılama Hub'ında Profil Temelli İyileştirme
ms.date: 11/19/2018
ms.assetid: dc3a1914-dbb6-4401-bc63-10665a8c8943
ms.openlocfilehash: e1aaf64c18ebde29e6ea0d6b4b6bdad66f21a435
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823545"
---
# <a name="profile-guided-optimization-in-the-visual-studio-2013-performance-and-diagnostics-hub"></a>Visual Studio 2013'ün performans ve tanılama hub'ında profil temelli iyileştirme

Visual Studio 2013 kullanıyorsanız, profil temelli iyileştirme performans ve tanılama hub'ı eklentisi Visual c++ geliştiricileri için profil temelli iyileştirme deneyimi basitleştirir. Yapabilecekleriniz [eklentinizi indirin](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) Visual Studio Web sitesinden. Eklenti, Visual Studio'nun sonraki sürümlerde desteklenmez.

Profil temelli iyileştirme (PGO) yardımcı derlemeler için kullanıcıların iyileştirilmiş x86 ve x64 yerel uygulama oluşturmak, bunlarla etkileşim kurun. PGO çok adımlı bir işlemdir: Profil oluşturma için izleme eklenmiş olan bir uygulama derleme oluşturun ve ardından, "eğitim." gerçekleştirin Diğer bir deyişle, ortak kullanıcı etkileşim senaryoları izleme eklenmiş uygulamayı çalıştırın. Yakalanan profil oluşturma verilerini kaydedin ve yeniden bütün program iyileştirmesi kılavuza sonuçları kullanarak uygulamanızı derleyin. Bu adımları tek tek komut satırında veya Visual Studio'da gerçekleştirebileceğiniz olsa da, PGO eklentisi merkezileştirir ve bu süreci kolaylaştırır. PGO eklentisi tüm gerekli seçenekleri ayarlar, her adımda size, analiz gösterir ve sonra sonuçları, boyut veya hız için her işlevi en iyi duruma getirmek için yapı yapılandırmak için kullanır. PGO eklentisi Ayrıca uygulama eğitim yeniden çalıştırın ve kodunuzu değiştikçe derleme en iyi duruma getirme verileri güncelleştirmek kolaylaştırır.

## <a name="prerequisites"></a>Önkoşullar

Yapmanız gerekenler [PGO eklentisi indirme](https://marketplace.visualstudio.com/items?itemName=ProfileGuidedOptimizationTeam.ProfileGuidedOptimizationforVisualC) ve performans ve tanılama hub'ı kullanmadan önce Visual Studio yükleyin.

## <a name="walkthrough-using-the-pgo-plug-in-to-optimize-an-app"></a>İzlenecek yol: Bir uygulamayı en iyi duruma getirme PGO eklentisi kullanma

İlk olarak, Visual Studio ile temel bir Win32 masaüstü uygulaması oluşturacaksınız. En iyi duruma getirmek istediğiniz yerel bir uygulama zaten varsa, bunu kullanın ve bu adımı atlayın.

### <a name="to-create-an-app"></a>Bir uygulama oluşturmak için

1. Menü çubuğunda, **dosya**, **yeni**, **proje**.

1. Sol bölmesinde **yeni proje** iletişim kutusunda **yüklü**, **şablonları**, **Visual C++** ve ardından  **MFC**.

1. Orta bölmede seçin **MFC uygulaması**.

1. Proje için bir ad belirleyin — Örneğin, **SamplePGOProject**— içinde **adı** kutusu. Seçin **Tamam** düğmesi.

1. Üzerinde **genel bakış** sayfasının **MFC Uygulama Sihirbazı** iletişim kutusunda **son** düğmesi.

Ardından, uygulamanızın derleme yapılandırması yayın PGO derleme ve eğitim adımları için hazırlamak üzere ayarlayın.

### <a name="to-set-the-build-configuration"></a>Derleme yapılandırmasını ayarlamak için

1. Menü çubuğunda, **derleme**, **Configuration Manager**.

1. İçinde **Configuration Manager** iletişim kutusunda **etkin çözüm yapılandırması** açılan düğmesini seçip alt **yayın**. Seçin **Kapat** düğmesi.

Performans ve tanılama hub'ı açın; menü çubuğunda, **Çözümle**, **performans ve tanılama**. Bu, proje türü için kullanılabilir olan araçlarına sahip bir tanılama oturumu sayfasını açar.

![Performans ve tanılama hub'ı PGO](media/pgofig0hub.png "PGO performans ve tanılama hub'ı")

İçinde **kullanılabilir Araçları**seçin **profil temelli iyileştirme** onay kutusu. Seçin **Başlat** PGO eklentisi başlatmak için düğme.

![PGO giriş sayfası](media/pgofig1start.png "PGO giriş sayfası")

**Profil temelli iyileştirme** sayfasını eklenti kullandığı uygulamanızın performansını iyileştirmek için adımları açıklar. Seçin **Başlat** düğmesi.

![PGO izleme sayfası](media/pgofig2instrument.png "PGO izleme sayfası")

İçinde **izleme** bölümünde kullandığınız **eğitim başlangıçta etkin** seçeneği uygulamanızı başlatma aşaması Eğitimin bir parçası olarak dahil edilip edilmeyeceğini seçin. Bu seçeneği seçili değilse, açıkça eğitimi etkinleştirene kadar eğitim verilerini çalışan izleme eklenmiş bir uygulamada kaydedilmez.

Seçin **gereç** düğmesini özel bir dizi derleyici seçeneği ile uygulamanızı oluşturun. Derleyici oluşturulan kodda araştırma yönergeleri ekler. Bu yönergeler eğitim aşamasında profil oluşturma verilerini kaydeder.

![PGO işaretlenmiş yapımda sayfa](media/pgofig3build.PNG "PGO işaretlenmiş yapımda sayfası")

Uygulamanızın izleme eklenmiş derleme tamamlandıktan sonra uygulamayı otomatik olarak başlatılır.

Yapı sırasında herhangi bir hata veya uyarı meydana gelirse, bunları düzeltin ve ardından **yeniden derleme** işaretlenmiş yapımda yeniden başlatmak için.

Uygulama başlatıldığında kullanabilirsiniz **Başlat eğitim** ve **duraklatma eğitim** bağlantılar **eğitim** bilgi profil oluşturma zaman kaydedilir denetlemek için bölüm. Kullanabileceğiniz **Durdur uygulama** ve **uygulamayı Başlat** bağlantılarını durdurun ve uygulamayı yeniden başlatın.

![PGO eğitim sayfa](media/pgofig4training.PNG "PGO eğitim sayfası")

Eğitim sırasında kodu En İyileştir PGO eklentisi gereken profil bilgilerini yakalamak üzere kullanıcı senaryoları gidin. Eğitimi tamamladıktan sonra uygulamanızı kapatın veya seçin **Durdur uygulama** bağlantı. Seçin **Çözümle** analiz adım başlatmak için düğme.

Analiz tamamlandığında **analiz** bölümü kullanıcı senaryosu eğitim aşaması sırasında yakalanan profil bilgilerini raporunu gösterir. Çoğu ve geçen en çok zaman adlı uygulamanızı, işlev incelemek için bu raporu kullanabilirsiniz. PGO eklentisi bilgileri hızını iyileştirmek için hangi uygulama çalışır ve hangi boyutu için en iyi duruma getirme belirlemek için kullanır. Eğitim sırasında kaydedilen kullanıcı senaryolar için en küçük, hızlı uygulama oluşturmak için derleme iyileştirmeleri PGO eklentisi yapılandırır.

![PGO analiz sayfası](media/pgofig5analyze.png "PGO çözümleme sayfası")

Eğitim beklenen profil bilgilerini yakalanan, seçebileceğiniz **Değişiklikleri Kaydet** gelecekteki yapılar iyileştirmek için projenizde çözümlenen profil verilerini kaydetmek için. Profil verileri atmak ve eğitim en baştan yeniden başlamak için seçin **Yinele eğitim**.

Profil veri dosyasını projenize kayıtlı olduğu bir **PGO eğitim verilerini** klasör. Bu verileri uygulamanızda derleyici derleme iyileştirme ayarlarını denetlemek için kullanılır.

![PGO veri dosyası Çözüm Gezgini'nde](media/pgofig6data.png "PGO veri dosyası Çözüm Gezgini'nde")

Çözümleme sonrasında, eklenti PGO profil verilerini seçmeli olarak derleme sırasında uygulamanızı en iyi duruma getirme kullanmak için projenizdeki derleme seçeneklerini ayarlar. Aynı profili verileri ile uygulamanızı oluşturun ve değiştirmek devam edebilirsiniz. Uygulama oluşturulduğunda, yapı çıkışını kaç işlevleri ve yönergeler profil verileri kullanılarak en iyi duruma getirilmiş raporlar.

![PGO tanılama çıkışı](media/pgofig7diagnostics.png "PGO tanılama çıkışı")

Geliştirme sırasında önemli bir kod değişikliği yaparsanız, en iyileştirmelerini almak için uygulamanızı yeniden eğitme gerekebilir. Derleme çıktısında profil verileri kullanılarak yüzde 80'den küçük işlevleri veya yönergeleri getirildi bildirdiğinde, uygulamanızı yeniden eğitme öneririz.