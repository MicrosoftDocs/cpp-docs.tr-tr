---
title: Visual Studio 'daC++ C/dll oluşturma
description: Visual Studio C++ 'Da dll 'lerin neden ve nasıl oluşturulacağı ve kullanılacağı hakkında genel bakış.
ms.date: 01/27/2020
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 7083924f137fa9283da40404c7d15183e59c0b1c
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821427"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio 'daC++ C/dll oluşturma

Windows 'da, dinamik bağlantı kitaplığı (DLL), paylaşılan bir işlev ve kaynak kitaplığı olarak davranan bir tür yürütülebilir dosyadır. Dinamik bağlama bir işletim sistemi özelliğidir. Bir yürütülebilir dosyanın işlevleri çağırmasını veya ayrı bir dosyada depolanan kaynakları kullanmasını sağlar. Bu işlevler ve kaynaklar bunları kullanan yürütülebilir bilgisayarlardan ayrı olarak derlenebilir ve dağıtılabilir.

DLL tek başına yürütülebilir dosya değildir. Dll 'Ler onları çağıran uygulamalar bağlamında çalışır. İşletim sistemi, DLL 'yi bir uygulamanın bellek alanına yükler. Uygulama yüklendiğinde (*örtük bağlantı*) veya çalışma zamanında (*Açık bağlama*) isteğe bağlı olarak yapılır. Dll 'Ler Ayrıca, çalıştırılabilir dosyalar arasında işlev ve kaynak paylaşmayı kolaylaştırır. Birden fazla uygulama, bellekteki tek bir DLL kopyasının içeriklerine aynı anda erişebilir.

## <a name="differences-between-dynamic-linking-and-static-linking"></a>Dinamik bağlama ve statik bağlama arasındaki farklar

Statik bağlama, bir statik kitaplıktaki tüm nesne kodunu, derlendiklerinde kullanan yürütülebilir dosyalara kopyalar. Dinamik bağlama, yalnızca Windows 'un çalışma zamanında, bir veri öğesi veya işlevi içeren DLL 'yi bulmak ve yüklemek için gereken bilgileri içerir. Bir DLL oluşturduğunuzda, bu bilgileri içeren bir içeri aktarma kitaplığı da oluşturursunuz. DLL 'yi çağıran bir yürütülebilir dosya oluşturduğunuzda bağlayıcı, bu bilgileri Windows yükleyici için depolamak üzere içeri aktarma kitaplığındaki dışarı aktarılan sembolleri kullanır. Yükleyici bir DLL yüklediğinde, DLL, uygulamanızın bellek alanı ile eşleştirilir. Varsa, DLL 'nin gerektirdiği bir başlatma yapmak için, `DllMain`DLL 'de özel bir işlev çağırılır.

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>Uygulamalar ve DLL 'Ler arasındaki farklılıklar

Dll 'Ler ve uygulamalar her ikisi de yürütülebilir modüller olsa da, çeşitli yollarla farklılık gösterir. En belirgin fark, bir DLL çalıştıramıyoruz. Sistemin görünüm noktasından uygulamalar ve DLL 'Ler arasında iki temel fark vardır:

- Bir uygulamanın sistemde aynı anda çalışan birden fazla örneği olabilir. DLL 'nin yalnızca bir örneği olabilir.

- Bir uygulama, işlem olarak yüklenebilir. Yığın, yürütme iş parçacıkları, genel bellek, dosya tanıtıcıları ve bir ileti kuyruğu gibi şeyler olabilir. Bir DLL bu şeylere sahip olamaz.

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Dll kullanmanın avantajları

Koda ve kaynaklara dinamik bağlama statik bağlama üzerinden çeşitli avantajlar sunar:

- Dinamik bağlama belleği kaydeder ve değiştirme azaltır. Birçok işlem bir DLL 'yi aynı anda kullanarak bir DLL 'nin salt okuma bölümlerinin tek bir kopyasını bellekten değiştirebilir. Buna karşılık, statik olarak bağlı bir kitaplık kullanılarak oluşturulan her uygulamanın, Windows 'un belleğe yüklenmesi gereken kitaplık kodunun tamamen bir kopyası vardır.

