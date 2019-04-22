---
title: Olası yükseltme sorunlarına (Visual C++) genel bakış
ms.date: 11/04/2016
ms.assetid: 2c99a8cb-098f-4a9d-bf2c-b80fd06ace43
ms.openlocfilehash: 1dac6ad201656dc83428aa5182a59cb8ff824651
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58898836"
---
# <a name="overview-of-potential-upgrade-issues-visual-c"></a>Olası yükseltme sorunlarına (Visual C++) genel bakış

Yıllar içinde Microsoft Visual C++ Derleyici C++ dili, C++ Standart Kitaplığı, C çalışma zamanı (CRT) ve MFC ve ATL gibi diğer kitaplıkları değişiklikleri birlikte birçok değişiklik gerçekleştirdi Sonuç olarak, bir uygulama, Visual Studio'nun önceki bir sürümden yükseltirken, derleyici ve bağlayıcı hataları ve Uyarıları düzgün bir şekilde daha önce derlenmiş kodda karşılaşabilirsiniz. Eski özgün kod tabanı, bu tür hatalar daha olası. Bu genel bakışta karşılaşabileceğiniz olası sorunların en yaygın sınıfları özetler ve daha ayrıntılı bilgi için bağlantılar sağlar.

> [!NOTE]
> Geçmişte, birçok Visual Studio sürümü span yükseltmeleri aynı anda gerçekleştirilen artımlı olarak bir sürüm olması gerektiğini önerilir. Artık bu yaklaşım önerilir. Bunun hemen her zaman ne kadar eski kod tabanı ne olursa olsun Visual Studio'nun en güncel sürüme yükseltmek daha basit olduğunu bulduk.

Sorularınız veya yükseltme işlemi hakkında yorumlar göndermenin vcupgrade@microsoft.com.

## <a name="library-and-toolset-dependencies"></a>Kitaplık ve araç takımı bağımlılıkları

Uygulamanın yeni bir Visual Studio sürümüne yükseltirken önemle tavsiye edilir ve çoğunda da tüm kitaplıkları ve uygulamanın bağlandığı DLL'leri yükseltmek için gereken durumlarda. Bu, kaynak koduna erişim iznine sahip veya kitaplık satıcı yeni ikili dosyaları aynı ana sürümüne derleyici ile derlenmiş sağlayabilir gerektirir. Şu koşullardan biri doğruysa, ikili uyumluluğu ayrıntılarını ile ilgilenen bu bölümü atlayabilirsiniz. Yükseltilen uygulamanızdaki kitaplıkları kullanmayı mümkün olmayabilir sonra hiçbiri bu durumda, vardır. Bu bölümdeki bilgiler, yükseltme işlemine devam olup olmadığını anlamanıza yardımcı olur.

### <a name="toolset"></a>Araç Takımı

.Obj ve .lib dosyası biçimleri, iyi tanımlanmış ve nadiren değiştirin. Bu dosya biçimleri için yapılan eklemeler bazen, ancak bu eklemeler nesne dosyaları ve kitaplıkları eski araç takımları tarafından üretilen kullanma olanağı yeni araç takımları, genellikle etkilemez. Büyük burada kullanarak derlerseniz işlemdir [/GL (bütün Program iyileştirmesi)](../build/reference/gl-whole-program-optimization.md). Kullanarak derleme yaparsanız `/GL`, sonuçta elde edilen nesne dosyası yalnızca bu üretmek için kullanılan araç kümesini kullanarak bağlanabilir. Bu nedenle sahip bir nesne dosyası üretmek `/GL` ve Visual Studio 2017 (v141) derleyici kullanarak, Visual Studio 2017 (v141) bağlayıcı kullanarak bağlanmalıdır. Nesne dosyalarının iç veri yapılarını araç ana sürümler arasında tutarlı değildir ve yeni araç takımları eski veri biçimlerini anlaşılmıyor nedeni budur.

