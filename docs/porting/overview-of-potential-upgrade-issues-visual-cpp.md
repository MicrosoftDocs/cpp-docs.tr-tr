---
title: Olası yükseltme sorunlarını (Visual C++) genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 2c99a8cb-098f-4a9d-bf2c-b80fd06ace43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5cdded022a495b85570ba7f1ad86179b6210356
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848521"
---
# <a name="overview-of-potential-upgrade-issues-visual-c"></a>Olası yükseltme sorunlarını (Visual C++) genel bakış

Yıllar içinde Microsoft Visual C++ Derleyici C++ dili, C++ Standart Kitaplığı, C çalışma zamanı (CRT) ve diğer kitaplıkları MFC ve ATL gibi değişiklikler yanı sıra birçok değişikliği gerçekleştirdi Sonuç olarak, bir uygulama, Visual Studio'nun önceki bir sürümden yükseltirken, derleyici ve bağlayıcı hataları ve Uyarıları daha önce düzgün bir şekilde derlenmiş kod karşılaşabilirsiniz. Temel eski özgün kod, bu tür hatalara büyük olası. Bu genel bakışta karşılaşabileceğiniz olası sorunların en yaygın sınıfları özetler ve daha ayrıntılı bilgi için bağlantılar sağlar.

Not: Visual Studio birkaç sürümleri span yükseltmeler aynı anda gerçekleştirilen artımlı olarak bir sürüm olacağını geçmişte önerilir. Artık bu yaklaşım öneririz. Bunun hemen her zaman en güncel sürümünü Visual Studio ne kadar eski kod temeli olsun yükseltmek daha basit olduğunu fark ettik.

İçin Sorular veya yükseltme işlemi hakkında açıklamalar gönderilebilir vcupgrade@microsoft.com.

## <a name="library-and-toolset-dependencies"></a>Kitaplık ve araç takımı bağımlılıkları

Bir uygulama, Visual Studio'nun yeni bir sürüme yükseltme yaparken, kesinlikle önerilir ve çoğunda aynı zamanda tüm kitaplıkları ve uygulama bağlandığı DLL'leri yükseltmek için gereken durumlarda. Bu, kaynak kodu erişimi ya da kitaplık satıcı ile derleyici aynı ana sürümüne derlenmiş yeni ikili dosyaları sağlayabilir gerektirir. Ardından Bu koşullardan biri doğruysa ikili uyumluluğu ayrıntılarla ilgilenir bu bölümü atlayabilirsiniz. Yükseltilen uygulamanızı kitaplıklarında kullanmanız mümkün olmayabilir sonra hiçbiri bu durumda, demektir. Bu bölümdeki bilgiler, yükseltme işlemine devam olup olmadığını anlamanıza yardımcı olur.

### <a name="toolset"></a>Araç Takımı

.Obj ve .lib dosya biçimleri iyi tanımlanmış ve nadiren değiştirin. Eklemeleri bu dosya biçimleri için bazen yapılır, ancak bu eklemeleri genellikle daha yeni toolsets nesne dosyaları ve kitaplıkları eski toolsets tarafından üretilen kullanma olanağı etkilemez. Tek büyük burada kullanarak, derleme istisnası [/GL (bütün Program iyileştirmesi)](../build/reference/gl-whole-program-optimization.md). Kullanarak derleme yaparsanız **/GL**, sonuçta elde edilen nesne dosyası yalnızca onu üretmek için kullanılan araç takımı kullanarak bağlanabilir. Bunu, bir nesne dosyasıyla üretmek varsa **/GL** ve Visual Studio 2017 (v141) derleyici kullanarak, Visual Studio 2017 (v141) bağlayıcı kullanarak bağlanmanız gerekir. Nesne dosyaları iç veri yapılarını araç takımı ana sürümleri arasında tutarlı değil ve yeni toolsets eski veri biçimleri anlaşılmıyor nedeni budur.

