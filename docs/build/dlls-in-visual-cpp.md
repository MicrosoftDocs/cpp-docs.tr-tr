---
title: Visual Studio 'daC++ C/dll oluşturma
ms.date: 07/18/2019
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 9f5b34fda8a429f8e55631e1e0125ed6f79d5bae
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341073"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio 'daC++ C/dll oluşturma

Windows 'da, dinamik bağlantı kitaplığı (DLL), paylaşılan bir işlev ve kaynak kitaplığı olarak davranan bir tür yürütülebilir dosyadır. Dinamik bağlama, bir yürütülebilir dosyanın işlevleri çağırmasını veya ayrı bir dosyada depolanan kaynakları kullanmasını sağlayan bir işletim sistemi özelliğidir. Bu işlevler ve kaynaklar bunları kullanan yürütülebilir bilgisayarlardan ayrı olarak derlenebilir ve dağıtılabilir. DLL tek başına çalıştırılabilir değildir; Onu çağıran bir uygulama bağlamında çalışır. İşletim sistemi, uygulama yüklendiğinde (*örtük bağlantı*) veya çalışma zamanında (*Açık bağlama*) isteğe bağlı olarak DLL 'yi bir uygulamanın bellek alanına yükleyebilir. Dll 'Ler Ayrıca, çalıştırılabilir dosyalar arasında işlev ve kaynak paylaşmayı kolaylaştırır. Birden fazla uygulama, bellekteki tek bir DLL kopyasının içeriklerine aynı anda erişebilir.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>Dinamik bağlama ve statik bağlama arasındaki farklar

Statik bağlama, bir statik kitaplıktaki tüm nesne kodunu, derlendiklerinde kullanan yürütülebilir dosyalara kopyalar. Dinamik bağlama, yalnızca Windows 'un çalışma zamanında, bir veri öğesi veya işlevi içeren DLL 'yi bulmak ve yüklemek için gereken bilgileri içerir. Bir DLL oluşturduğunuzda, bu bilgileri içeren bir içeri aktarma kitaplığı da oluşturursunuz. DLL 'yi çağıran bir yürütülebilir dosya oluşturduğunuzda bağlayıcı, bu bilgileri Windows yükleyici için depolamak üzere içeri aktarma kitaplığındaki dışarı aktarılan sembolleri kullanır. Yükleyici bir DLL yüklediğinde, DLL, uygulamanızın bellek alanı ile eşleştirilir. Varsa, dll 'deki `DllMain`özel bir işlev, dll 'nin gerektirdiği bir başlatma işlemini gerçekleştirmek için çağırılır.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>Uygulamalar ve DLL 'Ler arasındaki farklılıklar

Dll 'Ler ve uygulamalar her ikisi de yürütülebilir modüller olsa da, çeşitli yollarla farklılık gösterir. Son kullanıcıya en belirgin fark, dll 'Lerin doğrudan yürütülebilecek uygulamalar olmadığı bir uygulamalardır. Sistemin görünüm noktasından uygulamalar ve DLL 'Ler arasında iki temel fark vardır:

- Bir uygulamanın sistemde aynı anda çalışan birden fazla örneği olabilir, ancak bir DLL yalnızca bir örneğe sahip olabilir.

- Bir uygulama, yığın, yürütme iş parçacıkları, genel bellek, dosya tanıtıcıları ve bir ileti sırası gibi öğelere sahip olabilecek bir işlem olarak yüklenebilir, ancak bir DLL olamaz.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Dll kullanmanın avantajları

Koda ve kaynaklara dinamik bağlama statik bağlama üzerinden çeşitli avantajlar sunar:

- Dinamik bağlama belleği kaydeder ve değiştirme azaltır. Birçok işlem bir DLL 'yi aynı anda kullanarak bir DLL 'nin salt okuma bölümlerinin tek bir kopyasını bellekten değiştirebilir. Buna karşılık, statik olarak bağlı bir kitaplık kullanılarak oluşturulan her uygulamanın, Windows 'un belleğe yüklenmesi gereken kitaplık kodunun tamamen bir kopyası vardır.