C++, kararlı uygulama ikili arabiriminde (ABI) yok. Visual Studio, kararlı bir C++ ABI'SİNDE yayın tüm ikincil sürümlerinin tutar. Örneğin, Visual Studio 2017 ve tüm güncelleştirmeleri ikili uyumludur. Ancak ABI ana Visual Studio sürümleri arasında mutlaka uyumlu değil (2015 ve 2017, hangi _olan_ uyumlu ikili). Diğer bir deyişle, biz C++ türü düzeni, ad düzenlemesi, özel durum işleme ve diğer bölümlerini C++ ABI'SİNDE bozucu değişiklikler yapabilir. C++ bağlantısı olan dış sembolü olmayan bir nesne dosyası varsa, bu nedenle, bu nesne dosyası doğru şekilde farklı bir ana sürümü araç takımı ile üretilen nesne dosyaları ile bağlayamazsınız. Burada "çalışmayabilir" Not sahip birçok sonuçtan: bağlantı tamamen başarısız olabilir (örneğin ad düzenlemesi değiştirdiyseniz), bağlantı başarısız olabilir ve çalışma zamanında şeyler çalışmayabilir (örn türü düzeni değişirse), şeyler durum çoğu zaman çalışmaya oluşabilir veya hiçbir şey wro geçer NG. Ayrıca C++ ABI'SİNDE C ABI kararlı ve C++ ABI'SİNDE alt kümesi için gerekli olmamasına karşın COM kararlı dikkat edin.

Bir içeri aktarma kitaplığına bağlarsanız, sonraki bir sürümünü ABI uyumluluğu korumak Visual Studio yeniden dağıtılabilir kitaplıkların çalışma zamanında kullanılabilir. Örneğin, uygulamanız derlenir ve Visual Studio 2015 güncelleştirme 3 araç takımı kullanarak bağlı, 2015 veya 2017 kitaplıkları ikili geriye dönük uyumluluk korunur olduğundan tüm Visual Studio 2017 yeniden dağıtılabilir, kullanabilirsiniz. Tersi doğru değildir; uyumlu bir ABI olsa bile, kodunuzu derlemek için kullanılan çok yeniden dağıtılabilir araç önceki bir sürümü için kullanamazsınız.

### <a name="libraries"></a>Kitaplıklar

