---
title: Visual C++'ta DLL'ler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28be2caa3477eabc8b717b387c99d65585a9ef19
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718061"
---
# <a name="dlls-in-visual-c"></a>Visual C++'da DLL'ler

Windows bir dinamik bağlantı kitaplığı (DLL) paylaşılan bir kitaplık işlevleri ve kaynak davranır yürütülebilir dosya türüdür. Dinamik bağlama işlevlerini veya ayrı bir dosyada depolanan kaynakları kullanmak bir yürütülebilir dosya sağlayan bir işletim sistemi özelliğidir. Bu işlevler ve kaynakları derlenmiş ve bunları yürütülebilir dosyaları ayrı ayrı dağıtılsa. Bir DLL tek başına yürütülebilir dosya değil; Bu işlem, onu çağıran bir uygulama bağlamında çalışır. Uygulama yüklendiğinde işletim sisteminin bir uygulamanın bellek alanına DLL yükleyebilirsiniz (*örtük bağlama*), ya da isteğe bağlı çalışma zamanında (*açık bağlama*). DLL'leri da işlevleri ve kaynakları yürütülebilir dosyalar arasında paylaşmak kolaylaştırır. Birden çok uygulama içeriğini DLL bellek içinde tek bir kopyasını aynı anda erişebilir.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>Dinamik bağlama statik bağlamadan arasındaki farklar

Statik bağlama tüm nesne kodu statik kitaplıkta oluşturulduklarında, onu kullanan yürütülebilir dosyaları kopyalar. Dinamik bağlama, yalnızca Windows tarafından bulmak ve bir veri öğesi ya da işlev içeren DLL yüklemek için çalışma zamanında gereken bilgileri içerir. Bir DLL oluşturduğunuzda, bu bilgileri içeren bir içeri aktarma kitaplığı oluşturabilir. DLL'yi çağıran bir yürütülebilir dosya oluştururken, bağlayıcı dışarı aktarılan simgeleri içeri aktarma kitaplığı'nda Windows Yükleyicisi için bu bilgileri depolamak için kullanır. Yükleyici bir DLL yüklendiğinde, DLL uygulamanızın bellek alanı eşlenir. Varsa, özel bir işlev DLL'deki `DllMain`, DLL gerektiren herhangi bir başlatma gerçekleştirmek üzere çağırılır.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>Uygulamalar ve DLL'ler arasındaki farklılıklar

DLL'ler ve uygulamalar her iki yürütülebilir modüllerin olsa da, çeşitli yollarla farklılık gösterir. Son kullanıcıya, DLL doğrudan yürütülebilecek uygulamalar olmayan en belirgin farktır. Sistemin açısından bakıldığında, iki, uygulamalar ve DLL'ler arasındaki temel farklar vardır:

- Bir DLL yalnızca bir örneğine sahip olabilir ancak bir uygulamanın kendisini sistemde eşzamanlı olarak çalışan birden çok örneğini olabilir.

- Bir yığın, iş parçacığı yürütme, genel bellek, dosya tanıtıcıları ve bir ileti kuyruğu gibi şeyler sahip bir işlem olarak bir uygulama yüklenebilir, ancak bir DLL olamaz.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>DLL'leri kullanmanın yararları

Kod ve kaynaklar için statik bağlama yerine dinamik bağlama, çeşitli avantajlar sunar. DLL'leri kullandığınızda, bellek alanı kaydedebilir ve değiştirmeyi azaltır. Çoklu uygulamaları tek bir DLL kopyasının kullandığınızda disk alanını kaydetmek ve bant genişliği'ni indirin. DLL'ler dağıtılabilir ve yeniden oluşturun ve tüm kodlar göndermek zorunda kalmadan kolayca desteği ve yazılım güncelleştirmeleri sağlamak olanak sağlayan ayrı olarak güncelleştirildi. DLL'leri, çok dilli programları destekler ve uluslararası uygulamalarınızın sürümlerini oluşturma sürecini kolaylaştırır, yerel ayara özgü kaynaklar sağlamak için kullanışlı bir yoludur. Açık bağlama uygulamanızı keşfedip çalışma zamanında, yeni özellikler sağlayan uzantıları gibi DLL'leri yükleme izin verebilirsiniz.