- Dinamik bağlama disk alanını ve bant genişliğini kaydeder. Birçok uygulama, disk üzerinde DLL 'nin tek bir kopyasını paylaşabilir. Buna karşılık, statik bağlantı kitaplığı kullanılarak oluşturulan her uygulamanın, yürütülebilir görüntüsüne bağlı kitaplık kodu vardır. Bu, daha fazla disk alanı kullanır ve aktarmaya daha fazla bant genişliği alır.

- Bakım, güvenlik düzeltmeleri ve yükseltmeler daha kolay olabilir. Uygulamalarınız DLL 'de ortak işlevleri kullanırken, hata düzeltmeleri uygulayabilir ve DLL 'ye güncelleştirme dağıtabilirsiniz. Dll 'Ler güncelleniyorsa, bunları kullanan uygulamaların yeniden derlenmesi veya yeniden bağlanması gerekmez. Bunlar dağıtıldıktan hemen sonra yeni DLL 'yi kullanabilir. Buna karşılık, statik olarak bağlanmış nesne kodunda düzeltmeler yaptığınızda, onu kullanan her uygulamayı yeniden bağlamanız ve yeniden dağıtmanız gerekir.

- -Market 'ten sonra destek sağlamak için dll 'Leri kullanabilirsiniz. Örneğin, bir görüntü sürücüsü DLL 'SI, uygulama sevk edildiğinde kullanılamayan bir ekranı destekleyecek şekilde değiştirilebilir.

- Çalışma zamanında DLL 'Leri bulup yüklemek için açık bağlamayı kullanabilirsiniz. Örneğin, uygulamanıza yeniden derleme veya yeniden dağıtma olmadan yeni işlevler ekleyen uygulama uzantıları.

- Dinamik bağlama, farklı programlama dillerinde yazılmış uygulamaları desteklemeyi kolaylaştırır. Farklı programlama dillerinde yazılan programlar, programlar işlevin çağırma kuralını izlediğinden aynı DLL işlevini çağırabilir. Programlar ve DLL işlevi aşağıdaki yollarla uyumlu olmalıdır: işlevin bağımsız değişkenlerini yığına itilmesi için beklediği sıra. Yığının temizlenmesinden bağımsız olarak işlevin mi yoksa uygulamanın mi sorumlu olduğu. Ve herhangi bir bağımsız değişkenin, yazmaçlara geçirilip geçirilmediğini belirtir.

- Dinamik bağlama, Microsoft Foundation sınıf kitaplığı (MFC) sınıflarını genişletmek için bir mekanizma sağlar. Mevcut MFC sınıflarından sınıfları türetebilir ve MFC uygulamaları tarafından kullanılmak üzere bunları bir MFC uzantı DLL 'sine yerleştirebilirsiniz.

- Dinamik bağlama, uygulamanızın uluslararası sürümlerinin oluşturulmasını kolaylaştırır. Dll 'Ler, bir uygulamanın uluslararası sürümlerini oluşturmayı çok daha kolay hale getirmek için, yerel ayara özgü kaynaklar sağlamak için kullanışlı bir yoldur. Uygulamanızın birçok yerelleştirilmiş sürümünü teslim etmek yerine, her dilin dize ve görüntülerini ayrı bir kaynak DLL 'de yerleştirebilirsiniz. Ardından, uygulamanız çalışma zamanında bu yerel ayar için uygun kaynakları yükleyebilir.

Dll kullanmanın potansiyel bir dezavantajı uygulamanın kendi kendine dahil olmaması olur. Bu, ayrı bir DLL modülünün varlığına bağlıdır: bir tane, yüklemenizin bir parçası olarak sizin dağıtmanız veya doğrulamanız gerekir.

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Dll 'Leri oluşturma ve kullanma hakkında daha fazla bilgi

Aşağıdaki makalelerde, Visual Studio 'da C/C++ dll oluşturma hakkında ayrıntılı bilgi sağlanmaktadır.