Visual Studio C++ kitaplıkları üst bilgi dosyaları belirli bir sürümünü kullanarak bir kaynak dosyasını derlerseniz (tarafından # üst bilgiler including), sonuçta elde edilen nesne dosyası kitaplıkları aynı sürümü ile bağlanması gerekir. Böylece, örneğin, kaynak dosyanız Visual Studio 2015 güncelleştirme 3 ile derlenmişse \<immintrin.h >, Visual Studio 2015 güncelleştirme 3'ü vcruntime kitaplığıyla bağlamanız gerekir. Benzer şekilde, kaynak dosyanız Visual Studio 2017 sürüm 15.5 ile derlenmiş olan \<iostream >, Visual Studio 2017 sürüm 15.5 standart C++ kitaplığı ile msvcprt bağlamanız gerekir. Karıştırma ve eşleşen desteklenmiyor.

C++ Standart Kitaplığı için karıştırma ve eşleşen açıkça kullanımı aracılığıyla verilmedi `#pragma detect_mismatch` Visual Studio 2010 itibaren standart üst bilgisindeki. Uyumsuz nesne dosyalarını bağlamanız deneyin veya bağlantı yanlış standart kitaplığı ile çalıştığınızda, bağlantı başarısız olur

CRT karıştırma ve eşleşen hiçbir zaman destekleniyordu, ancak bir API yüzeyi çoğu zaman içinde değiştirmediğinden genellikle yalnızca, en az Visual Studio 2015 ve evrensel CRT kadar çalıştınız. Böylece gelecekte biz geriye dönük uyumluluğu korumak Evrensel CRT geriye dönük uyumluluk kesildi. Diğer bir deyişle, yeni, gelecekte tutulan Evrensel CRT ikili tanıtmak için herhangi bir plan sahibiz. Bunun yerine, mevcut Evrensel CRT sunulmuştur yerinde güncelleştirilir.

Nesne dosyaları (ve kitaplıklar) eski sürümleri Microsoft C çalışma zamanı üst bilgileri ile derlenmiş kısmi bağlantı uyum sağlamak için bir kitaplık legacy_stdio_definitions.lib, Visual Studio 2015 ve sonraki sunuyoruz. Bu kitaplık uyumluluk semboller için evrensel CRT kaldırılan işlevleri ve verileri dışarı aktarmaları çoğunu sağlar. Uyumluluk sembolleri legacy_stdio_definitions.lib tarafından sağlanan dizi tüm bağımlılıkları Windows SDK'da bulunan kitaplıkları dahil olmak üzere çoğu bağımlılıklarını karşılamak yeterli olur. Ancak, böyle uyumluluk sembolleri sağlamak mümkün değil Evrensel CRT'den kaldırılan bazı simgeleri vardır. Bazı işlevler bu simgeleri dahil et (örn, \_ \_iob\_func) ve veri dışarı aktarmaları (örneğin, \_ \_Imp\_\_\_iob, \_ \_Imp\_\_\_pctype, \_ \_Imp\_\_\_mb\_ven\_max).

C çalışma zamanı üst bilgileri daha eski bir sürümüyle oluşturulmuş bir statik kitaplık varsa, aşağıdaki eylemleri (bu sırayla) öneririz:

1. Statik kitaplık ile Evrensel CRT bağlama desteklemek için Visual Studio 2017 ve evrensel CRT üst bilgileri kullanarak yeniden oluşturun. Tam olarak desteklenir (ve bu nedenle en iyi) seçenek budur.

1. Olamaz (veya istemiyorsanız) ile eski bağlama çalışabilir, statik kitaplık yeniden\_stdio\_definitions.lib. Bağlama zamanı bağımlılıklarını, statik kitaplık uyuyorsa, ikili dosyada bu olumsuz herhangi biri tarafından etkilenmemesini emin olmak için kullanıldığı gibi statik kitaplık sınamanız isteyeceksiniz [yapılan davranış değişiklikleri Evrensel CRT](visual-cpp-change-history-2003-2015.md#BK_CRT).

1. Statik kitaplık bağımlılıkları eski tarafından tatmin edici değil\_stdio\_definitions.lib veya yukarıda sözü edilen davranış değişiklikleri nedeniyle Evrensel CRT kitaplığı çalışmıyor, şifrelenmiş önerilir, Microsoft C çalışma zamanı doğru sürümü ile bağlantı bir DLL statik kitaplığa. Örneğin, statik kitaplık Visual Studio 2013 kullanılarak oluşturulduysa, Visual Studio 2013 ve Visual Studio 2013 C++ kitaplıkları da kullanarak bu DLL'yi oluşturmak istiyorsunuz. Bir DLL içine kitaplığı oluşturarak, belirli bir Microsoft C çalışma zamanı sürümü bağımlı olan uygulama ayrıntısı kapsüller. (DLL arabirimi hangi C çalışma zamanı, örneğin dosya * veya DLL sınırı arasında malloc ayrılan bir işaretçi döndüren ve ücretsiz için çağıranı bekleniyor döndürerek kullandığı ayrıntıları sızıntı değil dikkatli olmak isteyeceksiniz unutmayın.)

Tek bir işlemde birden çok büyüklükteki CRT'lerden değil ve (aslında çoğu işlemler birden çok CRT DLL'leri yükleme sona erer; Örneğin, Windows işletim sistemi bileşenleri üzerinde msvcrt.dll bağlıdır ve CLR kendi özel CRT üzerinde bağlıdır) sorunlu kendisinin kullanılır. Farklı büyüklükteki CRT'lerden durumundan jumble olduğunda sorunları ortaya çıkar. Örneğin, değil msvcr110.dll!malloc kullanarak bellek ayırma ve msvcr120.dll!free kullanarak bu belleği serbest bırakma girişimi ve msvcr110 kullanarak bir dosyayı açmaya çalışmamalısınız! dosya fopen ve buradan okuma girişimi msvcr120 kullanarak! fread. Farklı büyüklükteki CRT'lerden durumundan jumble yoksa sürece, güvenli bir şekilde tek bir işlemde yüklü birden fazla büyüklükteki CRT'lerden olabilir.

Daha fazla bilgi için [kodunuzu Evrensel CRT'ye yükseltme](upgrade-your-code-to-the-universal-crt.md).

## <a name="errors-due-to-project-settings"></a>Hatalar nedeniyle proje ayarları

Yükseltme işlemine başlamak için bir eski proje/çözüm/çalışma alanı Visual Studio'nun en son sürümünde açın. Visual Studio, eski proje ayarlarına göre yeni bir proje oluşturur. Eski proje kitaplığın veya standart olmayan konumlara sabit kodlanmış yollar içeriyorsa, bu projenin varsayılan ayarları kullanır, bu yollar dosyalarında derleyici için görünür olmaz mümkündür. Daha fazla bilgi için [bağlayıcı ÇıkışDosyası ayarının](porting-guide-spy-increment.md#linker_output_settings).

Genel olarak, artık proje Bakımı basitleştirmek için proje kodunuzun düzgün şekilde düzenlemek için mükemmel bir fırsattır ve Yardım olabildiğince çabuk derleme yükseltilen kodunuzu alın. Kaynak kodunuzu zaten iyi düzenlenmiş ve Visual Studio 2010 veya sonraki bir sürümü eski projeniz derlenir, derleme üzerinde hem bir eski ve yeni derleyici desteği için yeni proje dosyasını el ile düzenleyebilirsiniz. Aşağıdaki örnek, Visual Studio 2015 ve Visual Studio 2017 için derleme gösterilmektedir:

```xml
<PlatformToolset Condition="'$(VisualStudioVersion)'=='14.0'">v140</PlatformToolset>
<PlatformToolset Condition="'$(VisualStudioVersion)'=='15.0'">v141</PlatformToolset>
```

### <a name="lnk2019-unresolved-external"></a>LNK2019: Çözülmemiş dış öğe

Çözülmemiş simgeler için proje ayarlarınızın düzeltme gerekebilir.

- Varsayılan olmayan bir konumda, projenin yolu eklemek yaptığınız kaynak dosyası ise, dizinleri dahil edilsin mi?

- Dış bir .lib dosyasına tanımlanmazsa, proje özelliklerinde LIB yol belirttiğinizden ve aslında burada bulunan .lib dosyası doğru sürümü nedir?

- Farklı bir Visual Studio sürümü ile derlenen bir .lib dosyasına bağlantı çalışıyorsunuz? Bu durumda, önceki bölümde kitaplık ve araç takımı bağımlılıkları bakın.

- Çağrı sitesinde bağımsız değişkenlerinin türlerine gerçekten var olan bir aşırı işlevin eşleşiyor mu? İşlev imzası ve işlevi çağıran kodu her tür tanımları için temel alınan türler olmalarını beklediğiniz olduğundan emin olun.

Çözümlenmeyen sembol hataları gidermek için bir ikili dosyada tanımlanan simgeleri incelemek için dumpbin.exe kullanmayı deneyebilirsiniz. Bir kitaplık tanımlanan semboller görüntülemek için şu komut satırını deneyin:

```cmd
dumpbin.exe /LINKERMEMBER somelibrary.lib
```

### <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

(Microsoft Visual içinde C++ 6.0 ve önceki sürümleri, **wchar_t** yerleşik bir tür olarak uygulanmadı, ancak wchar.h içinde işaretsiz için bir typedef bildirildi.) C++ Standart gerektirir **wchar_t** yerleşik bir tür olabilir. Typedef sürümünü kullanarak, taşınabilirlik sorunlarına neden olabilir. Visual Studio'nun önceki sürümlerinden yükseltin ve kod örtük dönüştürmeye çalıştığı için derleyici hatası C2664 karşılaştığınız bir **wchar_t** için **işaretsiz**, size değiştirmenizi öneririz ayar yerine hatayı gidermek için kod `/Zc:wchar_t-`. Daha fazla bilgi için [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

### <a name="upgrading-with-the-linker-options-nodefaultlib-entry-and-noentry"></a>/ Nodefaultlıb/Entry ve/NOENTRY bağlayıcı seçenekleri ile yükseltme

`/NODEFAULTLIB` Bağlayıcı seçeneği (veya tüm varsayılan kitaplıkları yoksay bağlayıcı özelliği) bağlayıcıya otomatik olarak varsayılan kitaplık CRT gibi bağlantısını değil. Bu, her kitaplık giriş olarak listelenen ayrı ayrı olduğu anlamına gelir. Bu kitaplıklar listesi verilir **ek bağımlılıklar** özelliğinde **bağlayıcı** bölümünü **proje özellikleri** iletişim.

Bazı varsayılan kitaplık adlarını değiştirdiğiniz için bu seçeneği kullanın projeleri yükseltme yaparken, bir sorun sunar. Her kitaplık yer alması gerektiğinden **ek bağımlılıklar** özelliği veya bağlayıcı komut satırında kitaplıkların geçerli adları listesini güncelleştirmeniz gerekir.

Aşağıdaki tablo, Visual Studio 2015 ile başlayan adları değiştirildi kitaplıkları gösterir. Yükseltmek için ikinci sütun adları ile ilk sütun adlarını değiştirmeniz gerekiyor. Bu kitaplıklar içeri aktarma kitaplıkları bazıları, ancak önemli olmamalıdır.

|||
|-|-|
|Kullandıysanız:|İle değiştirmeniz gerekir:|
|libcmt.lib|libucrt.lib, libvcruntime.lib|
|libcmtd.lib|libucrtd.lib, libvcruntimed.lib|
|msvcrt.lib|ucrt.lib, vcruntime.lib|
|msvcrtd.lib|ucrtd.lib, vcruntimed.lib|

Aynı sorunu, ayrıca kullandığınız geçerlidir `/ENTRY` seçeneği veya `/NOENTRY` varsayılan kitaplık atlayarak etkisini de seçeneği.

## <a name="errors-due-to-improved-language-conformance"></a>Hatalar nedeniyle geliştirilmiş dil uyumluluğu

Microsoft Visual C++ derleyicisi, sürekli olarak, standart C++ uyumluluk yıllar içinde geliştirdi. Önceki sürümlerinde derlenmiş kod, Visual Studio 2017'de derleyici doğru açıkça izin verilen veya önceden yoksayıldı hata işaretler çünkü derleme başarısız olabilir.

Örneğin, `/Zc:forScope` anahtar erken MSVC geçmişinde tanıtılmıştır. Bu davranışı loop değişkenleri DSCP izin verir. Bu anahtar artık kullanım dışıdır ve gelecek sürümlerde kaldırılabilir. Bu anahtar, kodunuzu yükseltirken kullanmayacak şekilde önemle tavsiye edilir. Daha fazla bilgi için [/Zc:forScope-kullanım dışı](porting-guide-spy-increment.md#deprecated_forscope).

Const olmayan bir bağımsız değişken için const bir parametre olarak geçirildiğinde yükseltirken görebileceğiniz ortak bir derleyici hatası için bir örnektir. Eski sürümleri, derleyici her zaman bu hata olarak bayrak. Daha fazla bilgi için [derleyicinin daha katı dönüştürmeler](porting-guide-spy-increment.md#stricter_conversions).

Belirli bir uyumluluk geliştirmeleri hakkında daha fazla bilgi için bkz. [Visual C++ değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md) ve [Visual Studio'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md).

## <a name="errors-involving-stdinth-integral-types"></a>Hatalar içeren \<stdint.h > tam sayı türleri

\<Stdint.h > Üstbilgi typedefs tanımlar ve, yerleşik tam sayı türleri farklı garanti makroları, tüm platformlarda belirtilen uzunluğa sahip. Bazı örnekler `uint32_t` ve `int64_t`. \<Stdint.h > üst bilgi, Visual Studio 2010'da eklendi. 2010'dan önce yazılmış kod, bu türleri için özel tanımları sağlanan ve bu tanımları her zaman ile tutarlı olmayabilir \<stdint.h > tanımlar.

Hatası C2371 ise ve a `stdint` türü eklendiyse, bu büyük olasılıkla türü kodunuzu veya üçüncü taraf kitaplığı dosya üstbilgisinde tanımlanır anlamına gelir. Yükseltme sırasında hiçbir özel tanımları ortadan \<stdint.h > türlerini, ancak ilk geçerli standart tanımları özel tanımları karşılaştırmak, değil Karşınızda yeni sorunlar emin olmak için.

Basabilirsiniz **F12** (**Tanıma Git**) söz konusu tür tanımlandığı görmek için.

[/Showıncludes](../build/reference/showincludes-list-include-files.md) derleyici seçeneği yararlı olabilir burada. İçinde **özellik sayfaları** iletişim kutusunu açın, projeniz için **C/C++** > **Gelişmiş** sayfasında ve ayarlayın **Göster içerir** için **Evet**. Ardından projenizi yeniden derleyin ve listesini `#include`çıktı penceresinde s. Her bir üst bilgi içeren bir üst bilgisi altında girintili hale getirilir.

## <a name="errors-involving-crt-functions"></a>CRT işlevlerinin ilgili hatalar

Birçok değişiklik için C çalışma zamanı yıllar içinde yapıldı. İşlevlerin güvenli sürümleri birçok eklenen ve bazı kaldırıldı. Ayrıca, bu makalenin önceki bölümlerinde açıklandığı gibi CRT, Microsoft'un uygulama Visual Studio 2015'te yeni ikili dosyaları ve ilişkili .lib dosyaları halinde yeniden düzenlenmeden.

Hata bir CRT işlevini içeriyorsa, arama [Visual C++ değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md) veya [Visual Studio'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md) bu konulara ek bilgileri içerip içermediğini görmek için. Hatası LNK2019, çözülmemiş dış ise işlev kaldırılmamıştır emin olun. İşlev hala mevcut olduğundan ve çağırma kodunun doğru olduğundan emin olup, aksi takdirde, projenizi kullanıp kullanmadığını denetleyin `/NODEFAULTLIB`. Bu durumda, böylece yeni evrensel (UCRT) kitaplıkları kullanan proje kitaplıkların listesini güncelleştirmeniz gerekir. Kitaplık ve bağımlılıklarını daha fazla bilgi için yukarıdaki bölüme bakın.

Hata içeriyorsa `printf` veya `scanf`, özel olarak ya da işlev stdio.h dahil etmeden tanımladığınız değil, emin olun. Bu durumda, özel tanımları kaldırın veya bağlantısını için eski\_stdio\_definitions.lib. Bunu ayarlayabilirsiniz **özellik sayfaları** iletişim altında **yapılandırma özellikleri** > **bağlayıcı** > **giriş**, **ek bağımlılıklar** özelliği. Windows 8.1 SDK'sı ile bağlama veya önceki bir sürümü varsa, eski eklersiniz\_stdio\_definitions.lib.

Biçim dizesi bağımsız değişkenleri hata içeriyorsa, derleyici standart zorlama hakkında daha sıkı büyük olasılıkla olmasıdır. Değişiklik geçmişini daha fazla bilgi için bkz. Bir güvenlik riski potansiyel olarak temsil edebilir çünkü Lütfen Kapat hataları burada dikkat edin.

## <a name="errors-due-to-changes-in-the-c-standard"></a>C++ Standart değişiklikleri nedeniyle hataları

C++ Standart her zaman geriye dönük olarak uyumlu olmayan şekilde gelişmiştir. C ++ 11 taşıma semantiği, yeni anahtar sözcükleri ve diğer dili ve standart kitaplık özellikleri giriş, potansiyel olarak derleyici hatalarına neden olur ve hatta farklı çalışma zamanı davranışı.

Örneğin, eski bir C++ programını iostream.h üst bilgisi içerebilir. Bu üstbilgi C++ geçmişinde erken kullanım dışı bırakıldı ve Visual Studio'dan sonuçta tamamen kaldırıldı. Bu durumda, kullanmanız gerekecektir \<iostream > ve kodunuzu yeniden yazma. Daha fazla bilgi için [eski iostreams kodunu güncelleştirme](porting-guide-spy-increment.md#updating_iostreams_code).

### <a name="c4838-narrowing-conversion-warning"></a>C4838: dönüştürme uyarı daraltma

C++ standardı artık işaretsiz dönüşümlerse imzalı tam sayı değerlerine daraltma dönüşümleri olarak kabul edilir belirtir. Derleyici bu uyarıyı önce Visual Studio 2015 vermedi. Kodunuzun doğruluğunu etkileyebilir değil daraltma mu emin olmak için her oluşumu incelemeniz gerekir.

## <a name="warnings-to-use-secure-crt-functions"></a>Güvenli CRT işlevleri kullanmak için uyarılar

C çalışma zamanı işlevlerin güvenli sürümleri yıllar içinde tanıtılmıştır. Eski ve güvenli olmayan sürümler hala kullanılabilir olsa da, kodunuzu güvenli sürümler kullanmak için değiştirmeniz önerilir. Derleyici, güvenli olmayan sürümlerden kullanımı için bir uyarı verir. Devre dışı bırakmak veya bu uyarılarını gözardı seçebilirsiniz. Çözümünüzdeki tüm projeler için uyarıyı devre dışı bırakmak için açın **görünümü** > **özellik Yöneticisi**, uyarıyı devre dışı bırakın ve ardından seçili sağ istediğiniz tüm projeleri seçin öğeleri ve seçin **özellikleri**. İçinde **özellik sayfaları** iletişim altında **yapılandırma özellikleri** > **C/C++** > **Gelişmiş**, seçin **belirli uyarıları devre dışı**. Aşağı açılan oka tıklayın ve ardından **Düzenle**. 4996 metin kutusuna girin. ('C' ön eki dahil değildir.) Daha fazla bilgi için [güvenli CRT kullanılacak taşıma](porting-guide-spy-increment.md#porting_to_secure_crt).

## <a name="errors-due-to-changes-in-windows-apis-or-obsolete-sdks"></a>Windows API'leri veya eski bir SDK'ları değişiklikleri nedeniyle hataları

Yıllar içinde Windows API'leri ve veri türleri eklenir ve bazen değiştirilmiş veya kaldırıldı. Ayrıca, diğer çekirdek işletim sistemine ait olmayan SDK'ları gelen gitti ve. Eski programları, bu nedenle artık mevcut API'lere giden çağrıların içerebilir. Ayrıca, artık desteklenen diğer Microsoft SDKs API'lere giden çağrıların içeriyor olabilir. Windows API bir veya daha eski bir Microsoft SDK API içeren bir hata görürseniz, bir API kaldırıldı ve/veya daha yeni ve güvenli bir işlev tarafından değiştirilen olduğunu mümkündür.

Belirli bir Windows API'si için en düşük desteklenen işletim sistemleri ve geçerli API hakkında daha fazla bilgi için bkz. [Microsoft API ve başvuru Kataloğu](https://msdn.microsoft.com/library) ve söz konusu API gidin.

### <a name="windows-version"></a>Windows sürümü

Windows API doğrudan veya dolaylı olarak kullanan bir program yükseltirken desteklemek için en düşük Windows sürümü karar vermeniz gerekir. Çoğu durumda Windows 7 iyi bir seçimdir. Daha fazla bilgi için [üstbilgi dosya sorunlarını](porting-guide-spy-increment.md#header_file_problems). `WINVER` Makro tanımlar, programınız için tasarlanan Windows en eski sürümünü çalıştırın. MFC programınızı WINVER 0x0501 (Windows XP) için ayarlar MFC artık XP desteklediğinden derleyici XP modu sahip olsa da, bir uyarı alırsınız.

Daha fazla bilgi için [hedef Windows sürümüne güncelleştirmeden](porting-guide-spy-increment.md#updating_winver) ve [daha üst bilgi dosyaları'nı eski](porting-guide-spy-increment.md#outdated_header_files).

## <a name="atl--mfc"></a>ATL / MFC

ATL ve MFC göreceli olarak kararlı apı'lerdir ancak bazen yapılan değişiklikler. Bkz: [Visual C++ değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md) daha fazla bilgi ve [Visual c++ Visual Studio'daki yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md) ve [Visual Studio'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md).

### <a name="lnk-2005-dllmain12-already-defined-in-msvcrtdlib"></a>LNK 2005 _DllMain@12 MSVCRTD.lib içinde zaten tanımlı

MFC uygulamalarında bu hata oluşabilir. Bu, CRT kitaplık ve MFC kitaplığını arasındaki sıralama bir sorun olduğunu gösterir. MFC, böylece yeni sağlar önce bağlantılı ve delete işleçleri gerekiyor. Hatayı düzeltmek için kullanmak `/NODEFAULTLIB` bu varsayılan kitaplıkları Yoksay olarak geçin: MSVCRTD.lib and mfcs140d.lib. Daha sonra bu aynı libs ek bağımlılıkları olarak ekleyin.

## <a name="32-vs-64-bit"></a>32 ve 64 bit

32-bit sistemler için özgün kod derlenir, yerine veya yeni bir 32 bit uygulama yanı sıra 64-bit sürümünü oluşturma seçeneğiniz vardır. Genel olarak, 32 bit modunda derleme programınızı ilk alın ve sonra 64-bit denemeniz gerekir. 64 bit için derleme basittir, ancak bazı durumlarda 32-bit derlemeler tarafından gizlenmiş hataları ortaya çıkarabilir.

Ayrıca, işaretçi boyutu, zaman ve boyut değerleri ve biçim belirticileri printf veya scanf işlevindeki ilgili, derleme zamanı ve çalışma zamanı olası sorunların farkında olmalıdır. Daha fazla bilgi için [yapılandırma Visual C++ 64 bit x64 için hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md) ve [yaygın Visual C++ 64 bit geçiş sorunları](../build/common-visual-cpp-64-bit-migration-issues.md). Ek geçiş ipuçları için bkz: [64 bit Windows için Programlama Kılavuzu](/windows/desktop/WinProg64/programming-guide-for-64-bit-windows).

## <a name="unicode-vs-mbcsascii"></a>Unicode ve MBCS/ASCII

Unicode standart önce birçok program çok baytlı karakter kümesi (MBCS) ASCII karakter kümesinde yer almayan karakterlerini temsil etmek için kullanılır. Eski MFC projelerinde MBCS varsayılan ayar olan ve böyle bir program yükselttiğinizde, Unicode kullanmayı öneri uyarıları görürsünüz. Devre dışı bırakma veya Unicode dönüştürme maliyeti geliştirme olmadığını karar verirseniz, uyarıyı yok sayın tercih edebilirsiniz. Çözümünüzdeki tüm projeler için devre dışı bırakmak için açın **görünümü** > **özellik Yöneticisi**, uyarıyı devre dışı bırakmak ve ardından seçili öğeleri üzerinde sağ istediğiniz tüm projeleri seçin ve seçin **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **C/C++** > **Gelişmiş**. İçinde **belirli uyarıları devre dışı** özelliği, açılan liste okunu açın ve ardından **Düzenle**. 4996 metin kutusuna girin. ('C' ön eki dahil değildir.) Seçin **Tamam** özelliği kaydetmek için ardından **Tamam** yaptığınız değişiklikleri kaydedin.

Daha fazla bilgi için [MBCS, Unicode taşıma](porting-guide-spy-increment.md#porting_to_unicode). MBCS vs hakkında genel bilgi için. Unicode bkz [Visual C++'da metin ve dizeler](../text/text-and-strings-in-visual-cpp.md) ve [uluslararası duruma getirme](../c-runtime-library/internationalization.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual Studio'da C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)