---
title: Visual Studio'da C/C++ DLL'leri oluşturma
ms.date: 05/06/2019
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 7f1c2b71a58c59bf0662aa4ffec53344ce657df0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220751"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio'da C/C++ DLL'leri oluşturma

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

C oluşturma hakkında ayrıntılı bilgi aşağıdaki konularda /C++ Visual Studio'daki DLL'ler.

[İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Visual Studio kullanarak bir DLL'nin nasıl oluşturulacağı ve kullanılacağı açıklanmıştır.

[DLL Türleri](kinds-of-dlls.md)<br/>
Yapılandırılabilecek farklı DLL türleri hakkında bilgi sağlar.

[Sıkça Sorulan DLL soruları](dll-frequently-asked-questions.md)<br/>
DLL'ler hakkında sık sorulan soruların yanıtlarını sağlar.

[Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md)<br/>
DLL'ye olan açık ve örtük bağlantıları açıklar.

[DLL'yi Başlat](run-time-library-behavior.md#initializing-a-dll)<br/>
DLL dosyanız yüklendiğinde yürütülmesi gereken DLL başlatma kodunu açıklanır.

[DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](run-time-library-behavior.md)<br/>
Çalışma zamanı kitaplığının DLL başlangıç dizisini nasıl gerçekleştirdiğini açıklar.

[LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)<br/>
Kullanımını açıklar **LoadLibrary** ve `AfxLoadLibrary` çalışma zamanında bir DLL'ye açıkça bağlanmak için.

[GetProcAddress](getprocaddress.md)<br/>
Kullanımını açıklar **GetProcAddress** DLL'de dışa aktarılan bir işlevin adresini almak için.

[FreeLibrary ve AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)<br/>
Kullanımını açıklar **FreeLibrary** ve `AfxFreeLibrary` zaman DLL Modulü artık gerekli.

[Dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order)<br/>
Windows işletim sisteminin sistemde DLL bulmak için kullandığı arama yolunu açıklar.

[MFC'ye Dinamik Olarak Bağlı Normal MFC DLL'sinin Modül Durumları](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
MFC DLL dinamik olarak MFC'ye bağlı normal modül durumunu açıklar.

[MFC uzantısı DLL’leri](extension-dlls-overview.md)<br/>
Genel olarak varolan Microsoft Foundation Sınıf Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan DLL'leri açıklar.

[Yalnızca Kaynak DLL Oluşturma](creating-a-resource-only-dll.md)<br/>
Simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren yalnızca kaynak DLL'sini açıklar.

[MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri](localized-resources-in-mfc-applications-satellite-dlls.md)<br/>
Uydu DLL'lere gelişmiş destek, çoklu dillerde yerelleşmiş uygulamalar oluşturmaya yardım eden bir özellik sağlar.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)<br/>
Bir uygulamaya genel simgelerin nasıl içe aktarılacağını veya işlevlerin DLL'den nasıl dışa aktarılacağını açıklar

[Etkin Teknoloji ve DLL'ler](active-technology-and-dlls.md)<br/>
Nesne sunucularının DLL içinde uygulanacak şekilde sağlar.

[DLL'de Otomasyon](automation-in-a-dll.md)<br/>
MFC DLL Sihirbazı'ndaki Otomasyon seçeneğinin ne sağladığını açıklar.

[MFC DLL'leri İçin Adlandırma Kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)<br/>
MFC'de bulunan DLL dosyalarının ve kitaplıkların nasıl bir yapılandırılmış adlandırma kuralı izlediğini açıklar.

[Visual Basic uygulamalarından DLL işlevleri çağırma](calling-dll-functions-from-visual-basic-applications.md)<br/>
Visual Basic uygulamalarından DLL işlevlerinin nasıl çağrılacağını açıklar.

## <a name="related-sections"></a>İlgili Bölümler

[Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)<br/>
MFC kitaplığını Windows dinamik bağlantı kitaplığının bir parçası olarak kullanmanıza olanak Normal MFC DLL'leri açıklar.

[MFC'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)<br/>
MFCxx.dll kullanabilirsiniz ve (burada x MFC sürüm numarasıdır) paylaşılan dinamik bağlantı kitaplıkları paylaşılan MFC uygulamaları ve MFC uzantısı DLL'leri ile nasıl açıklanmaktadır.
