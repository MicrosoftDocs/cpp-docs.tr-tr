---
title: Visual C++'ta DLL'leri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 14f8a0914b1bb7f2d3a16681a3a66091eda71d73
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="dlls-in-visual-c"></a>Visual C++'da DLL'ler  
  
Windows, bir dinamik bağlantı kitaplığı (DLL) paylaşılan bir kitaplık işlevleri ve kaynakların çalışır yürütülebilir dosya türüdür. Dinamik bağlantılandırma işlevleri çağırmak ya da ayrı bir dosyada depolanan kaynakları kullanmak için yürütülebilir bir dosya sağlayan bir işletim sistemi özelliğidir. Bu işlevler ve kaynakları derlenmiş ve bunları yürütülebilir dosyalar ayrı olarak dağıtılabilir. DLL tek başına yürütülebilir dosya değildir; çağıran bir uygulama bağlamında çalışır. Uygulama yüklendiğinde işletim sisteminin bir uygulamanın bellek alanına DLL yükleyebilirsiniz (*örtük bağlantılandırma*), ya da çalışma zamanında isteğe bağlı (*açıkça bağlama*). DLL'leri de işlevleri ve kaynakları yürütülebilir dosyalar arasında paylaşmak kolaylaştırır. Birden çok uygulama bellek DLL'de tek bir kopyasını içeriği aynı anda erişebilir.  
  
## <a name="differences-between-dynamic-linking-and-static-linking"></a>Dinamik olarak bağlama ve statik bağlama arasındaki farklar  
  
Statik bağlama tüm nesne kodu oluşturulduklarında kullanan yürütülebilir dosyalar statik kitaplığa kopyalar. Dinamik bağlantılandırma yalnızca Windows tarafından bulmak ve bir veri öğesi veya işlevi içeren DLL yüklemek için çalışma zamanında gereken bilgileri içerir. DLL oluşturduğunuzda, ayrıca bu bilgileri içeren bir içeri aktarma kitaplığı oluşturun. DLL çağıran yürütülebilir yapılandırdığınızda, bağlayıcı dışarı aktarılan sembolleri içeri aktarma kitaplığı'nda Windows Yükleyicisi için bu bilgileri depolamak için kullanır. Yükleyici bir DLL yüklendiğinde, DLL, uygulamanızın bellek alanına eşlenir. Varsa, özel bir işlev DLL'de `DllMain`, DLL gerektirir başlatma gerçekleştirmek üzere çağırılır.  
  
<a name="differences-between-applications-and-dlls"></a>  
  
## <a name="differences-between-applications-and-dlls"></a>Uygulamalar ve DLL'ler arasındaki farklılıklar  
  
DLL'ler ve uygulamalar hem yürütülebilir modülleri olsa da, çeşitli yollarla farklılık gösterir. Son kullanıcı için en bariz fark DLL'leri doğrudan yürütülebilir uygulamaları olmamasıdır. Sistemin açısından bakıldığında, uygulamalar ve DLL'ler arasındaki iki temel farklar vardır:  
  
-   DLL yalnızca bir örneği olabilir ancak bir uygulama kendisini eşzamanlı olarak çalışan birden çok örneği olabilir.  
  
-   Bir yığın, iş parçacıklarının yürütülmesine, genel bellek, dosya tanıtıcıları ve bir ileti sırası gibi şeyler sahip bir işlem olarak bir uygulama yüklenebilir, ancak bir DLL'in olamaz.  
  
<a name="advantages-of-using-dlls"></a>  
  
## <a name="advantages-of-using-dlls"></a>DLL'leri kullanmanın yararları  
  
Kod ve kaynaklara statik bağlama yerine dinamik bağlantılandırma birkaç avantaj sunar. DLL'leri kullandığınızda, bellek alanı kaydedin ve değiştirmeyi azaltır. Birden çok uygulama DLL tek bir kopyasını kullandığınızda disk alanından tasarruf ve bant genişliği indirin. DLL'leri dağıtılabilir ve yeniden oluşturun ve tüm kodunuzu sevk gerek kalmadan Pazar sonrası desteği ve yazılım güncelleştirmeleri sağlamak sağlayan ayrı olarak güncelleştirilir. DLL'leri çok dilli programları destekler ve uygulamalarınızın uluslararası sürüm oluşturma kolaylaştırır yerel ayarlara özgü kaynakları sağlamak için kullanışlı bir yoldur. Açıkça bağlantılandırma bulmak ve yeni özellikleri sağlıyor uzantıları gibi çalışma zamanında DLL'leri yüklemek, uygulamanızın izin verebilirsiniz.  
  
