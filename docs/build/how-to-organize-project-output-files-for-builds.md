---
title: 'Nasıl Yapılır: Derlemeler için Proje Çıktı Dosyalarını Düzenleme'
ms.date: 05/06/2019
helpviewer_keywords:
- C++, output files
- output files, organizing
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
ms.openlocfilehash: 13aa3d1f8e2993ca34163ecbc0515948db56eb79
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328523"
---
# <a name="how-to-organize-project-output-files-for-builds"></a>Nasıl Yapılır: Derlemeler için Proje Çıktı Dosyalarını Düzenleme

Bu konu, proje çıktısı dosyalarını düzenlemek için en iyi uygulamaları açıklar. Proje çıktı dosyalarını yanlış ayarladığınızda yapı hataları oluşabilir. Bu konu, proje çıktı dosyalarınızı düzenlemek için her alternatifin avantaj ve dezavantajlarını da özetler.

## <a name="referencing-clr-assemblies"></a>CLR Montajlarına Başvurma

#### <a name="to-reference-assemblies-with-using"></a>#using ile derlemelere başvurmak için

1. Bir derlemeye doğrudan kodunuzdan, `#using <System.Data.dll>`#using yönergesi gibi . Daha fazla bilgi için [#using Yönergesi'ne](../preprocessor/hash-using-directive-cpp.md)bakın.

   Belirtilen dosya MSIL'de olduğu sürece .dll, .exe, .netmodule veya .obj olabilir. Başvurulan bileşen herhangi bir dilde oluşturulabilir. Meta veriler MSIL'den çıkarılalır, bu seçeneği kullanarak IntelliSense'e erişebilirsiniz. Söz konusu dosya proje için yolda olmalıdır; aksi takdirde, proje derlemez ve IntelliSense kullanılamaz. Dosyanın yolda olup olmadığını belirlemenin kolay bir yolu, #using satırına sağ tıklatMak ve **Belgeyi Aç** komutunu seçmektir. Dosya bulunamazsa size bildirilir.

   Dosyaya tam yol koymak istemiyorsanız, #using başvuruları için arama yolunu yeniden kullanmak için **/AI** derleyicisi seçeneğini kullanabilirsiniz. Daha fazla bilgi için bkz: [/AI (Meta veri dizinlerini belirtin)](reference/ai-specify-metadata-directories.md).

#### <a name="to-reference-assemblies-with-fu"></a>/FU ile derlemelere başvurmak için