- Dinamik bağlama disk alanını ve bant genişliğini kaydeder. Birçok uygulama, disk üzerinde DLL 'nin tek bir kopyasını paylaşabilir. Buna karşılık, statik bağlantı kitaplığı kullanılarak oluşturulan her uygulamanın, daha fazla disk alanı kullanan ve aktarmaya daha fazla bant genişliği alan yürütülebilir görüntüsüne bağlı kitaplık kodu vardır.

- Bakım, güvenlik düzeltmeleri ve yükseltmeleri daha kolay olabilir. Uygulamalarınız DLL 'de ortak işlevleri kullanırken, işlev bağımsız değişkenleri ve dönüş değerleri değişmedikçe, hata düzeltmeleri uygulayabilir ve DLL 'ye güncelleştirme dağıtabilirsiniz. Dll 'Ler güncelleştirilirken, bunları kullanan uygulamaların yeniden derlenmesi veya yeniden bağlanması gerekmez ve dağıtıldıktan hemen sonra yeni DLL 'yi kullanmaları gerekir. Buna karşılık, statik olarak bağlı nesne kodunda yaptığınız düzeltmeler, onu kullanan her uygulamayı yeniden bağlamanız ve yeniden dağıtmanız gerekir.

- -Market 'ten sonra destek sağlamak için dll 'Leri kullanabilirsiniz. Örneğin, bir görüntü sürücüsü DLL 'SI, uygulama sevk edildiğinde kullanılamayan bir ekranı destekleyecek şekilde değiştirilebilir.

- Çalışma zamanında DLL 'LERI bulup yüklemek için açık bağlamayı kullanabilirsiniz (örneğin, uygulamanıza yeniden derleme veya yeniden dağıtmaya gerek kalmadan uygulamanıza yeni işlevler ekleyen uygulama uzantıları gibi).

- Dinamik bağlama, farklı programlama dillerinde yazılmış uygulamaları desteklemeyi kolaylaştırır. Farklı programlama dillerinde yazılan programlar, programlar işlevin çağırma kuralını izlediğinden aynı DLL işlevini çağırabilir. Programlar ve DLL işlevi aşağıdaki yollarla uyumlu olmalıdır: işlevin bağımsız değişkenlerini yığına itilmesi için beklediği sıra işlevin ya da uygulamanın yığının temizlenmesinden sorumlu olup olmadığı ve herhangi bir bağımsız değişken olup olmadığı geçirilen Yazmaçları.

- Dinamik bağlama MFC Kitaplık sınıflarını genişletmek için bir mekanizma sağlar. Mevcut MFC sınıflarından sınıfları türetebilir ve MFC uygulamaları tarafından kullanılmak üzere bunları bir MFC uzantı DLL 'sine yerleştirebilirsiniz.

- Dinamik bağlama, uygulamanızın uluslararası sürümlerinin oluşturulmasını kolaylaştırır. Dll 'Ler, bir uygulamanın uluslararası sürümlerini oluşturmayı çok daha kolay hale getirmek için, yerel ayara özgü kaynaklar sağlamak için kullanışlı bir yoldur. Uygulamanızın birçok yerelleştirilmiş sürümünü teslim etmek yerine, her dilin dize ve görüntülerini ayrı bir kaynak DLL 'ye yerleştirebilir ve sonra uygulamanız çalışma zamanında bu yerel ayar için uygun kaynakları yükleyebilir.

Dll kullanmanın potansiyel bir dezavantajı, uygulamanın kendi kendine dahil olmaması ve Bu, yüklemenizin bir parçası olarak kendinizi dağıtmanız veya doğrulamanız gereken ayrı bir DLL modülünün varlığına bağlıdır.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Dll 'Leri oluşturma ve kullanma hakkında daha fazla bilgi

Aşağıdaki konularda, Visual Studio 'da C/C++ dll oluşturma hakkında ayrıntılı bilgi sağlanmaktadır.

