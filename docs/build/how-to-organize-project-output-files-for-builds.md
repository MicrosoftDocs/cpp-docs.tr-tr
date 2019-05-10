---
title: 'Nasıl yapılır: Derlemeler için proje çıktı dosyalarını düzenleme'
ms.date: 05/06/2019
helpviewer_keywords:
- C++, output files
- output files, organizing
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
ms.openlocfilehash: 202b2cbf135a5d8371354aac0fb8dd26367896c2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220668"
---
# <a name="how-to-organize-project-output-files-for-builds"></a>Nasıl yapılır: Derlemeler için proje çıktı dosyalarını düzenleme

Bu konuda, proje çıktı dosyalarını düzenlemek için en iyi uygulamalar açıklanmaktadır. Derleme proje çıktı dosyalarını yanlış ayarladığınızda hatalar meydana gelebilir. Bu konuda, avantajları ve dezavantajları proje çıktı dosyalarınızı düzenlemek için her bir alternatif de açıklanmaktadır.

## <a name="referencing-clr-assemblies"></a>CLR derlemelerine başvurma

#### <a name="to-reference-assemblies-with-using"></a>Başvuru bütünleştirilmiş kodları ile için #using

1. Kullanarak doğrudan kodunuzdan bir derlemeye başvurabilir #using yönergesi, gibi `#using <System.Data.dll>`. Daha fazla bilgi için [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).

   Belirtilen dosya, MSIL'de bulunduğu sürece bir .dll, .exe, .netmodule veya .obj olabilir. Başvurulan bileşen herhangi bir dilde oluşturulabilir. Bu seçeneği kullanarak meta veri MSIL çıkartıldığından bu yana IntelliSense erişiminiz gerekir. Söz konusu dosya projenin yolunda olmalıdır; Aksi takdirde, proje derlenmez ve IntelliSense kullanılamaz. Sağ tıklamak dosyanın yolunda olup olmadığını belirlemek için kolay bir yol olan # seçin ve satır using **açık belge** komutu. Dosya bulunamazsa, size bildirilir.

   Dosyaya tam yolunu koymak istemiyorsanız kullanabileceğiniz **/AI** arama yolunu düzenlemek için derleyici seçeneği #using. Daha fazla bilgi için [/AI (meta veri dizinlerini belirtin)](reference/ai-specify-metadata-directories.md).

#### <a name="to-reference-assemblies-with-fu"></a>Derlemelere /FU ile başvurmak için

1. Kullanabileceğiniz bir derlemeye doğrudan kod dosyasından yukarıda açıklanan şekilde başvurmak yerine **/FU** derleyici seçeneği. Ayrı bir eklemeniz gerekmez, bu yöntemin avantajı olan # verilen bir derlemeye başvuran her dosyaya using deyimi.

   Bu seçeneği belirlemek için açık **özellikler sayfaları** projesi için. Genişletin **yapılandırma özellikleri** düğümünü ve ardından **C/C++** düğümünü seçip alt **Gelişmiş**. İstenen derlemeleri ekleyin **zorla #using**. Daha fazla bilgi için [/FU (zorlanan adı #using)](reference/fu-name-forced-hash-using-file.md).

#### <a name="to-reference-assemblies-with-add-new-reference"></a>Derlemelere Yeni Başvuru Ekle ile başvurmak için

1. Bu, CLR derlemeleri kullanmak için en kolay yoludur. İlk olarak, emin proje ile derlenmiş **/CLR** derleyici seçeneği. Projeden sağ'a tıklayarak **Çözüm Gezgini** seçip **Ekle**, **başvuruları**. **Özellik sayfaları** iletişim kutusu görüntülenir.

1. Gelen **özellik sayfaları** iletişim kutusunda **Yeni Başvuru Ekle**. Tüm .NET, COM ve diğer derlemelerin geçerli projede kullanılabilir listeleyen bir iletişim kutusu görünür. İstenen derlemeyi seçin ve tıklayın **Tamam**.

   Bir proje başvurusu ayarlandıktan sonra ilgili bağımlılıkları otomatik olarak işlenir. Ayrıca, meta veriler bir derlemenin parçası olduğundan, bir üst bilgi dosyası veya prototip yönetilen derlemelerden kullanılmakta olan öğeleri eklemek için gerek yoktur.

## <a name="referencing-native-dlls-or-static-libraries"></a>Yerel DLL'lere veya statik kitaplıklara başvurma

