---
title: 'Nasıl yapılır: derlemeler için proje çıktı dosyalarını düzenleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, output files
- output files, organizing
ms.assetid: 521d95ea-2dcc-4da0-b5eb-ac3e57941446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0d1e7f8ea67db0e87199e0c12128555fa039112
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-organize-project-output-files-for-builds"></a>Nasıl Yapılır: Derlemeler için Proje Çıktı Dosyalarını Düzenleme
Bu konu, proje çıktı dosyalarını düzenleme için en iyi uygulamaları açıklar. Yapı proje çıktı dosyalarını yanlış olarak ayarladığınızda hatalar oluşabilir. Bu konu ayrıca olumlu ve olumsuz yönlerini proje çıktı dosyalarını düzenleme için her alternatif özetler.  
  
## <a name="referencing-clr-assemblies"></a>CLR derlemelere başvurma  
  
#### <a name="to-reference-assemblies-with-using"></a>Başvuru derlemeleri ile için #using  
  
1.  Bir derlemeyi kullanarak doğrudan kodunuzdan başvurusu yapabilir # gibi using yönergesi, `#using <System.Data.dll>`. Daha fazla bilgi için bkz: [#using yönergesi](../preprocessor/hash-using-directive-cpp.md).  
  
     MSIL içinde olduğu sürece belirtilen dosya bir .dll, .exe, .netmodule veya .obj, olabilir. Başvurulan bileşeni herhangi bir dilde oluşturulabilir. Meta veriler MSIL'den ayıklanacağı beri bu seçeneği kullanarak, IntelliSense erişebilir. Söz konusu dosyayı projesi için yolunda olmalıdır; Aksi takdirde, proje derlenmez ve IntelliSense kullanılamaz. Sağ için dosya yolu olup olmadığını belirlemek için kolay bir yoludur # seçin ve satır using **açık belge** komutu. Dosya bulunamazsa size bildirilecek.  
  
     Tam yol dosyaya koymak istemiyorsanız kullanabileceğiniz **/AI** derleyici seçeneği için arama yolu düzenlemek için #using. Daha fazla bilgi için bkz: [/AI (meta veri dizinlerini belirtin)](../build/reference/ai-specify-metadata-directories.md).  
  
#### <a name="to-reference-assemblies-with-fu"></a>/FU Derlemelerle başvurmak için  
  
1.  Kullanabileceğiniz bütünleştirilmiş kod dosyasının yukarıda açıklandığı gibi başvuran yerine, **/FU** derleyici seçeneği. Bu yöntem yararınıza ayrı bir eklemek gerekmez olan # verilen derlemeyi başvuran her dosya için using.  
  
     Bu seçeneği belirlemek için açık **özellikler sayfalarına** projesi için. Genişletin **yapılandırma özellikleri** düğümünü genişletin ve ardından **C/C++** düğümü ve select **Gelişmiş**. İstenen derlemeleri ekleyebilirsiniz **zorla #using**. Daha fazla bilgi için bkz: [/FU (zorlanan adı #using)](../build/reference/fu-name-forced-hash-using-file.md).  
  
#### <a name="to-reference-assemblies-with-add-new-reference"></a>Yeni Başvuru Ekle derlemelere başvurma  
  
1.  Bu, CLR derlemelerine kullanmak için en kolay yoludur. İlk olarak, emin olun proje ile derlenmiş **/CLR** derleyici seçeneği. Sağ projeden ardından **Çözüm Gezgini** seçip **Ekle**, **başvurular**. **Özellik sayfaları** iletişim kutusu görünecektir.  
  
2.  Gelen **özellik sayfaları** iletişim kutusunda **Yeni Başvuru Ekle**. Tüm .NET, COM ve geçerli projede kullanılabilir diğer derlemelerden listeleyen bir iletişim kutusu görünür. İstenen derleme tıklatıp **Tamam**.  
  
     Proje başvurusu ayarladıktan sonra bunlara karşılık gelen bağımlılıklar otomatik olarak işlenir. Ayrıca, meta veri bütünleştirilmiş parçası olduğundan, bir üst bilgi dosyası veya prototip yönetilen derlemelerden kullanılmakta olan öğeler eklemek için gerek yoktur.  
  
## <a name="referencing-native-dlls-or-static-libraries"></a>Yerel DLL'leri veya statik kitaplıklar başvurma  
  