1. Bir derlemeyi doğrudan yukarıda açıklandığı gibi bir kod dosyasından başvurmak yerine, **/FU** derleyici seçeneğini kullanabilirsiniz. Bu yöntemin avantajı, belirli bir derlemeye başvuran her dosyaya ayrı bir #using deyimi eklemeniz gerekmemesidir.

   Bu seçeneği ayarlamak için proje için **Özellikler Sayfalarını** açın. Yapılandırma **Özellikleri** düğümünü genişletin ve ardından **C/C++** düğümünü genişletin ve **Gelişmiş'i**seçin. **Force #using'nin**yanına istenilen montajları ekleyin. Daha fazla bilgi için bkz: [/FU (Ad Zorla #using Dosyası)](reference/fu-name-forced-hash-using-file.md).

#### <a name="to-reference-assemblies-with-add-new-reference"></a>Yeni Başvuru Ekle ile derlemelere başvurmak için

1. CLR montajlarını kullanmanın en kolay yolu budur. İlk olarak, projenin **/clr** derleyici seçeneği ile derlenmiş olduğundan emin olun. Ardından, **Çözüm Gezgini'nden** projeyi sağ tıklatın ve Add **,** **References'ı**seçin. **Özellik Sayfaları** iletişim kutusu görüntülenir.

1. Özellik **Sayfaları** iletişim kutusundan **Yeni Başvuru Ekle'yi**seçin. Geçerli projede bulunan tüm .NET, COM ve diğer derlemeleri listeleyen bir iletişim kutusu görüntülenir. İstenilen derlemeyi seçin ve **Tamam'ı**tıklatın.

   Proje başvurusu ayarlandıktan sonra, karşılık gelen bağımlılıklar otomatik olarak işlenir. Ayrıca, meta veriler bir derlemenin parçası olduğundan, yönetilen derlemelerden kullanılan öğelerin üstbilgi dosyası veya prototipi eklemenize gerek yoktur.

## <a name="referencing-native-dlls-or-static-libraries"></a>Yerel DL'lere veya Statik Kitaplıklara Başvurma

#### <a name="to-reference-native-dlls-or-static-libraries"></a>Yerel DL'lere veya statik kitaplıklara başvurmak için

1. #include yönergesini kullanarak kodunuzdaki uygun üstbilgi dosyasına başvurun. Üstbilgi dosyası, geçerli projenin dahil yolu veya parçası olmalıdır. Daha fazla bilgi için [#include bkz.](../preprocessor/hash-include-directive-c-cpp.md)

1. Proje bağımlılıklarını da ayarlayabilirsiniz. Proje bağımlılıklarını ayarlamak iki şeyi garanti eder. İlk olarak, projelerin doğru sırada inşa edilmesini sağlar, böylece bir proje her zaman gereksinim duyduğu bağımlı dosyaları bulabilir. İkinci olarak, dosyaların bağlantı zamanında kolayca bulunabilmesi için bağımlı projenin çıktı dizinini dolaylı olarak yola ekler.

1. Uygulamayı dağıtmak için DLL'yi uygun bir yere yerleştirmeniz gerekir. Bu aşağıdakilerden biri olabilir:

   1. Yürütülebilir olanla aynı yol.

   1. Sistem yolunun herhangi bir yerinde **(yol** ortamı değişkeni).

   1. Yan yana montajda. Daha fazla bilgi için [C/C++ Bina Yan Yana Derlemeler'e](building-c-cpp-side-by-side-assemblies.md)bakın.

## <a name="working-with-multiple-projects"></a>Birden Fazla Proje ile Çalışma

Varsayılan olarak, tüm çıktı dosyaları proje dizininin bir alt dizini oluşturulur şekilde oluşturulan projeler. Dizin, yapı yapılandırmasını (örn. Hata Ayıklama veya Sürüm) temel alınatır. Kardeş projelerin birbirine atıfta bulunabilmesi için, bağlantının başarılı olabilmesi için her projenin diğer proje çıktı dizinlerini kendi yoluna açıkça eklemesi gerekir. Bu, proje bağımlılıklarını ayarladığınızda otomatik olarak yapılır. Ancak, bağımlılıkları kullanmazsanız, bunu dikkatle işlemeniz gerekir, çünkü yapılar yönetmek çok zor olabilir. Örneğin, bir projede Hata Ayıklama ve Sürüm yapılandırmaları varsa ve kardeş projeden bir dış kitaplık içeriyorsa, hangi yapılandırmanın oluşturulduğuna bağlı olarak farklı bir kitaplık dosyası kullanmalıdır. Bu nedenle, zor kodlama bu yolları zor olabilir.

Tüm temel çıktı dosyaları (yürütülebilir ler, artımlı bağlayıcı dosyaları ve PDB dosyaları gibi) ortak bir çözüm dizinine kopyalanır. Bu nedenle, eşdeğer yapılandırmalara sahip bir dizi C++ projesi içeren bir çözümle çalışırken, tüm çıktı dosyaları basitleştirilmiş bağlantı ve dağıtım için merkezileştirilir. Bu dosyaları bir arada tutarlarsa (dosyaların yolda olacağı garanti olduğundan) uygulamalarının/kitaplıklarının beklendiği gibi çalışacağından emin olabilirsiniz.

Çıktı dosyalarının konumu, üretim ortamına dağıtılırken önemli bir sorun olabilir. IDE'de proje çalıştırırken, dahil edilen kitaplıklara giden yollar, üretim ortamındakiyle aynı olmayabilir. Örneğin, kodunuzda `#using "../../lib/debug/mylib.dll"` varsa ancak sonra mylib.dll'yi farklı bir göreli konuma dağıtıyorsanız, uygulama çalışma zamanında başarısız olur. Bunu önlemek için, kodunuzda #include ifadelerde göreli yollar kullanmaktan kaçınmalısınız. Gerekli dosyaların proje oluşturma yolunda olduğundan ve benzer şekilde karşılık gelen üretim dosyalarının düzgün şekilde yerleştirildiğinden emin olmak daha iyidir.

#### <a name="how-to-specify-where-output-files-go"></a>Çıktı dosyalarının nereye gideceği nasıl belirtilir?

1. Proje çıktı ayarlarının konumu, projenin Özellik **Sayfalarında**bulunabilir. **Yapılandırma Özellikleri'nin** yanındaki düğümü genişletin ve **Genel'i**seçin. Çıktı konumu **Çıktı Dizini**yanında belirtilir. Daha fazla bilgi için [Genel Özellik Sayfası (Proje)](reference/general-property-page-project.md)sayfasına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C++ proje türleri](reference/visual-cpp-project-types.md)