Dinamik bağlantılandırma aşağıdaki avantajlara sahiptir:  
  
-   Dinamik bağlantılandırma bellek kaydeder ve değiştirmeyi azaltır. Birçok işlemler DLL bellek DLL'de salt okunur bölümlerini tek bir kopyasını paylaşımı aynı anda kullanabilir. Buna karşılık, statik olarak bağlantılı bir kitaplık kullanılarak oluşturulmuş her uygulama Windows belleğe gerekir kitaplık kodu tam bir kopyasını sahiptir.  
  
-   Dinamik bağlantılandırma disk alanı ve bant genişliği kaydeder. Birçok uygulama, DLL diskteki tek bir kopyasını paylaşabilirsiniz. Buna karşılık, statik bağlantı kitaplığı kullanılarak oluşturulmuş her uygulamanın daha fazla disk alanı kullanır ve aktarmak için daha fazla bant genişliği alır, yürütülebilir görüntü bağlantılı kitaplık kodu vardır.  
  
-   Bakım, güvenlik düzeltmelerini ve yükseltmeleri daha kolay olabilir. Uygulamalarınızı DLL'de ortak işlevler kullandığınızda, sonra işlev bağımsız değişkenleri ve dönüş değerleri değiştirmeyin sürece, hata düzeltmeleri uygulamak ve güncelleştirmeleri DLL'e dağıtabilirsiniz. DLL'leri güncelleştirildiğinde, bunları kullanan uygulamaları yeniden derlenmesi veya yeniden gerekmez ve yaptıkları dağıtıldıktan hemen sonra yeni DLL'SİNİN kullanın. Buna karşılık, statik olarak bağlantılı nesne kodunda yaptığınız düzeltmeleri yeniden bağlamak ve onu kullanan her uygulamayı yeniden gerektirir.  
  
-   DLL'leri Pazar sonrası desteği sağlamak için kullanabilirsiniz. Örneğin, bir görüntü sürücüsü DLL uygulama gönderildiğinde, kullanılabilir olmayan bir görüntüyü destekleyecek şekilde değiştirilebilir. Açıkça bağlantılandırma uygulama uzantıları DLL'ler olarak yüklemek için kullanın ve yeniden oluşturma veya dağıtarak, uygulamanızın yeni işlevsellik ekleyin.  
  
-   Dinamik bağlantılandırma farklı programlama dilinde yazılmış uygulamalar desteklemeyi kolaylaştırır. İşlev çağırma programları izlediğiniz sürece farklı programlama dilinde yazılmış programları aynı DLL işlevini çağırabilir. Programları ve DLL işlevi aşağıdaki yollarla uyumlu olmalıdır: hangi sırayla işlevi yığına edilmesini bağımsız değişkenleri bekler, işlevin veya uygulamanın yığını temizleme işlemi için sorumlu olup, ve olup olmadığı herhangi bir bağımsız değişken geçirilen kaydeder.  
  
-   Dinamik bağlantılandırma MFC kitaplık sınıflarını genişletmek için bir mekanizma sağlar. Sınıfları varolan MFC sınıflarından ve MFC uygulamaları tarafından kullanım için MFC uzantı DLL'de yerleştirin.  
  
-   Dinamik bağlantılandırma uygulamanızın uluslararası sürümlerin oluşturulmasını kolaylaştırır. DLL'de yerel ayarlara özgü kaynakları koyarak uluslararası sürümlerini bir uygulama oluşturmak çok daha kolay olur. Uygulamanızın birçok yerelleştirilmiş sürümleri sevkiyat, yerine ayrı kaynak DLL dizeler ve görüntüleri her dil için yerleştirin ve uygulamanızı yerel çalışma zamanında uygun kaynaklara sonra yükleyebilirsiniz.   
  
 DLL'leri kullanmanın olası bir dezavantajı, uygulama kendi içinde değil olan; dağıtma veya kendiniz yüklemenizin bir parçası doğrulamak ayrı bir DLL modülü varlığını bağlıdır.  
  
  
## <a name="more-information-on-how-to-create-and-use-dlls"></a>Oluşturma ve DLL'leri kullanma hakkında daha fazla bilgi  
  
