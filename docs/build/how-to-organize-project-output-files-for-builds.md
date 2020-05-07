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

Bu konuda, proje çıktı dosyalarını düzenlemek için en iyi yöntemler açıklanmaktadır. Proje çıktı dosyalarını yanlış ayarladığınızda, derleme hataları oluşabilir. Bu konu ayrıca, proje çıktı dosyalarınızı düzenlemek için her bir alternatifin olumlu ve olumsuz yönlerini de özetler.

## <a name="referencing-clr-assemblies"></a>CLR derlemelerine başvurma

#### <a name="to-reference-assemblies-with-using"></a>#Using bütünleştirilmiş kodlara başvurmak için

1. Bir derlemeye, gibi #using yönergesini kullanarak doğrudan kodunuzda başvurabilirsiniz `#using <System.Data.dll>`. Daha fazla bilgi için bkz. [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).

   Belirtilen dosya, MSIL 'de olduğu sürece bir. dll,. exe,. netmodule veya. obj olabilir. Başvurulan bileşen herhangi bir dilde oluşturulabilir. Bu seçeneği kullanarak, meta verilerin MSIL 'den ayıklanmasından bu yana IntelliSense 'e erişebilirsiniz. Söz konusu dosya projenin yolunda olmalıdır; Aksi takdirde, proje derlenmez ve IntelliSense kullanılabilir olmaz. Dosyanın yolda olup olmadığını belirlemenin kolay bir yolu #using satırına sağ tıklayıp **belgeyi aç** komutunu kullanmaktır. Dosya bulunamazsa size bildirim gönderilir.

   Dosyanın tam yolunu koymak istemiyorsanız, #using başvuruların arama yolunu düzenlemek için **/AI** derleyici seçeneğini kullanabilirsiniz. Daha fazla bilgi için bkz. [/AI (meta veri dizinlerini belirt)](reference/ai-specify-metadata-directories.md).

#### <a name="to-reference-assemblies-with-fu"></a>Derlemelere/FU ile başvurmak için