#### <a name="to-reference-native-dlls-or-static-libraries"></a>Yerel DLL'leri veya statik kitaplıklar başvurmak için  
  
1.  Kod kullanarak uygun üstbilgi dosyası başvuru #include yönergesi. Üst bilgi dosyasını dahil etme yolu veya geçerli projenin bir parçası olması gerekir. Daha fazla bilgi için bkz: [#include yönergesi (C/C++)](../preprocessor/hash-include-directive-c-cpp.md).  
  
2.  Proje bağımlılıkları da ayarlayabilirsiniz. Proje bağımlılıkları ayarı iki şey güvence altına alır. İlk olarak, bir proje gereken bağımlı dosyaları her zaman bulabilmesi için projeleri doğru sırada oluşturulan sağlar. Dosyaları bağlantı zamanında kolayca bulunabilir böylece ikinci olarak, örtük olarak bağımlı projenin çıktı dizini yolu ekler.  
  
3.  Uygulamayı dağıtmak için uygun bir yerinde DLL yerleştirmeniz gerekir. Bu aşağıdakilerden biri olabilir:  
  
    1.  Yürütülebilir dosya aynı yol.  
  
    2.  Sistem yolunda başka bir yerindeki ( **yolu** ortam değişkeni).  
  
    3.  Yan yana derleme. Daha fazla bilgi için bkz: [yapı C/C++ yan yana derlemeler](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="working-with-multiple-projects"></a>Birden çok proje ile çalışma  
 Tüm çıktı dosyaları proje dizininin bir alt dizinde oluşturulur, varsayılan olarak, projeler oluşturulur. Dizin derleme yapılandırmasını temel alarak olarak adlandırılır (örn: hata ayıklama veya yayın). Sırayla birbirine başvurmak eşdüzey projeleri için her proje açıkça bir proje çıktı dizinleri başarılı olması için bağlama sırası içinde kendi yol eklemeniz gerekir. Proje bağımlılıkları ayarladığınızda, bu otomatik olarak gerçekleştirilir. Bağımlılıklar kullanmıyorsanız derlemeleri yönetmek oldukça zor olabilir çünkü ancak, dikkatlice bu işlemelidir. Örneğin, bir projeyi hata ayıklama ve yayın yapılandırmaları olan ve bir eşdüzey projeden dış kitaplık içerir, yapılandırma bağlı olarak oluşturulmakta olan farklı bir kitaplık dosyası kullanmalısınız. Bu nedenle, bu yollar kodlamak zor olabilir.  
  
 Tüm gerekli çıktı dosyaları (örneğin, yürütülebilir dosyalar, artımlı bağlayıcı dosyaları ve PDB dosyaları), ortak bir çözüm dizini kopyalanır. Bu nedenle, C++ projeleri eşdeğer yapılandırmalarla sayısını içeren bir çözümü ile çalışırken, tüm çıktı dosyaları Basitleştirilmiş bağlama ve dağıtım için merkezi olarak kullanılır. Kendi uygulama/kitaplığı (dosya yolunda olması garanti bu yana) bunlar bu dosyaları bir arada tutmak, beklendiği gibi çalıştığından emin olabilir.  
  
 Çıkış dosyalarının konumunu bir üretim ortamına dağıtılmadan önemli bir sorun olabilir. IDE içinde projeleri çalıştırılırken eklenen kitaplıkları yollara mutlaka üretim ortamı ile aynı değildir. Örneğin, `#using "../../lib/debug/mylib.dll"` kodunuzda sonra ancak farklı bir göreli konuma mylib.dll dağıtmak için uygulamanın çalışma zamanında başarısız olur. Bunu önlemek için göreli yolları yapmaktan kaçınmalısınız # deyimleri kodunuzda include. Daha iyi gerekli dosyaları proje derleme yolunda olduğundan emin olun ve karşılık gelen üretim dosyaları düzgün yerleştirilir benzer şekilde sağlama.  
  
#### <a name="how-to-specify-where-output-files-go"></a>Burada Git çıktı dosyaları belirtme  
  
1.  Proje konumunu ayarlar projesinin bulunabilir çıktı **özellik sayfaları**. Yanına düğümünü **yapılandırma özellikleri** seçip **genel**. Çıkış konumu yanına belirtilen **çıktı dizini**. Daha fazla bilgi için bkz: [genel özellik sayfası (Proje)](../ide/general-property-page-project.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)