Aşağıdaki konular, Visual c++ programı DLL'leri hakkında ayrıntılı bilgi sağlar.  
  
 [İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Visual Studio kullanarak bir DLL'nin nasıl oluşturulacağı ve kullanılacağı açıklanmıştır.  
  
 [DLL Türleri](../build/kinds-of-dlls.md)  
 Yapılandırılabilecek farklı DLL türleri hakkında bilgi sağlar.  
  
 [Sıkça Sorulan DLL soruları](../build/dll-frequently-asked-questions.md)  
 DLL'ler hakkında sık sorulan soruların yanıtlarını sağlar.  
  
 [Bir yürütülebilir dosyayı DLL’ye bağlama](../build/linking-an-executable-to-a-dll.md)  
 DLL'ye olan açık ve örtük bağlantıları açıklar.  
  
 [DLL başlatma](../build/run-time-library-behavior.md#initializing-a-dll)  
 DLL yüklendiğinde yürütülmelidir DLL başlatma kodu açıklanır.  
  
 [DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)  
 Çalışma zamanı kitaplığının DLL başlangıç dizisini nasıl gerçekleştirdiğini açıklar.  
  
 [LoadLibrary ve AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 Kullanarak anlatılmaktadır **LoadLibrary** ve `AfxLoadLibrary` çalışma zamanında bir DLL için açıkça bağlanmak için.  
  
 [GetProcAddress](../build/getprocaddress.md)  
 Kullanarak anlatılmaktadır **GetProcAddress** DLL dışarı aktarılan bir işlevin adresini elde edin.  
  
 [FreeLibrary ve AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 Kullanarak anlatılmaktadır **FreeLibrary** ve `AfxFreeLibrary` zaman DLL modülü artık gerekli.  
  
 [DLL Bulmak için Windows Tarafından Kullanılan Arama Yolu](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 Windows işletim sisteminin sistemde DLL bulmak için kullandığı arama yolu açıklar.  
  
 [MFC'ye Dinamik Olarak Bağlı Normal MFC DLL'sinin Modül Durumları](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 MFC DLL dinamik olarak MFC'ye bağlı normal modül durumları açıklar.  
  
 [MFC uzantısı DLL’leri](../build/extension-dlls-overview.md)  
 Genel olarak varolan Microsoft Foundation Sınıf Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan DLL'leri açıklar.  
  
 [Yalnızca Kaynak DLL Oluşturma](../build/creating-a-resource-only-dll.md)  
 Simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren yalnızca kaynak DLL'sini açıklar.  
  
 [MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 Uydu DLL'lere gelişmiş destek, çoklu dillerde yerelleşmiş uygulamalar oluşturmaya yardım eden bir özellik sağlar.  
  
 [İçeri ve Dışarı Aktarma](../build/importing-and-exporting.md)  
 Bir uygulamaya genel simgelerin nasıl içe aktarılacağını veya işlevlerin DLL'den nasıl dışa aktarılacağını açıklar  
  
 [Etkin Teknoloji ve DLL'ler](../build/active-technology-and-dlls.md)  
 Nesne sunucularının DLL içinde uygulanmasına izin verir.  
  
 [DLL'de Otomasyon](../build/automation-in-a-dll.md)  
 MFC DLL Sihirbazı'ndaki Otomasyon seçeneğinin ne sağladığını açıklar.  
  
 [MFC DLL'leri İçin Adlandırma Kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)  
 MFC'de bulunan DLL dosyalarının ve kitaplıkların nasıl bir yapılandırılmış adlandırma kuralı izlediğini açıklar.  
  
 [Visual Basic uygulamasından DLL işlevi çağırma](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Visual Basic uygulamalarından DLL işlevlerinin nasıl çağrılacağını açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
  
 [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 MFC kitaplığını Windows dinamik bağlantı kitaplığı bir parçası olarak kullanmanıza olanak tanır Normal MFC DLL'leri açıklar.  
  
 [DLL Version of MFC](../mfc/tn033-dll-version-of-mfc.md)  
 MFCxx.dll kullanabilirsiniz ve MFC uygulamaları ve MFC uzantı DLL'leri ile dinamik bağlantı kitaplıkları (x MFC sürüm numarası olduğu yer) MFCxxD.dll paylaşılan nasıl açıklanmaktadır.  