[İzlenecek yol: dinamik bağlantı kitaplığı oluşturma ve kullanma (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)\
Visual Studio kullanarak bir DLL'nin nasıl oluşturulacağı ve kullanılacağı açıklanmıştır.

[DLL türleri](kinds-of-dlls.md)\
Yapılandırılabilecek farklı DLL türleri hakkında bilgi sağlar.

[DLL hakkında sık sorulan sorular](dll-frequently-asked-questions.md)\
DLL'ler hakkında sık sorulan soruların yanıtlarını sağlar.

[Yürütülebilir dosyayı dll 'ye bağlama](linking-an-executable-to-a-dll.md)\
DLL'ye olan açık ve örtük bağlantıları açıklar.

[DLL 'Yi başlatma](run-time-library-behavior.md#initializing-a-dll)\
DLL 'niz yüklenirken yürütülmesi gereken DLL başlatma kodunu açıklar.

[DLL 'ler ve C++ görsel çalışma zamanı kitaplığı davranışı](run-time-library-behavior.md)\
Çalışma zamanı kitaplık DLL başlangıç sırasını açıklar.

[LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)\
Çalışma zamanında bir DLL 'ye açıkça bağlanmak için `LoadLibrary` ve `AfxLoadLibrary` kullanımını açıklar.

[GetProcAddress](getprocaddress.md)\
DLL 'deki bir dışarıya aktarılmış işlevin adresini almak için `GetProcAddress` kullanmayı açıklar.

[FreeLibrary ve AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)\
DLL modülüne artık gerek kalmadığında `FreeLibrary` ve `AfxFreeLibrary` kullanımını açıklar.

[Dinamik bağlantı kitaplığı arama sırası](/windows/win32/Dlls/dynamic-link-library-search-order)\
Windows işletim sisteminin sistemde bir DLL bulmak için kullandığı arama yolunu açıklar.

[MFC 'ye dinamik olarak bağlı normal MFC DLL 'Nin modül durumları](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)\
MFC 'ye dinamik olarak bağlı normal bir MFC DLL 'nin modül durumlarını açıklar.

[MFC uzantı dll 'leri](extension-dlls-overview.md)\
Genellikle var olan MFC sınıflarından türetilen yeniden kullanılabilir sınıfları uygulayan dll 'Leri açıklar.

[Yalnızca kaynak DLL\ oluşturma](creating-a-resource-only-dll.md)
Simgeler, bit eşlemler, dizeler ve iletişim kutuları gibi kaynakları içeren yalnızca kaynak DLL'sini açıklar.

[MFC uygulamalarında yerelleştirilmiş kaynaklar: uydu dll 'leri](localized-resources-in-mfc-applications-satellite-dlls.md)\
Uydu DLL'lere gelişmiş destek, çoklu dillerde yerelleşmiş uygulamalar oluşturmaya yardım eden bir özellik sağlar.

\ [içeri ve dışarı aktarma](importing-and-exporting.md)
Bir uygulamaya genel simgelerin nasıl içe aktarılacağını veya işlevlerin DLL'den nasıl dışa aktarılacağını açıklar

[Etkin teknoloji ve DLL 'ler](active-technology-and-dlls.md)\
Nesne sunucularının DLL içinde uygulanmasına izin verir.

[DLL 'de otomasyon](automation-in-a-dll.md)\
MFC DLL Sihirbazı'ndaki Otomasyon seçeneğinin ne sağladığını açıklar.

[MFC DLL 'leri Için adlandırma kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)\
MFC'de bulunan DLL dosyalarının ve kitaplıkların nasıl bir yapılandırılmış adlandırma kuralı izlediğini açıklar.

[Visual Basic UYGULAMALARDAN dll Işlevleri çağırma](calling-dll-functions-from-visual-basic-applications.md)\
Visual Basic uygulamalarından DLL işlevlerinin nasıl çağrılacağını açıklar.

## <a name="related-sections"></a>İlgili Bölümler

[DLL 'nin bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)\
MFC kitaplığını Windows dinamik bağlantı kitaplığının bir parçası olarak kullanmanıza olanak sağlayan normal MFC DLL 'Lerini açıklar.

[MFC\ dll sürümü](../mfc/tn033-dll-version-of-mfc.md)
MFCxx. dll ve MFCxxD. dll ' nin (x MFC sürüm numarası olduğu) MFC uygulamaları ve MFC uzantı dll 'Leri ile paylaşılan dinamik bağlantı kitaplıklarını nasıl kullanabileceğinizi açıklar.