C++ kararlı uygulama ikili arabirimi (ABI) sahip değil. Visual Studio bir yayın tüm ikincil sürümlerinin kararlı bir C++ ABI tutar. Örneğin, Visual Studio 2017 ve tüm güncelleştirmeleri ikili uyumludur. Ancak ABI önde gelen Visual Studio sürümleri arasında mutlaka uyumlu değil (2015 ve 2017, dışında _olan_ ikili uyumlu). Diğer bir deyişle, biz önemli değişiklikler C++ türü düzeni, ad düzenleme, özel durum işleme ve diğer bölümleri C++ ABI kalmasına neden olabilir. C++ bağlantı dış sembolleriyle sahip bir nesne dosyanız varsa, bu nedenle, bu nesne dosyası doğru bir araç takımı ana farklı sürümüyle üretilen nesne dosyalarla bağlamayan. Burada, "çalışmayabilir" Not sahip birçok sonuçtan: bağlantıyı tamamen başarısız olabilir (örneğin Adlandır değiştirdiyseniz), bağlantı başarılı olabilir ve şeyler çalışma zamanında çalışmayabilir (örn türü düzeni değişirse), veya olacaklar birçok durumda çalışmaya ve hiçbir şey wro gider NG. Ayrıca C++ ABI kararlı, C ABI ve C++ ABI kısmı için gerekli olmamasına karşın COM kararlı dikkat edin.

Sonraki bir sürümünü Visual Studio yeniden dağıtılabilir kitaplıkların ABI uyumluluğu korumak için içeri aktarma kitaplığı bağlantı varsa, çalışma zamanında kullanılabilir. Örneğin, uygulamanızın derlenir ve Visual Studio 2015 güncelleştirme 3'ü araç takımı kullanılarak bağlanan, 2015 ve 2017 kitaplıkları ikili geriye dönük uyumluluk korunur olmadığından yeniden dağıtılabilir, tüm Visual Studio 2017 kullanabilirsiniz. Bu durumun tersi geçerli değildir; uyumlu ABI olsa bile, kodunuzu oluşturmak için kullanılan daha yeniden dağıtılabilir Araç Takımı'nın önceki bir sürümü için kullanamazsınız.

### <a name="libraries"></a>Kitaplıklar