Dinamik bağlama, aşağıdaki avantajlara sahiptir:

- Dinamik bağlama, bellek kaydeder ve değiştirmeyi azaltır. Pek bir DLL bellekte bir DLL salt okunur bölümlerini tek bir kopyasını paylaşımı eşzamanlı olarak kullanabilirsiniz. Buna karşılık, bir statik olarak bağlı kitaplığı kullanılarak derlenen her bir uygulama Windows belleğe gerekir kitaplık kodu tam bir kopyasına sahip olur.

- Dinamik bağlama, disk alanı ve bant genişliği kaydeder. Birçok uygulama, tek bir DLL disk üzerindeki kopyasını paylaşabilirsiniz. Buna karşılık, bir statik bağlantı kitaplığı kullanılarak derlenen her bir uygulama, daha fazla disk alanı kullanır ve aktarmak için daha fazla bant genişliği alır, yürütülebilir görüntü bağlı kitaplık kodu var.

- Bakım, güvenlik düzeltmeleri ve yükseltmeleri daha kolay olabilir. Uygulamalarınızı bir DLL içinde ortak işlevlerini kullandığınızda, ardından işlev bağımsız değişkenleri ve dönüş değerlerini değiştirmeyin sürece, hata düzeltmeleri hazırlayın ve güncelleştirmeleri DLL'ye dağıtın. DLL'leri güncelleştirildiğinde, bunları kullanan uygulamaları yeniden derlenen ya da yeniden gerekmez ve dağıtıldıktan sürede yeni DLL'SİNİN kullanırlar. Buna karşılık, statik olarak bağlı nesne kodunda yaptığınız düzeltmeleri yeniden bağlayın ve onu kullanan her uygulamanın yeniden yapmanız gerekir.

- DLL'leri, kolayca destek sağlamak için kullanabilirsiniz. Örneğin, bir ekran sürücüsü DLL uygulama gönderildiğinde, derlenen bir görüntüyü destekleyecek şekilde değiştirilebilir. Açık bağlama uygulama uzantıları dll olarak yüklemek için kullanın ve yeniden oluşturma veya yeniden dağıtmaya gerek olmadan yeni işlevleri uygulamanıza ekleyin.

- Dinamik bağlama, farklı programlama dillerinde yazılan uygulamalar desteklemeyi kolaylaştırır. İşlev çağırma program uyduğu sürece farklı programlama dillerinde yazılan programlar aynı DLL işlevinin çağırabilirsiniz. Programlar ve DLL işlevini aşağıdaki yollarla uyumlu olmalıdır: işlev bağımsız değişkenleri bu da yığına itilecek bekleyen, işlev veya uygulama yığını temizleme işlemi için sorumlu olmasına ve herhangi bir bağımsız değişken olup sırası kayıtlara geçirilen.

- Dinamik bağlama, MFC Kitaplığı sınıflarını genişletecek bir mekanizma sağlar. Sınıfları varolan MFC sınıflarından ve MFC uygulamaları tarafından kullanılacak bir MFC uzantılı DLL yerleştirin.

- Dinamik bağlama, uygulamanızın uluslararası sürümlerin oluşturulmasını kolaylaştırır. Bir DLL içinde yerel ayara özgü kaynaklar yerleştirerek bir uygulamanın uluslararası sürümleri oluşturmak çok daha kolay olur. Uygulamanızı birçok yerelleştirilmiş sürümlerini aktarma yerine ayrı bir kaynak DLL içinde dizeleri ve her bir dilin görüntüleri yerleştirin ve ardından uygulamanızın çalışma zamanında, yerel ayar için uygun kaynakların yükleyebilirsiniz.

DLL'leri kullanmanın olası bir dezavantajı, uygulama kendi içinde değil olduğunu; Bu, dağıtmak veya kendiniz yüklemenizin bir parçası doğrulayın ayrı bir DLL modülü varlığını bağlıdır.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Oluşturma ve DLL'leri kullanma hakkında daha fazla bilgi