1. Yukarıda açıklanan şekilde doğrudan bir kod dosyasından derlemeye başvurmak yerine, **/Fu** derleyici seçeneğini kullanabilirsiniz. Bu yöntemin avantajı, belirli bir derlemeye başvuran her dosyaya ayrı bir #using deyimleri eklemeniz gerekmez.

   Bu seçeneği ayarlamak için, proje için **Özellikler sayfalarını** açın. **Yapılandırma özellikleri** düğümünü genişletin ve ardından **C/C++** düğümünü genişletin ve **Gelişmiş**' i seçin. İstenen derlemeleri **zorla #using**' nin yanına ekleyin. Daha fazla bilgi için bkz. [/Fu (zorlanan #using dosyayı adlandır)](reference/fu-name-forced-hash-using-file.md).

#### <a name="to-reference-assemblies-with-add-new-reference"></a>Derlemelere yeni başvuru Ekle başvurusu yapmak için

1. Bu, CLR derlemelerini kullanmanın en kolay yoludur. İlk olarak, projenin **/clr** derleyici seçeneği ile derlendiğinden emin olun. Sonra, **Çözüm Gezgini** projeye sağ tıklayın ve **Ekle**, **Başvurular**' ı seçin. **Özellik sayfaları** iletişim kutusu görüntülenir.

1. **Özellik sayfaları** Iletişim kutusunda **Yeni Başvuru Ekle**' yi seçin. Geçerli projede bulunan tüm .NET, COM ve diğer derlemelerin listelendiği bir iletişim kutusu görüntülenir. İstediğiniz derlemeyi seçip **Tamam**' a tıklayın.

   Proje başvurusu ayarlandıktan sonra, karşılık gelen bağımlılıklar otomatik olarak işlenir. Ayrıca, meta veriler bir derlemenin parçası olduğundan, bir üst bilgi dosyası ya da yönetilen derlemelerden kullanılan öğeleri prototip ekleme gereksinimi yoktur.

## <a name="referencing-native-dlls-or-static-libraries"></a>Yerel dll 'Lere veya Statik Kitaplıklara başvurma

#### <a name="to-reference-native-dlls-or-static-libraries"></a>Yerel dll 'Lere veya statik kitaplıklara başvurmak için

1. #İnclude yönergesini kullanarak kodunuzdaki uygun üst bilgi dosyasına başvurun. Üst bilgi dosyası, geçerli projenin içerme yolunda veya bir bölümünde olmalıdır. Daha fazla bilgi için bkz. [#include yönergesi (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).

1. Ayrıca, Proje bağımlılıklarını da ayarlayabilirsiniz. Proje bağımlılıklarını ayarlama iki şeyi garanti eder. İlk olarak, projenin ihtiyaç duyacağı bağımlı dosyaları her zaman bulabilmesi için projelerin doğru sırada derlenmesini sağlar. İkinci olarak, bağlı projenin çıkış dizinini dolaylı olarak yola ekler, böylece dosyalar bağlantı sırasında kolayca bulunabilir.

1. Uygulamayı dağıtmak için, DLL 'yi uygun bir yere yerleştirmeniz gerekir. Bu, aşağıdakilerden biri olabilir:

   1. Yürütülebilir dosya ile aynı yol.

   1. Sistem yolundaki herhangi bir yerde ( **Path** ortam değişkeni).

   1. Yan yana derlemesinde. Daha fazla bilgi için bkz. [C/C++ yan yana derlemeler oluşturma](building-c-cpp-side-by-side-assemblies.md).

## <a name="working-with-multiple-projects"></a>Birden çok projeyle çalışma

Varsayılan olarak, projeler, tüm çıktı dosyaları proje dizininin bir alt dizininde oluşturulacak şekilde oluşturulur. Dizin, derleme yapılandırmasına göre adlandırılır (ör. hata ayıklama veya sürüm). Eşdüzey projelerin birbirlerine başvurması için, bağlama işleminin başarılı olması için her projenin diğer proje çıkış dizinlerini kendi yoluna eklemesi gerekir. Bu, Proje bağımlılıklarını ayarladığınızda otomatik olarak yapılır. Ancak, bağımlılıkları kullanmıyorsanız, derlemelerin yönetilmesi çok zor olabileceğinden bunu dikkatle uygulamanız gerekir. Örneğin, bir proje hata ayıklama ve yayın yapılandırmalarına sahip olduğunda ve bir eşdüzey projeden harici bir kitaplık içeriyorsa, hangi yapılandırmanın derlendiğine bağlı olarak farklı bir kitaplık dosyası kullanmalıdır. Bu nedenle, bu yolların sabit kodlanması karmaşık olabilir.

Tüm gerekli çıkış dosyaları (yürütülebilir dosyalar, artımlı bağlayıcı dosyaları ve PDB dosyaları gibi) ortak bir çözüm dizinine kopyalanır. Bu nedenle, benzer yapılandırmalara sahip bir dizi C++ projesi içeren bir çözümle çalışırken, Basitleştirilmiş bağlama ve dağıtım için tüm çıkış dosyaları merkezi hale getirilmiş olur. Uygulama/kitaplık, bu dosyaları birlikte tutduklarında (dosyaların yolda olması garanti edildiğinden) beklendiği gibi çalıştığından emin olabilirsiniz.

Çıkış dosyalarının konumu, üretim ortamına dağıtım yaparken önemli bir sorun olabilir. IDE 'de projeleri çalıştırırken, dahil edilen kitaplıkların yollarının üretim ortamındaki ile aynı olması gerekmez. Örneğin, kodunuzda varsa `#using "../../lib/debug/mylib.dll"` ve daha sonra MyLib. dll dosyasını farklı bir göreli konuma dağıtırsanız, uygulama çalışma zamanında başarısız olur. Bunu önlemek için kodunuzda #include deyimlerde göreli yollar kullanmaktan kaçının. Gerekli dosyaların proje derleme yolunda olduğundan ve benzer şekilde karşılık gelen üretim dosyalarının düzgün yerleştirildiğinden emin olmanın daha iyi bir yoludur.

#### <a name="how-to-specify-where-output-files-go"></a>Çıkış dosyalarının nereye gitbağlanacağını belirtme

1. Proje çıkış ayarlarının konumu projenin **özellik sayfalarında**bulunabilir. **Yapılandırma özellikleri** ' nin yanındaki düğümü genişletin ve **genel**' i seçin. Çıkış **dizini**' nin yanında çıktı konumu belirtilir. Daha fazla bilgi için bkz. [genel özellik sayfası (proje)](reference/general-property-page-project.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C++ proje türleri](reference/visual-cpp-project-types.md)