[İzlenecek yol: Dinamik Bağlantı Kitaplığı Oluşturma ve Kullanma (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Visual Studio kullanarak bir DLL'nin nasıl oluşturulacağı ve kullanılacağı açıklanmıştır.

[DLL Türleri](kinds-of-dlls.md)<br/>
Yapılandırılabilecek farklı DLL türleri hakkında bilgi sağlar.

[DLL hakkında sık sorulan sorular](dll-frequently-asked-questions.md)<br/>
DLL'ler hakkında sık sorulan soruların yanıtlarını sağlar.

[Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md)<br/>
DLL'ye olan açık ve örtük bağlantıları açıklar.

[DLL 'yi başlatma](run-time-library-behavior.md#initializing-a-dll)<br/>
DLL 'niz yüklenirken yürütülmesi gereken DLL başlatma kodunu açıklar.

[DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](run-time-library-behavior.md)<br/>
Çalışma zamanı kitaplığının DLL başlangıç dizisini nasıl gerçekleştirdiğini açıklar.

[LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)<br/>
Çalışma zamanında  bir dll `AfxLoadLibrary` 'ye açıkça bağlantı için LoadLibrary ve kullanmayı açıklar.

[GetProcAddress](getprocaddress.md)<br/>
DLL 'de dışarıya aktarılmış bir işlevin adresini almak için **GetProcAddress** kullanılarak açıklanır.

[FreeLibrary ve AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)<br/>
**FreeLibrary** ve `AfxFreeLibrary` dll modülünün artık gerekli olmadığı açıklanır.

[Dinamik bağlantı kitaplığı arama sırası](/windows/desktop/Dlls/dynamic-link-library-search-order)<br/>
Windows işletim sisteminin sistemde bir DLL bulmak için kullandığı arama yolunu açıklar.

[MFC'ye Dinamik Olarak Bağlı Normal MFC DLL'sinin Modül Durumları](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
MFC 'ye dinamik olarak bağlı normal bir MFC DLL 'nin modül durumlarını açıklar.

[MFC uzantısı DLL’leri](extension-dlls-overview.md)<br/>
Genel olarak varolan Microsoft Foundation Sınıf Kitaplığı sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan DLL'leri açıklar.

[Yalnızca Kaynak DLL Oluşturma](creating-a-resource-only-dll.md)<br/>
Simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren yalnızca kaynak DLL'sini açıklar.

[MFC Uygulamalarında Yerelleştirilmiş Kaynaklar: Uydu DLL'leri](localized-resources-in-mfc-applications-satellite-dlls.md)<br/>
Uydu DLL'lere gelişmiş destek, çoklu dillerde yerelleşmiş uygulamalar oluşturmaya yardım eden bir özellik sağlar.

[İçeri ve Dışarı Aktarma](importing-and-exporting.md)<br/>
Bir uygulamaya genel simgelerin nasıl içe aktarılacağını veya işlevlerin DLL'den nasıl dışa aktarılacağını açıklar

[Etkin Teknoloji ve DLL'ler](active-technology-and-dlls.md)<br/>
Nesne sunucularının DLL içinde uygulanmasına izin verir.

[DLL'de Otomasyon](automation-in-a-dll.md)<br/>
MFC DLL Sihirbazı'ndaki Otomasyon seçeneğinin ne sağladığını açıklar.

[MFC DLL'leri İçin Adlandırma Kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)<br/>
MFC'de bulunan DLL dosyalarının ve kitaplıkların nasıl bir yapılandırılmış adlandırma kuralı izlediğini açıklar.

[Visual Basic uygulamalarından DLL işlevleri çağırma](calling-dll-functions-from-visual-basic-applications.md)<br/>
Visual Basic uygulamalarından DLL işlevlerinin nasıl çağrılacağını açıklar.

## <a name="related-sections"></a>İlgili Bölümler

[DLL 'nin bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)<br/>
MFC kitaplığını Windows dinamik bağlantı kitaplığının bir parçası olarak kullanmanıza olanak sağlayan normal MFC DLL 'Lerini açıklar.

[MFC 'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)<br/>
MFCxx. dll ve MFCxxD. dll ' nin (x MFC sürüm numarası olduğu) MFC uygulamaları ve MFC uzantı dll 'Leri ile paylaşılan dinamik bağlantı kitaplıklarını nasıl kullanabileceğinizi açıklar.