Aşağıdaki konular, Visual c++ programı DLL'leri hakkında ayrıntılı bilgi sağlar.

[İzlenecek yol: Oluşturma ve bir dinamik bağlantı kitaplığı (C++) kullanarak](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md) oluşturun ve Visual Studio kullanarak bir DLL'nin nasıl açıklar.

[DLL türleri](../build/kinds-of-dlls.md) farklı türlerde oluşturulabilir DLL'leri hakkında bilgi sağlar.

[DLL ile ilgili sık sorulan sorular](../build/dll-frequently-asked-questions.md) DLL'ler hakkında sık sorulan soruların yanıtlarını sağlar.

[Bir DLL'ye bağlandığı bir yürütülebilir dosya](../build/linking-an-executable-to-a-dll.md) DLL'ye açık ve örtük bağlantıları açıklar.

[DLL'yi Başlat](../build/run-time-library-behavior.md#initializing-a-dll) DLL dosyanız yüklendiğinde yürütülmesi gereken DLL ele alınmaktadır başlatma kod.

[DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md) çalışma zamanı kitaplığının DLL başlangıç dizisini nasıl gerçekleştirdiğini açıklar.

[LoadLibrary ve AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) kullanımını açıklar **LoadLibrary** ve `AfxLoadLibrary` çalışma zamanında bir DLL'ye açıkça bağlanmak için.

[GetProcAddress](../build/getprocaddress.md) kullanımını açıklar **GetProcAddress** DLL'de dışa aktarılan bir işlevin adresini almak için.

[FreeLibrary ve AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md) kullanımını açıklar **FreeLibrary** ve `AfxFreeLibrary` zaman DLL Modulü artık gerekli.

[Dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order) sistemde DLL bulmak için Windows işletim sisteminin kullandığı arama yolunu açıklar.

[Normal MFC DLL dinamik olarak bağlı MFC modül durumları](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md) MFC DLL dinamik olarak MFC'ye bağlı normal modül durumunu açıklar.

[MFC uzantı DLL'leri](../build/extension-dlls-overview.md) açıklar genellikle varolan Microsoft Foundation Class Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan DLL'leri.

[Resource-Only DLL oluşturma](../build/creating-a-resource-only-dll.md) simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren bir yalnızca kaynak DLL'sini açıklar.

[Yerelleştirilmiş MFC uygulamalarında kaynaklar: Uydu DLL'leri](../build/localized-resources-in-mfc-applications-satellite-dlls.md) Gelişmiş Uydu DLL'leri, çoklu dillerde yerelleşmiş uygulamalar oluşturmaya yardım eden bir özellik için destek sağlar.

[İçeri ve dışarı aktarma](../build/importing-and-exporting.md) ortak semboller bir uygulamaya aktarma veya işlevlerin DLL'den dışarı aktarma açıklar

[Etkin teknoloji ve DLL'ler](../build/active-technology-and-dlls.md) nesne sunucularının DLL içinde uygulanmasına izin verir.

[DLL'de Otomasyon](../build/automation-in-a-dll.md) MFC DLL Sihirbazı'ndaki Otomasyon seçeneğinin ne sağladığını açıklar.

[MFC DLL'leri için adlandırma kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions) MFC'de bulunan kitaplıkları ve DLL'lerin nasıl bir yapılandırılmış adlandırma kuralı izlediğini açıklar.

[Visual Basic uygulamalarından DLL işlevleri çağırma](../build/calling-dll-functions-from-visual-basic-applications.md) Visual Basic uygulamalarından DLL işlevleri çağırma açıklar.

## <a name="related-sections"></a>İlgili Bölümler

[Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md) , MFC kitaplığını Windows dinamik bağlantı kitaplığının bir parçası olarak kullanmanıza olanak tanır Normal MFC DLL'leri açıklar.

[MFC DLL sürümü](../mfc/tn033-dll-version-of-mfc.md) nasıl MFCxx.dll kullanabilirsiniz ve paylaşılan (burada x MFC sürüm numarasını adıdır) paylaşılan dinamik bağlantı kitaplıkları ile MFC uygulamaları ve MFC uzantısı DLL'leri açıklar.