Visual Studio C++ kitaplıkları üstbilgi dosyaları belirli bir sürümünü kullanarak bir kaynak dosyası derleme yaparsanız (tarafından # üstbilgileri including), sonuçta elde edilen nesne dosyası kitaplıkları aynı sürümü ile bağlanması gerekir. Böylece, örneğin, kaynak dosyanızı Visual Studio 2015 güncelleştirme 3 ile derlenmiş ise \<immintrin.h >, Visual Studio 2015 güncelleştirme 3'ü vcruntime kitaplıkla bağlamanız gerekir. Benzer şekilde, kaynak dosyanızın bir Visual Studio 2017 ile sürüm 15,5 derlenir \<iostream >, Visual Studio 2017 sürüm 15,5 standart C++ kitaplığı ile msvcprt bağlamanız gerekir. Karıştırma ve eşleşen desteklenmiyor.

C++ Standart Kitaplığı için karıştırma ve eşleşen açıkça kullanımı aracılığıyla verilmedi `#pragma detect_mismatch` Visual Studio 2010 itibaren standart üst bilgileri. Uyumsuz nesne dosyaları bağlamak deneyin ya da yanlış standart kitaplığı ile bağlantı çalışırsanız, bağlantı başarısız olur

CRT karıştırma ve eşleşen hiçbir zaman destekleniyordu, ancak API yüzeyi çok zaman içinde değiştirmediğinden genellikle yalnızca, en az Visual Studio 2015 ve evrensel CRT kadar çalıştınız. Gelecekte biz geriye dönük uyumluluk sağlayabilirsiniz böylece Evrensel CRT geriye dönük uyumluluk ihlal. Diğer bir deyişle, yeni, gelecekte sürümlü Evrensel CRT ikili tanıtmak için herhangi bir plan sahip. Bunun yerine, mevcut Evrensel CRT sunulmuştur yerinde güncelleştirildi.

Nesne dosyaları (ve kitaplıklar) Microsoft C çalışma zamanı üstbilgileri eski sürümleriyle derlenmiş kısmi bağlantı uyumluluk sağlamak üzere legacy_stdio_definitions.lib, Visual Studio 2015 ve daha sonra bir kitaplık sunuyoruz. Bu kitaplık uyumluluk simgeleri Evrensel CRT kaldırıldı işlevleri ve verileri dışarı aktarma çoğunu sağlar. Tüm bağımlılıklarıyla Windows SDK'da bulunan kitaplıkları da içinde olmak üzere çoğu bağımlılıklarını karşılamak için yeterli legacy_stdio_definitions.lib tarafından sağlanan uyumluluk simgelerin kümesidir. Ancak, bu gibi uyumluluk simgeleri sağlamak mümkün değil Evrensel CRT sıradan kaldırıldığını bazı simgeleri vardır. Bu simgeleri bazı işlevler içerir (örneğin, \_ \_iob\_func) ve veri dışarı aktarma (örn., \_ \_Yönetim paketini içeri aktar\_\_\_iob, \_ \_Yönetim paketini içeri aktar\_\_\_pctype, \_ \_Yönetim paketini içeri aktar\_\_\_mb\_geçerli\_max).

C çalışma zamanı üstbilgileri daha eski bir sürümü ile oluşturulmuş bir statik kitaplık varsa, aşağıdaki eylemleri (bu sırayla) öneririz:

1. Evrensel CRT ile bağlama desteklemek için Visual Studio 2017 ve evrensel CRT üstbilgileri kullanarak statik kitaplık yeniden oluşturun. Tam olarak desteklenen (ve dolayısıyla en iyi) seçenek budur.

1. Olamaz (veya istemediğiniz) statik kitaplık yeniden, eski ile bağlama deneyebilirsiniz\_stdio\_definitions.lib. Statik kitaplığınızın bağlama zamanı bağımlılıkları uymazsa, onu ikili olumsuz herhangi biri tarafından etkilenmez olduğundan emin olmak için kullanılan statik kitaplık sınamanız isteyeceksiniz [yapılan davranış değişiklikleri Evrensel CRT](visual-cpp-change-history-2003-2015.md#BK_CRT).

1. Statik kitaplığınızın tarafından eski bağımlılıkların değil,\_stdio\_definitions.lib veya kitaplık daha önce bahsedilen davranış değişiklikleri nedeniyle Evrensel CRT ile çalışmazsa Kapsüllenen öneririz, Microsoft C çalışma zamanı doğru sürümü ile bağlantı DLL statik kitaplığa. Örneğin, statik kitaplık Visual Studio 2013 kullanılarak oluşturuldu, Visual Studio 2013 ve Visual Studio 2013 C++ kitaplıkları da kullanarak bu DLL oluşturmak istersiniz. Bir DLL'e kitaplığı oluşturarak, belirli bir Microsoft C çalışma zamanı sürümü bağımlı uygulama ayrıntı kapsüller. (DLL arabirimi hangi C çalışma zamanı, örneğin dosya * DLL sınır arasında veya malloc ayrılmış bir işaretçi döndürme ve onu boşaltmak için arayan bekleniyor döndürerek kullandığı ayrıntıları sızıntısı değil dikkatli olun istediğiniz unutmayın.)

Tek bir işlemde birden çok büyüklükteki CRT'lerden değil ve (gerçekten, birden çok CRT DLL'leri yükleme çoğu işlemleri sona erer; Örneğin, Windows işletim sistemi bileşenleri üzerinde msvcrt.dll bağlıdır ve CLR üzerinde kendi özel CRT değişir) sorunlu kendisinin kullanılır. Farklı büyüklükteki CRT'lerden durumundan jumble zaman sorunları ortaya çıkar. Örneğin, değil msvcr110.dll!malloc kullanarak bellek ve msvcr120.dll!free kullanarak bu bellek ayırması girişimi ve msvcr110 kullanarak bir dosyayı açmaya çalışmamalısınız! fopen ve değerinden okuma girişimi dosya msvcr120 kullanarak! fread. Farklı büyüklükteki CRT'lerden durumundan jumble yok sürece, tek bir işlemde yüklü birden fazla büyüklükteki CRT'lerden güvenli olabilir.

Daha fazla bilgi için bkz: [kodunuzu Evrensel CRT yükseltme](upgrade-your-code-to-the-universal-crt.md).

## <a name="errors-due-to-project-settings"></a>Proje ayarları nedeniyle hataları

Yükseltme işlemine başlamak için bir eski proje/çözüm/çalışma alanı en son Visual Studio sürümünde açın. Visual Studio, eski proje ayarlarınızı temel alan yeni bir proje oluşturur. Eski proje kitaplık sahip veya standart olmayan konumlara sabit kodlanmış yolları içeriyorsa, varsayılan ayarları proje kullandığında, bu yollar dosyalarında derleyiciye görünmeyecektir olduğunu mümkündür. Daha fazla bilgi için bkz: [bağlayıcı ÇıktıDosyası ayarı](porting-guide-spy-increment.md#linker_output_settings).

Genel olarak, proje kodunuza proje bakım basitleştirmek için düzgün şekilde düzenlemek için çok fazla zaman sunulmuştur ve olabildiğince çabuk derleme yükseltilmiş kodunuzu sağlamak. Kaynak kodunuz iyi düzenlenmiş zaten ve eski projeniz Visual Studio 2010 veya üzeri derlenmiş üzerinde hem bir eski ve yeni derleyici derleme desteklemek için yeni proje dosyası el ile düzenleyebilirsiniz. Aşağıdaki örnek, Visual Studio 2015 ve Visual Studio 2017 için derleme gösterilmektedir:

```xml
<PlatformToolset Condition="'$(VisualStudioVersion)'=='14.0'">v140</PlatformToolset>
<PlatformToolset Condition="'$(VisualStudioVersion)'=='15.0'">v141</PlatformToolset>
```

### <a name="lnk2019-unresolved-external"></a>LNK2019: Çözümlenmemiş dış

Çözümlenmemiş simgelerini proje ayarlarınızı düzeltme gerekebilir.

- Kaynak dosyanın varsayılan olmayan konumunda, projenin yolunu ekleyin vermedi ise dizinleri edilsin mi?

- Dış .lib dosyasında tanımlanmış olması durumunda, proje özelliklerinde lib yol belirttiğinizden ve gerçekte var. bulunan .lib dosyasının doğru sürümü nedir?

- Visual Studio farklı bir sürümü ile derlenen bir .lib dosyasına bağlantı sağlamak çalışıyorsunuz? Bu durumda, önceki bölümde Kitaplığı ve araç takımı bağımlılıkları bakın.

- Çağrı sitesinde bağımsız değişken türleri gerçekte işlevinin varolan bir aşırı eşleşiyor mu? İşlev imzası ve işlevi çağıran kodu hiçbir tür tanımları için temel türleri olmalarını beklediğiniz olduğundan emin olun.

Çözümlenmemiş simgesi hataları gidermek için bir binary tanımlanmış semboller incelemek için dumpbin.exe kullanmayı deneyebilirsiniz. Bir Kitaplığı'nda tanımlanan simgeleri görüntülemek üzere aşağıdaki komut satırını deneyin:

```cmd
dumpbin.exe /LINKERMEMBER somelibrary.lib
```

### <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

(Microsoft Visual C++ 6.0 ve önceki sürümlerinde, `wchar_t` yerleşik bir tür olarak uygulanmadı ancak içinde wchar.h kısa imzasız için typedef bildirildi.) C++ Standart gerektiren `wchar_t` yerleşik bir tür olmalıdır. Typedef sürümüyle taşınabilirlik sorunlara neden olabilir. Visual Studio'nun önceki sürümlerinden yükseltme ve kod örtük dönüştürmeye çalışıyor olduğundan derleyici hatası C2664 karşılaşırsanız bir `wchar_t` için `unsigned short`, ayar yerine hatayı düzeltmek için kodu değiştirmenizi öneririz **/ ZC:wchar_t-**. Daha fazla bilgi için bkz: [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

### <a name="upgrading-with-the-linker-options-nodefaultlib-entry-and-noentry"></a>Bağlayıcı seçenekleri ile /NODEFAULTLIB, / Entry ve /NOENTRY yükseltme

**/NODEFAULTLIB** bağlayıcı seçeneği (veya tüm varsayılan kitaplıkları yoksay bağlayıcı özelliği) otomatik olarak CRT gibi varsayılan kitaplıklarındaki bağlamayan için bağlayıcı söyler. Bu, her kitaplık giriş olarak ayrı ayrı listelenecek olduğu anlamına gelir. Bu kitaplıklar listesi verilir **ek bağımlılıklar** özelliğinde **bağlayıcı** bölümünü **proje özelliklerini** iletişim.

Varsayılan kitaplıklar bazıları adlarını değiştirildiğinden bu seçeneği kullanın projeleri yükseltme yaparken, bir sorun sunar. Her kitaplık yer alması gerektiğinden **ek bağımlılıklar** özelliği veya bağlayıcı komut satırında geçerli adlar kullanmak için kitaplık listesini güncelleştirmeniz gerekir.

Aşağıdaki tabloda, Visual Studio 2015 ile başlayarak, adları değiştirilen kitaplıkları gösterir. Yükseltmek için ilk sütun adları ikinci sütundaki adlarla değiştirmeniz gerekiyor. Bu kitaplıklar içeri aktarma kitaplıkları bazıları, ancak, önemli döndürmemelidir.

|||
|-|-|
|Kullanıyorsanız:|Bunların yerine gerekir:|
|Libcmt.lib|libucrt.lib, libvcruntime.lib|
|libcmtd.lib|libucrtd.lib, libvcruntimed.lib|
|msvcrt.lib|ucrt.lib, vcruntime.lib|
|msvcrtd.lib|ucrtd.lib, vcruntimed.lib|

Kullanırsanız, aynı sorunu da geçerlidir **/Entry** seçeneği veya **/NOENTRY** varsayılan kitaplık atlayarak etkisini de seçeneği.

## <a name="errors-due-to-improved-language-conformance"></a>Hataları nedeniyle iyileştirilmiş dil uyumluluğu

Microsoft Visual C++ Derleyici yıllar içinde sürekli olarak kendi uyum standart C++ için geliştirilmiştir. Önceki sürümlerinde derlenmiş kod derleyici doğru açıkça izin verilen veya önceden yoksayıldı hata bayrakları olduğundan Visual Studio 2017 derlemek başarısız olabilir.

Örneğin, **/ZC: forscope** anahtar erken MSVC geçmişinde sunulmuştur. Döngü değişkenleri için uyumsuz davranışı verir. Bu anahtar artık kullanım dışıdır ve gelecek sürümlerde kaldırılabilir. Bu geçiş kodunuzu yükseltirken kullanmayacak şekilde önerilir. Daha fazla bilgi için bkz: [/Zc:forScope-kullanım dışıdır](porting-guide-spy-increment.md#deprecated_forscope).

Const olmayan bağımsız değişken const parametresi geçirildiğinde yükseltirken görebilirsiniz ortak bir derleyici hatası için bir örnektir. Eski sürümleri derleyici, her zaman bu hata olarak bayrak. Daha fazla bilgi için bkz: [derleyicinin daha katı dönüşümleri](porting-guide-spy-increment.md#stricter_conversions).

Belirli uygunluk iyileştirmeleri hakkında daha fazla bilgi için bkz: [Visual C++ değişiklik geçmişini 2003 2015](visual-cpp-change-history-2003-2015.md) ve [C++ uygunluk Visual Studio 2017 yenilikleri](../cpp-conformance-improvements-2017.md).

## <a name="errors-involving-stdinth-integral-types"></a>Hatalar içeren \<stdint.h > tam sayı türleri

\<Stdint.h > Üstbilgi tür tanımları tanımlar ve, yerleşik tam sayı türleri aksine garanti makroları tüm platformlarda belirtilen uzunlukta olması. Bazı örnekler `uint32_t` ve `int64_t`. \<Stdint.h > başlığı, Visual Studio 2010'da eklenmiştir. 2010'dan önce yazılmış kodun, bu türleri için özel tanımları sağlanan ve bu tanımları her zaman tutarlı olmayabilir \<stdint.h > tanımlar.

Hata C2371 stdint türü söz konusu ise, bu büyük olasılıkla türü kodunuzu veya bir üçüncü taraf lib dosya üstbilgi tanımlandığı anlamına gelir. Yükseltme yaparken, tüm özel tanımları ortadan \<stdint.h > türlerini, ancak geçerli standart tanımları özel tanımları karşılaştırmak ilk, olmayan giriş yeni sorunları emin olmak için.

F12 tuşuna basabilirsiniz **Tanıma Git** söz konusu türü tanımlandığı görmek için.

[/Showıncludes](../build/reference/showincludes-list-include-files.md) derleyici seçeneği yararlı olabilir burada. İçinde **özellik sayfaları** iletişim kutusunu açın, projeniz için **C/C++** > **Gelişmiş** sayfasında ve ayarlama **Göster içeren** için **Evet**. Daha sonra projenizi yeniden derleyin ve listesini görmek # çıkış penceresinde includes. Her üstbilgisi içerdiği başlığı altında girintili olur.

## <a name="errors-involving-crt-functions"></a>CRT işlevleri ile ilgili hataları

Birden çok değişikliği için C çalışma zamanı yıllar içinde yapıldı. İşlevler birçok güvenli sürümlerini eklenir ve bazı kaldırıldı. Ayrıca, bu makalenin önceki bölümlerinde açıklandığı gibi Microsoft'un CRT uyarlamasını Visual Studio 2015'te yeni ikili dosyaları ve ilişkili .lib dosyaları bulunanad.

Bir hata CRT işlevi içeriyorsa, arama [Visual C++ değişiklik geçmişini 2003 2015](visual-cpp-change-history-2003-2015.md) veya [C++ uygunluk Visual Studio 2017 yenilikleri](../cpp-conformance-improvements-2017.md) Bu konular ek bilgileri içerip içermediğini görmek üzere. Hatası LNK2019, çözümlenmemiş dış ise işlevi kaldırılmadığından emin olun. İşlev hala var ve arama kodunun doğru olduğundan emin olup, aksi halde, projenizi kullanıp kullanmadığını denetleyin **/NODEFAULTLIB**. Öyleyse proje yeni evrensel (UCRT) kitaplıkları kullanmayacağından kitaplıkları listesi güncelleştirmeniz gerekir. Kitaplık ve bağımlılıklarını daha fazla bilgi için yukarıdaki bölümüne bakın.

Hata içeriyorsa `printf` veya `scanf`, özel olarak ya da işlevi stdio.h eklemeden tanımlıyorsanız değil olduğundan emin olun. Bu durumda, özel tanımları kaldırın veya bağlamak için eski\_stdio\_definitions.lib. Bu ayarlayabileceğiniz **özellik sayfaları** altında iletişim **yapılandırma özellikleri** > **bağlayıcı** > **giriş**, **ek bağımlılıklar** özelliği. Windows 8.1 SDK ile bağlama veya önceki bir sürümü varsa, eski eklemek\_stdio\_definitions.lib.

Hata biçim dizesi bağımsız değişkenleri gerektiriyorsa, derleyici standart zorlama hakkında daha sıkı nedeni büyük olasılıkla olmasıdır. Değişiklik geçmişini daha fazla bilgi için bkz. Olası bir güvenlik riski gösterebilir olduğundan lütfen Kapat hataları burada dikkat edin.

## <a name="errors-due-to-changes-in-the-c-standard"></a>C++ Standart değişiklikleri nedeniyle hataları

C++ Standart her zaman geriye dönük olarak uyumlu olmayan şekilde gelişmiştir. C ++ 11 taşıma semantiği, yeni anahtar sözcüklerin ve diğer dili ve standart kitaplığı özellikleri giriş, büyük olasılıkla derleyici hatalarına neden olur ve hatta farklı çalışma zamanı davranışı.

Örneğin, eski bir C++ programı iostream.h üstbilgi içerebilir. Bu üst erken C++ geçmişinde kullanımdan kaldırılmıştır ve sonunda Visual Studio'dan tamamen kaldırıldı. Bu durumda, kullanmanız gerekecektir \<iostream > ve kodunuzu yeniden yazma. Daha fazla bilgi için bkz: [eski iostreams kodunu güncelleme](porting-guide-spy-increment.md#updating_iostreams_code).

### <a name="c4838-narrowing-conversion-warning"></a>C4838: dönüştürme uyarı daraltma

Standart C++ şimdi imzalı tam sayı değerleri imzasız gelen dönüştürme daraltma dönüşümleri olarak kabul edilen belirtir. Derleyici Visual Studio 2015 öncesinde bu uyarı vermedi. Kodunuzu doğruluğunu etkileyen değil daraltma mu emin olmak için her oluşumu incelemeniz gerekir.

## <a name="warnings-to-use-secure-crt-functions"></a>Güvenli CRT işlevleri kullanmak için uyarılar

C çalışma zamanı işlevleri güvenli sürümlerini yıllar içinde tanıtılmıştır. Eski, güvenli olmayan sürümleri hala kullanılabilir olsa da, güvenli sürümlerini kullanmak üzere kodunuzu değiştirmek için önerilir. Derleyici kullanımı güvenli olmayan sürümleri için bir uyarı verecek. Devre dışı bırakın veya bu uyarılarını gözardı seçebilirsiniz. Çözümünüzdeki tüm projeleri için uyarı devre dışı bırakmak için açık **Görünüm** > **özellik Yöneticisi**, uyarıyı devre dışı bırakın ve ardından seçili sağ tıklatın istediğiniz tüm projeleri seçin öğeleri ve seçin **özellikleri**. İçinde **özellik sayfaları** altında iletişim **yapılandırma özellikleri** > **C/C++** > **Gelişmiş**, seçin **belirli uyarıları devre dışı**. Aşağı açılan oku tıklatın ve ardından tıklatın **Düzenle**. 4996 metin kutusuna girin. ('C' öneki eklemeyin.) Daha fazla bilgi için bkz: [güvenli CRT kullanmak için taşıma](porting-guide-spy-increment.md#porting_to_secure_crt).

## <a name="errors-due-to-changes-in-windows-apis-or-obsolete-sdks"></a>Windows API'ları veya eski SDK'ları değişiklikleri nedeniyle hataları

Yıllar içinde Windows API'ları ve veri türleri eklenir ve bazen değiştirilmiş veya kaldırılmış. Ayrıca, diğer çekirdek işletim sistemine ait değil SDK'ları gelen gitti ve sahip. Eski programları, bu nedenle artık mevcut API çağrıları içerebilir. Bunlar, artık desteklenmeyen diğer Microsoft SDKs API'leri çağrıları içerebilir. Bir Windows API'si veya eski bir Microsoft SDK API'den içeren bir hata görürseniz, bir API kaldırıldı ve/veya daha yeni, daha güvenli bir işlev tarafından değiştirilen olduğunu mümkündür.

Geçerli API'si hakkında daha fazla bilgi ve belirli bir Windows API'si için en düşük desteklenen işletim sistemleri için bkz: [Microsoft API ve başvuru katalog](https://msdn.microsoft.com/library) ve söz konusu API gidin.

### <a name="windows-version"></a>Windows sürümü

Doğrudan veya dolaylı olarak Windows API'si kullanan bir programı yükseltirken desteklemek için en düşük Windows sürümü karar vermeniz gerekir. Çoğu durumda Windows 7 iyi bir seçimdir. Daha fazla bilgi için bkz: [üstbilgi dosyası sorunlarını](porting-guide-spy-increment.md#header_file_problems). Eski Windows sürümü ile programınız için tasarlanmış WINVER makrosu tanımlar üzerinde çalışır. MFC programınızı WINVER 0x0501'i için (Windows XP) ayarlar MFC artık XP desteklediğinden derleyici XP modu sahip olsa da, bir uyarı alırsınız.  

Daha fazla bilgi için bkz: [hedef Windows sürümü güncelleştirme](porting-guide-spy-increment.md#updating_winver) ve [üst bilgi dosyaları'daha eski](porting-guide-spy-increment.md#outdated_header_files).

## <a name="atl--mfc"></a>ATL / MFC

ATL ve MFC görece kararlı apı'leridir ancak bazen yapılan değişiklikler. Bkz: [Visual C++ değişiklik geçmişini 2003 2015](visual-cpp-change-history-2003-2015.md) daha fazla bilgi için ve [de Visual Studio 2017'de Visual C++ yenilikleri](../what-s-new-for-visual-cpp-in-visual-studio.md) ve [C++ uygunluk Visual Studio 2017yenilikleri](../cpp-conformance-improvements-2017.md).

### <a name="lnk-2005-dllmain12-already-defined-in-msvcrtdlib"></a>LNK 2005 _DllMain@12 MSVCRTD.lib içinde zaten tanımlandı

MFC uygulamalarında bu hata oluşabilir. CRT kitaplık ve MFC kitaplık arasında sıralama bir sorunu gösterir. MFC, böylece yeni sağlar ilk bağlanması ve delete işleçleri gerekiyor. Hatayı düzeltmek için bu varsayılan kitaplıkları yoksay için /NODEFAULTLIB anahtarı kullanın: MSVCRTD.lib ve mfcs140d.lib. Daha sonra bu aynı kitaplıklar ek bağımlılıklar olarak ekleyin.

## <a name="32-vs-64-bit"></a>32 vs 64 bit

32 bit sistemler için özgün kodunuzu derlenmiş, yerine veya yeni bir 32 bit uygulama yanı sıra 64-bit sürümünü oluşturma seçeneğiniz vardır. Genel olarak, 32-bit modunda derleme programınızı ilk ulaşmak ve 64-bit denemesi gerekir. 64 bit için derleme basittir, ancak bazı durumlarda 32-bit derlemeleri tarafından gizlenmiş hatalar ortaya çıkarabilir.

Ayrıca, işaretçi boyutu, saati ve boyutu değerleri ve printf ve scanf işlevleri içindeki Biçim belirticileri ilgili olası derleme zamanı ve çalışma zamanı sorunları haberdar olmanız gerekir. Daha fazla bilgi için bkz: [yapılandırma Visual C++ 64-bit, x64 için hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md) ve [ortak Visual C++ 64 bit geçiş sorunları](../build/common-visual-cpp-64-bit-migration-issues.md). Ek geçiş ipuçları için bkz: [64-bit Windows için Programlama Kılavuzu](https://msdn.microsoft.com/library/windows/desktop/bb427430\(v=vs.85\).aspx).

## <a name="unicode-vs-mbcsascii"></a>Unicode vs MBCS/ASCII

Unicode standartlaştırılmış önce birçok program çok baytlı karakter kümesi (MBCS) ASCII karakter kümesinde dahil edilmeyen karakter göstermek için kullanılır. Eski MFC projelerinde MBCS varsayılan ayar olan ve böyle bir program yükselttiğinizde, Unicode kullanmayı öneri uyarılar görürsünüz. Devre dışı bırakmak veya Unicode dönüştürme maliyet geliştirme olmadığını karar verirseniz uyarıyı yok sayın tercih edebilirsiniz. Çözümünüzdeki tüm projeleri için devre dışı bırakmak açmak **Görünüm** > **özellik Yöneticisi**, uyarıyı devre dışı bırak, ardından seçili öğelerde sağ istediğiniz tüm projeleri seçin ve seçin **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **C/C++** > **Gelişmiş**. İçinde **belirli uyarıları devre dışı** özelliği, aşağı açılan okunu açın ve ardından **Düzenle**. 4996 metin kutusuna girin. ('C' öneki eklemeyin.) Seçin **Tamam** özelliği kaydetmek için ardından **Tamam** yaptığınız değişiklikleri kaydetmek için.

Daha fazla bilgi için bkz: [Unicode'a MBCS bağlantı noktası oluşturma](porting-guide-spy-increment.md#porting_to_unicode). MBCS vs hakkında genel bilgi için. Unicode bkz [metin ve dizeler Visual C++'ta](../text/text-and-strings-in-visual-cpp.md) ve [uluslararası hale getirme](../c-runtime-library/internationalization.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Önceki Visual C++ Sürümü Projelerini Yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Visual Studio 2017’deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements-2017.md)  