#### <a name="to-reference-native-dlls-or-static-libraries"></a>Yerel DLL'lere veya statik kitaplıklara başvurmak için

1. Kullanarak kodunuzdaki uygun üstbilgi dosyasına başvurmak #include yönergesi. Üstbilgi dosyası ekleme yolunda olmalı veya geçerli projenin bir parçası olmalıdır. Daha fazla bilgi için [#include yönergesi (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).

1. Proje bağımlılıkları da ayarlayabilirsiniz. Proje bağımlılıklarını ayarlama, iki şeyi garanti eder. İlk olarak, bir proje her zaman ihtiyacı olan bağımlı dosyaları bulabilmesi projelerin doğru sırada oluşturulmasını sağlar. Dosyaların bağlantı anında kolayca bulunabilir böylece ikinci olarak, örtük olarak için bağımlı projenin çıktı dizini yolunu ekler.

1. Uygulamayı dağıtmak için DLL uygun bir yere yerleştirmeniz gerekir. Bu, aşağıdakilerden biri olabilir:

   1. Yürütülebilir olarak aynı yol.

   1. Sistem yolundaki herhangi bir yerde ( **yolu** ortam değişkeni).

   1. Yan yana derlemede. Daha fazla bilgi için [C/C++ yan yana derlemeler oluşturuluyor](building-c-cpp-side-by-side-assemblies.md).

## <a name="working-with-multiple-projects"></a>Birden fazla projeyle çalışma

Sağlayacak şekilde tüm çıktı dosyalarının proje dizininin alt dizininde oluşturulan varsayılan olarak, projeler oluşturulur. Dizin yapı yapılandırmasına göre adlandırılır (örneğin hata ayıklama veya sürüm). Eş projelerin birbirine sırayla her proje açıkça diğer proje çıktı dizinlerini kendi yoluna başarılı olması için sırayla eklemeniz gerekir. Proje bağımlılıkları oluşturduğunuzda bu otomatik olarak gerçekleştirilir. Bağımlılıklar kullanmazsanız, yapıları yönetmek çok zor olabilir çünkü Bununla birlikte, bunu dikkatle kullanmalısınız. Örneğin, bir projenin hata ayıklama ve yayın yapılandırmaları vardır ve bir kardeş projeden harici bir kitaplık içerir, hangi yapılandırmanın oluşturulduğunda farklı kitaplık dosyası kullanmalısınız. Bu nedenle, bu yolların sabit kodlama zor olabilir.

Tüm gerekli çıktı dosyaları (örneğin, yürütülebilir dosyalar, artımlı bağlayıcı dosyalar ve PDB dosyaları) bir ortak çözüm dizinine kopyalanır. Bu nedenle, bir dizi eşdeğer yapılandırmalara C++ projeleri içeren bir çözüm ile çalışırken, tüm çıktı dosyaları basit bağlama ve dağıtım için merkezi duruma getirilmiştir. Kendi uygulaması/kitaplığının (dosyaların yolda olması garanti edildiğinden), bu dosyaları bir arada tutmak, beklendiği gibi çalıştığından emin olabilir.

Bir üretim ortamına dağıtma yaparken, çıktı dosyalarının konumu önemli bir sorun olabilir. IDE'de projeleri çalıştırırken, eklenen kitaplıkların yollarının mutlaka üretim ortamıyla aynı değildir. Örneğin, `#using "../../lib/debug/mylib.dll"` mylib.dll kodunuzda ancak ardından farklı bir ilişkili konuma dağıtıyorsanız, uygulama çalışma zamanında başarısız olur. Bunu önlemek için göreli yollardan kaçınmalısınız # ifadeleri kodunuzda include. İyidir gerekli dosyaların proje oluşturma yolunda olduğundan emin olun ve benzer şekilde ilgili üretim dosyalarının düzgün bir şekilde yerleştirildiğinden emin olun.

#### <a name="how-to-specify-where-output-files-go"></a>Çıktı dosyalarının gideceği yeri belirleme

1. Proje konumunu ayarlar projesinin bulunabilir çıkış **özellik sayfaları**. Yanındaki düğümü genişletin **yapılandırma özellikleri** seçip **genel**. Çıkış konumu yanında belirtilir **çıkış dizinine**. Daha fazla bilgi için [genel özellik sayfası (Proje)](reference/general-property-page-project.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++Visual Studio Proje türleri](reference/visual-cpp-project-types.md)
