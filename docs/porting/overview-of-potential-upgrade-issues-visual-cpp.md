---
title: Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)
ms.date: 05/03/2019
ms.assetid: 2c99a8cb-098f-4a9d-bf2c-b80fd06ace43
ms.openlocfilehash: ef088f4881dfbd9967f90a009e4a8e397a70b134
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214987"
---
# <a name="overview-of-potential-upgrade-issues-visual-c"></a>Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)

Yıl boyunca, Microsoft C++ derleyicisi, C++ dilin kendisindeki değişikliklerle birlikte, C++ standart KITAPLıK, C çalışma zamanı (CRT) ve MFC ve ATL gibi diğer kitaplıklarda çok sayıda değişiklik yapılmıştır. Sonuç olarak, bir uygulamayı Visual Studio 'nun önceki bir sürümünden yükseltirken, derleyici ve bağlayıcı hatalarıyla ve daha önce düzgün şekilde derlenen koddaki uyarılarla karşılaşabilirsiniz. Eski kod tabanı, bu tür hataların potansiyeli artar. Bu genel bakışta, büyük ihtimalle karşılaştığınız sorunların en yaygın sınıflarını özetler ve daha ayrıntılı bilgi için bağlantılar sağlanmaktadır.

> [!NOTE]
> Geçmişte, Visual Studio 'nun birden çok sürümünü yayan yükseltmelerin aynı anda bir sürümü bir kez gerçekleştirmelerini öneririz. Bu yaklaşımı artık önermiyoruz. Kod tabanının ne kadar eski olduğuna bakılmaksızın, Visual Studio 'nun en güncel sürümüne yükseltmek için neredeyse her zaman daha kolay olduğunu belirledik.

Yükseltme işlemiyle ilgili sorular veya açıklamalar vcupgrade@microsoft.comgönderilebilir.

## <a name="library-and-toolset-dependencies"></a>Kitaplık ve araç kümesi bağımlılıkları

> [!NOTE]
> Bu bölüm, Visual Studio 2013 ve öncesiyle oluşturulan uygulamalar ve kitaplıklar için geçerlidir. Visual Studio 2015 ' de kullanılan araç kümeleri, Visual Studio 2017 ve Visual Studio 2019 ikili uyumludur. Daha fazla bilgi için bkz [ C++ . Visual Studio 2015 ve Visual Studio 2019 arasında ikili uyumluluk](binary-compat-2015-2017.md).

Bir uygulamayı Visual Studio 'nun yeni bir sürümüne yükseltirken, her ikisi de önerilir ve uygulamanın bağlandığı tüm kitaplıkları ve DLL 'Leri de yükseltmeniz gerekir. Kaynak koda erişiminizin olmasını veya kitaplık satıcısının derleyicinin aynı ana sürümüyle derlenen yeni ikili dosyalar sağlayabilmeniz gerekir. Bu koşullardan biri doğru ise, ikili uyumluluğun ayrıntılarıyla ilgilenen bu bölümü atlayabilirsiniz. Böyle bir durum söz konusu değilse, yükseltilen uygulamanızdaki kitaplıkları kullanmeyebilirsiniz. Bu bölümdeki bilgiler, yükseltmeye devam edip edemeyeceğinizi anlamanıza yardımcı olur.

### <a name="toolset"></a>Araç Takımı

. Obj ve. lib dosya biçimleri iyi tanımlanmış ve nadiren değiştirilebilir. Bazı durumlarda bu dosya biçimlerinde eklemeler yapılır, ancak bu eklemeler genellikle daha yeni araç kümelerinin, daha eski araç kümeleri tarafından üretilen nesne dosyalarını ve kitaplıklarını tüketme yeteneğini etkilemez. Buradaki önemli özel durum/GL kullanarak derlerseniz [(tüm program iyileştirmesi)](../build/reference/gl-whole-program-optimization.md). `/GL`kullanarak derlerseniz, elde edilen nesne dosyası yalnızca onu oluşturmak için kullanılan araç kümesiyle bağlantılı olabilir. Bu nedenle, `/GL` ile bir nesne dosyası üretemiyor ve Visual Studio 2017 (v141) derleyicisini kullanıyorsanız, Visual Studio 2017 (v141) bağlayıcı kullanarak bağlamanız gerekir. Bunun nedeni, nesne dosyalarındaki iç veri yapılarının araç takımının ana sürümleri arasında kararlı olmaması ve daha yeni araç kümelerinin eski veri biçimlerini anlamamalarıdır.

C++kararlı bir uygulama ikili arabirimine (ABı) sahip değildir. Ancak Visual Studio, bir sürümün C++ tüm küçük sürümleri için kararlı bir ABI tutar. Visual Studio 2015 (v140), Visual Studio 2017 (v141) ve Visual Studio 2019 (v142) yalnızca küçük sürümlerinde farklılık gösterir. Hepsi, 14 olan aynı ana sürüm numarasına sahiptir. Daha fazla bilgi için bkz [ C++ . Visual Studio 2015 ve Visual Studio 2019 arasında ikili uyumluluk](binary-compat-2015-2017.md).

Bağlantısı olan C++ dış sembolleri olan bir nesne dosyanız varsa, bu nesne dosyası araç takımının farklı bir ana sürümü tarafından oluşturulan nesne dosyalarıyla doğru şekilde bağlantı olmayabilir. Birçok olası sonuç vardır: bağlantı tamamen başarısız olabilir (örneğin, ad dekorasyonu değiştirilirse). Bağlantı başarılı olabilir ve işlemler çalışma zamanında çalışmayabilir (örneğin, tür düzeni değiştirilirse). Ya da pek çok durumda, şeyler işe başlayabilir ve hiçbir şey yanlış olmayacaktır. Ayrıca, C++ ABI kararlı olmasa da, com için gerekli olan C ABI ve C++ ABI alt kümesinin kararlı olduğunu da göz önünde bulabilirsiniz.

İçeri aktarma kitaplığına bağlantı verirseniz, ABı uyumluluğunu koruyan Visual Studio Redistributable kitaplıklarının daha sonraki bir sürümü çalışma zamanında kullanılabilir. Örneğin, uygulamanız Visual Studio 2015 güncelleştirme 3 araç takımı kullanılarak derlenip bağlanmışsa, 2015, 2017 ve 2019 kitaplıkları geriye doğru ikili uyumluluğu korunduğu için herhangi bir Visual Studio 2017 veya Visual Studio 2019 Redistributable kullanabilirsiniz. Tersi doğru değildir: uyumlu bir ABı sahip olsalar bile, bir araç takımının kodunuzu oluşturmak için kullandığınız önceki bir sürümü için yeniden dağıtılabilir kullanamazsınız.

### <a name="libraries"></a>Kitaplıklar

Visual Studio C++ kitaplıkları üstbilgi dosyalarının belirli bir sürümünü kullanarak bir kaynak dosya derlerseniz (üst bilgileri #including), sonuçta elde edilen nesne dosyası kütüphanelerin aynı sürümüyle bağlantılı olmalıdır. Bu nedenle, örneğin, kaynak dosyanız Visual Studio 2015 güncelleştirme 3 \<ımintrin. h > ile derlenmişse, Visual Studio 2015 güncelleştirme 3 vcruntime kitaplığı ile bağlantı oluşturmanız gerekir. Benzer şekilde, kaynak dosyanız Visual Studio 2017 sürüm 15,5 \<iostream > ile derlenmişse, Visual Studio 2017 sürüm 15,5 standart C++ kitaplığı, MSVCPRT ile bağlantı oluşturmanız gerekir. Karıştırma ve eşleştirme desteklenmez.

C++ Standart kitaplık Için, Visual Studio 2010 ' den beri standart başlıklarındaki `#pragma detect_mismatch` kullanılarak karıştırma ve eşleştirmeye açıkça izin verilmez. Uyumsuz nesne dosyalarını bağlamayı denerseniz veya yanlış standart kitaplıkla bağlantı yapmayı denerseniz bağlantı başarısız olur.

CRT için, karışık ve eşleme hiç desteklenmedi, ancak API yüzeyi zaman içinde çok fazla değişmediği için, en azından yalnızca Visual Studio 2015 ve Universal CRT kadar az çalıştık. Evrensel CRT, daha sonra geriye dönük uyumluluğu koruyabilmemiz için geriye dönük uyumlulukla uyum sağlayabilir. Diğer bir deyişle, gelecekte yeni, sürümlü Evrensel CRT ikilileri tanıtmak için planımız yok. Bunun yerine, mevcut Evrensel CRT artık yerinde güncelleştirilir.

Microsoft C çalışma zamanı üst bilgilerinin daha eski sürümleriyle derlenen nesne dosyalarıyla (ve kitaplıklarıyla) kısmi bağlantı uyumluluğu sağlamak için Visual Studio 2015 ve üzeri bir kitaplık, legacy_stdio_definitions. lib sağlıyoruz. Bu kitaplık, Evrensel CRT 'den kaldırılan işlevlerin ve veri dışa aktarımlarının çoğu için uyumluluk sembolleri sağlar. Legacy_stdio_definitions. lib tarafından sağlanan uyumluluk sembolleri kümesi, Windows SDK dahil olan kitaplıklardaki tüm bağımlılıklar dahil olmak üzere çoğu bağımlılığı karşılamak için yeterlidir. Ancak, Evrensel CRT 'den kaldırılan ve uyumluluk sembolleri sağlamak mümkün olmayan bazı semboller vardır. Bu semboller bazı işlevleri içerir (örneğin, \_\_iob\_Func) ve veri dışa aktarır (örneğin, \_\_imp\_\_\_iob, \_\_imp\_\_\_pctype, \_\_imp\_\_\_MB\_CUR\_max).

C çalışma zamanı üst bilgilerinin daha eski bir sürümüyle oluşturulmuş bir statik kitaplığınız varsa, şu sırayla aşağıdaki eylemleri yapmanızı öneririz:

1. Evrensel CRT ile bağlamayı desteklemek için, Visual Studio 'nun yeni sürümünü ve Evrensel CRT üst bilgilerini kullanarak statik kitaplığı yeniden derleyin. Bu yaklaşım, tam olarak desteklenen (ve bu nedenle en iyi) seçenektir.

1. Statik kitaplığı yeniden derlemek için (veya istemiyorsanız), eski\_stdio\_Definitions. lib ile bağlamayı deneyebilirsiniz. Statik kitaplığınızın bağlantı süresi bağımlılıklarını karşılıyorsa, [Evrensel CRT üzerinde yapılan herhangi bir davranış değişikliklerinden](visual-cpp-change-history-2003-2015.md#BK_CRT)olumsuz etkilenmediğinden emin olmak için statik kitaplığı ikili dosyada kullanıldığı gibi kapsamlı bir şekilde test etmek isteyeceksiniz.

1. Statik kitaplığınızın bağımlılıkları eski\_stdio\_Definitions. lib tarafından karşılanmazsa veya kitaplık Evrensel CRT ile birlikte çalışmazsa, belirtilen davranış değişiklikleri nedeniyle, statik kitaplığınızı Microsoft C çalışma zamanının doğru sürümü ile bağlantılandırdığınızda bir DLL 'ye kapsülletireceğiz. Örneğin, statik kitaplık Visual Studio 2013 kullanılarak oluşturulduysa, Visual Studio 2013 ve Visual Studio 2013 C++ kitaplıklarını kullanarak bu DLL 'yi de oluşturmak istersiniz. Kitaplığı bir DLL dosyasına oluşturarak, Microsoft C çalışma zamanının belirli bir sürümüne bağımlılığı olan uygulama ayrıntılarını yalıtır. DLL arabirimine hangi C çalışma zamanının kullandığı, örneğin DLL sınırında bir dosya döndürerek veya malloc ile ayrılmış bir işaretçi döndürerek ve çağıranın onu serbest bırakmasını gerektirdiğinden emin olmak isteyeceksiniz.

Tek bir işlemde birden çok CRI 'nin kullanımı kendi sorunlu değildir (Aslında, çoğu işlem birden çok CRT DLL 'yi yükler; Örneğin, Windows işletim sistemi bileşenleri Msvcrt. dll ' ye bağlıdır ve CLR kendi özel CRT 'sine bağlıdır). Farklı CRTs 'lerden küçük bir durum olduğunda sorunlar oluşur. Örneğin, Msvcr110. dll! malloc kullanarak bellek ayırmamalıdır ve Msvcr120. dll! ' yi kullanarak bu belleği serbest bırakma girişimi yapmanız gerekir ve Msvcr110! fopen kullanarak bir dosyayı açmaya çalışmamalısınız ve Msvcr120! fread kullanarak bu dosyadan okumaya çalışmazsınız. Farklı CRTs 'lerden önemli bir durum olmadığı sürece, tek bir işlemde birden çok CRTs yüklenmiş olabilir.

Daha fazla bilgi için bkz. [kodunuzu Evrensel CRT 'ye yükseltme](upgrade-your-code-to-the-universal-crt.md).

## <a name="errors-due-to-project-settings"></a>Proje ayarlarından kaynaklanan hatalar

Yükseltme işlemini başlatmak için, Visual Studio 'nun en son sürümünde eski bir projeyi/çözümü/çalışma alanını açın. Visual Studio, eski proje ayarlarına bağlı olarak yeni bir proje oluşturur. Eski projenin kitaplığı varsa veya standart olmayan konumlara sabit kodlanmış yollar içeriyorsa, proje varsayılan ayarları kullandığında, bu yollardaki dosyalar derleyiciye görünmez hale gelir. Daha fazla bilgi için bkz. [bağlayıcı ÇıktıDosyası ayarı](porting-guide-spy-increment.md#linker_output_settings).

Genel olarak, proje bakımını basitleştirmek ve yükseltilen kod derlemelerinizi mümkün olduğunca hızlı bir şekilde almak için proje kodunuzu doğru bir şekilde düzenlemek için harika bir zaman vardır. Kaynak kodunuz zaten iyi düzenlenmişse ve eski projeniz Visual Studio 2010 veya sonraki bir sürümü ile derlenmişse, hem eski hem de yeni derleyicide derlemeyi desteklemek için yeni proje dosyasını el ile düzenleyebilirsiniz. Aşağıdaki örnekte, Visual Studio 2015 ve Visual Studio 2017 için nasıl derleme yapılacağı gösterilmektedir:

```xml
<PlatformToolset Condition="'$(VisualStudioVersion)'=='14.0'">v140</PlatformToolset>
<PlatformToolset Condition="'$(VisualStudioVersion)'=='15.0'">v141</PlatformToolset>
```

### <a name="lnk2019-unresolved-external"></a>LNK2019: çözülmemiş dış

Çözümlenmemiş semboller için, proje ayarlarınızı çözmeniz gerekebilir.

- Kaynak dosya varsayılan olmayan bir konumdaysa, yolu projenin dahil olduğu dizine ekleyin mi?

- External bir. lib dosyasında tanımlanmışsa, proje özelliklerinde LIB yolunu belirtsin ve. lib dosyasının doğru sürümü var mı?

- Farklı bir Visual Studio sürümü ile derlenen bir. lib dosyasına bağlantı kurmaya çalışıyor musunuz? Bu durumda, kitaplık ve araç kümesi bağımlılıklarındaki önceki bölüme bakın.

- Çağrı sitesindeki bağımsız değişkenlerin türleri, işlevin var olan aşırı yüklemesiyle eşleşiyor mu? İşlevin imzasında ve işlev çağıran kodda, işlevleri çağıran kodda herhangi bir tür tanımları için temeldeki türleri doğrulayın.

Çözümlenmemiş sembol hatalarını gidermek için, bir ikili dosyada tanımlanan sembolleri incelemek üzere dumpbin. exe ' yi kullanmayı deneyebilirsiniz. Kitaplıkta tanımlanan sembolleri görüntülemek için aşağıdaki komut satırını deneyin:

```cmd
dumpbin.exe /LINKERMEMBER somelibrary.lib
```

### <a name="zcwchar_t-wchar_t-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

(Microsoft Visual C++ 6,0 ve önceki sürümlerde **wchar_t** yerleşik bir tür olarak uygulanmadı, ancak wchar. h 'de işaretsiz Short için typedef olarak bildirildi.) Standart C++ , **wchar_t** yerleşik bir tür olmasını gerektirir. TypeDef sürümünün kullanılması taşınabilirlik sorunlarına neden olabilir. Visual Studio 'nun önceki sürümlerinden yükseltme yaparsanız ve kod bir **wchar_t** örtük olarak **işaretsiz bir Short**'a dönüştürmeye çalıştığı için derleyici hatası C2664 ile karşılaşırsanız, bu kodu, `/Zc:wchar_t-`ayarlamak yerine hatayı giderecek şekilde değiştirmenizi öneririz. Daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

### <a name="upgrading-with-the-linker-options-nodefaultlib-entry-and-noentry"></a>Bağlayıcı seçenekleri/NODEFAULTLIB,/ENTRY ve/NOENTRY ile yükseltiliyor

`/NODEFAULTLIB` bağlayıcı seçeneği (veya tüm varsayılan kitaplıkları Yoksay bağlayıcı özelliği), bağlayıcının CRT gibi varsayılan kitaplıklarda otomatik olarak bağlantı oluşturmasını söyler. Her kitaplığın tek tek giriş olarak listelenmesi gerektiği anlamına gelir. Bu kitaplıkların listesi, **Proje özellikleri** Iletişim kutusunun **bağlayıcı** bölümündeki **ek bağımlılıklar** özelliğinde verilmiştir.

Bu seçeneği kullanan projeler, bazı varsayılan kitaplıkların içerikleri yeniden düzenlenmiş olduğundan, yükseltme sırasında bir sorun sunar. Her kitaplığın **ek bağımlılıklar** özelliğinde veya bağlayıcı komut satırında listelenmesi gerektiğinden, kitaplıkların listesini tüm geçerli adları kullanacak şekilde güncelleştirmeniz gerekir.

Aşağıdaki tabloda, içeriği Visual Studio 2015 ile başlayarak değiştirilen kitaplıklar gösterilmektedir. Yükseltmek için, ikinci sütundaki yeni kitaplık adlarını ilk sütundaki kitaplıklara eklemeniz gerekir. Bu kitaplıkların bazıları içeri aktarma kitaplıklarıdır, ancak böyle bir önemi yoktur.

|||
|-|-|
|Şunu kullanıyorsanız:|Şu kitaplıkları kullanmanız gerekir:|
|Libcmt. lib|Libcmt. lib, libucrt. lib, libvcruntime. lib|
|libcmtd.lib|libcmtd. lib, libucrtd. lib, libvcruntimed. lib|
|msvcrt.lib|Msvcrt. lib, UCRT. lib, vcruntime. lib|
|msvcrtd.lib|msvcrtd. lib, ucrtd. lib, vcrunzamanlandı. lib|

Ayrıca, varsayılan kitaplıkları atlama etkisi olan `/ENTRY` seçeneğini veya `/NOENTRY` seçeneğini kullanırsanız aynı sorun da geçerlidir.

## <a name="errors-due-to-improved-language-conformance"></a>Geliştirilmiş dil uyumluluğu nedeniyle hatalar oluştu

Microsoft C++ derleyicisi, yıl boyunca C++ standart uyumluluk uyumluluğunu sürekli olarak iyileştirdi. Önceki sürümlerde derlenen kod, derleyici daha önce yoksayılan veya açıkça izin verilen bir hatayı doğru bir şekilde ayarlayacağından Visual Studio 'nun sonraki sürümlerinde derlenemeyebilir.

Örneğin, `/Zc:forScope` anahtarı, MSVC geçmişinde erken kullanıma sunulmuştur. Döngü değişkenleri için uyumlu olmayan davranışa izin verir. Bu anahtar artık kullanım dışıdır ve gelecek sürümlerde kaldırılabilir. Kodunuzu yükseltirken bu anahtarın kullanılması kesinlikle önerilir. Daha fazla bilgi için bkz. [/Zc: forScope-kullanım dışıdır](porting-guide-spy-increment.md#deprecated_forscope).

Bir const parametreye const olmayan bir bağımsız değişken geçirildiğinde görebileceğiniz yaygın bir derleyici hatası örneği. Derleyicinin eski sürümleri her zaman bir hata olarak bayrak almadı. Daha fazla bilgi için [derleyicinin daha katı dönüştürmelerine](porting-guide-spy-increment.md#stricter_conversions)bakın.

Belirli uygunluk geliştirmeleri hakkında daha fazla bilgi için bkz. Visual Studio 'da [ C++ görsel değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md) ve [ C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md).

## <a name="errors-involving-stdinth-integral-types"></a>\<stdint. h > integral türlerini içeren hatalar

\<stdint. h > üst bilgisi, yerleşik integral türlerin aksine, tüm platformlarda belirli bir uzunluğa sahip olduğu garanti edilen tür tanımları ve makroları tanımlar. Bazı örnekler `uint32_t` ve `int64_t`. \<stdınt. h > üst bilgisi Visual Studio 2010 ' ye eklenmiştir. 2010 'den önce yazılan kod bu türler için özel tanımlar sağlamış olabilir ve bu tanımlar \<stdınt. h > tanımlarına göre her zaman tutarlı olmayabilir.

Hata C2371 ve `stdint` bir tür varsa, büyük olasılıkla tür kodunuzda veya üçüncü taraf lib dosyasında tanımlanan bir başlıkta tanımlanmıştır. ' Yi yükseltirken, \<stdint. h > türlerinin özel tanımlarını ortadan kaldırmanız gerekir, ancak ilk olarak özel tanımları geçerli standart tanımlarla karşılaştırarak yeni sorunlarla karşılaştığınızdan emin olun.

Söz konusu türün nerede tanımlandığını görmek için **F12** tuşuna (**Tanıma Git**) basabilirsiniz.

[/ShowIncludes](../build/reference/showincludes-list-include-files.md) derleyici seçeneği burada yararlı olabilir. Projeniz için **Özellik sayfaları** iletişim kutusunda, **C++ C/**  > **Gelişmiş** sayfasını açın ve **eklemeleri göster** ' i **Evet**olarak ayarlayın. Ardından projenizi yeniden derleyin ve çıkış penceresinde `#include`s listesini görüntüleyin. Her üst bilgi, onu içeren üst bilgi altında girintilenir.

## <a name="errors-involving-crt-functions"></a>CRT işlevleriyle ilgili hatalar

C çalışma zamanında yıllarda çok sayıda değişiklik yapılmıştır. İşlevlerin birçok güvenli sürümü eklenmiştir ve bazıları kaldırılmıştır. Ayrıca, bu makalenin önceki kısımlarında açıklandığı gibi, Microsoft 'un CRT 'nin uygulanması, Visual Studio 2015 ' de yeni ikili dosyalar ve ilişkili. lib dosyaları yeniden düzenlenmiş.

Bir hata CRT işlevi içeriyorsa, bu makalelerin ek bilgiler içerdiğini görmek için [görsel C++ değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md) ' i veya [ C++ Visual Studio 'daki uygunluk geliştirmelerini](../overview/cpp-conformance-improvements.md) arayın. Hata LNK2019 ise, çözümlenmemiş dış ise işlevin kaldırılmadığından emin olun. Aksi takdirde, işlevin hala mevcut olduğundan eminseniz ve çağıran kod doğru olduğundan, projenizin `/NODEFAULTLIB`kullanıp kullanmadığını kontrol edin. Bu durumda, projenin yeni Evrensel (UCRT) kitaplıklarını kullanması için kitaplıkların listesini güncelleştirmeniz gerekir. Daha fazla bilgi için kitaplık ve bağımlılıklarda yukarıdaki bölüme bakın.

Hata `printf` veya `scanf`içeriyorsa, stdio. h dahil olmak üzere herhangi bir işlevi özel olarak tanımlamadığınızdan emin olun. Varsa, özel tanımları kaldırın veya eski\_stdio\_Definitions. lib bağlantısını kaldırın. Bu **kitaplığı,** **ek bağımlılıklar** özelliğindeki > **bağlayıcı** > **yapılandırma özellikleri** altındaki **Özellik sayfaları** iletişim kutusunda ayarlayabilirsiniz. Windows SDK 8,1 veya önceki bir sürümü ile bağlanıyorsanız eski\_stdio\_Definitions. lib ekleyin.

Hata, biçim dizesi bağımsız değişkenlerini içeriyorsa, büyük olasılıkla derleyicinin standart zorlama konusunda daha sıkı olmasından kaynaklanır. Daha fazla bilgi için bkz. değişiklik geçmişi. Bir güvenlik riskini potansiyel olarak temsil ettiğinden, buradaki hatalara yakın bir şekilde dikkat edin.

## <a name="errors-due-to-changes-in-the-c-standard"></a>C++ Standart değişikliklerden kaynaklanan hatalar

Standart C++ , her zaman geriye dönük olarak uyumlu olmayan yollarla gelişmiştir. C++ 11 ' in taşıma semantiklerine, yeni anahtar sözcüklere ve diğer dil ve standart kitaplık özelliklerine giriş, büyük olasılıkla derleyici hatalarına ve hatta farklı çalışma zamanı davranışına neden olabilir.

Örneğin, eski C++ bir program iostream. h üst bilgisini içerebilir. Bu üst bilgi, geçmişinden erken kullanımdan kaldırılmıştır C++ ve sonunda Visual Studio 'dan tamamen kaldırılmıştır. Bu durumda, \<iostream > kullanmanız ve kodunuzu yeniden yazmanız gerekir. Daha fazla bilgi için bkz. [eski Iostreams kodunu güncelleştirme](porting-guide-spy-increment.md#updating_iostreams_code).

### <a name="c4838-narrowing-conversion-warning"></a>C4838: daraltma dönüştürme uyarısı

Standart C++ Şu anda işaretsiz ve işaretli integral değerleri için dönüştürmelerin daraltma dönüştürmesi olarak kabul edileceğini belirtir. Derleyici, Visual Studio 2015 ' dan önce bu uyarıyı yükseltmedi. Daraltmaya ait kodunuzun doğruluğunu etkilemediğinden emin olmak için her bir oluşumu inceleyin.

## <a name="warnings-to-use-secure-crt-functions"></a>Güvenli CRT işlevlerini kullanma uyarıları

Yıllarca, C çalışma zamanı işlevlerinin güvenli sürümleri sunulmuştur. Eski, güvenli olmayan sürümler hala kullanılabilir olsa da, kodunuzun güvenli sürümlerini kullanmak için değiştirilmesi önerilir. Derleyici, güvenli olmayan sürümlerin kullanımı için bir uyarı verecek. Bu uyarıları devre dışı bırakmayı veya yoksaymayı seçebilirsiniz. Çözümünüzdeki tüm projelere yönelik uyarıyı devre dışı bırakmak için, **görünüm** > **Özellik Yöneticisi**açın, uyarıyı devre dışı bırakmak istediğiniz tüm projeler ' i seçin, ardından seçili öğelere sağ tıklayıp **Özellikler**' i seçin. **Yapılandırma özellikleri** altındaki **Özellik sayfaları** iletişim kutusunda, **C++ C/**  > **Gelişmiş** > , **belirli uyarıları devre dışı bırak**' ı seçin. Açılan oka tıklayın ve ardından **Düzenle**' ye tıklayın. Metin kutusuna 4996 girin. (' C ' önekini eklemeyin.) Daha fazla bilgi için bkz. [GÜVENLI CRT 'yi kullanmak Için taşıma](porting-guide-spy-increment.md#porting_to_secure_crt).

## <a name="errors-due-to-changes-in-windows-apis-or-obsolete-sdks"></a>Windows API 'Lerinde veya eski SDK 'larda yapılan değişikliklerden kaynaklanan hatalar

Yıl boyunca, Windows API 'Leri ve veri türleri eklenmiştir ve bazen değişir ya da kaldırılır. Ayrıca, çekirdek işletim sistemine ait olmayan diğer SDK 'lar da gelir ve kayboldu. Bu nedenle, daha eski programlar artık varolmayan API 'lere çağrılar içerebilir. Ayrıca, artık desteklenmeyen diğer Microsoft SDK 'Lerinde API 'lere çağrılar de içerebilir. Eski bir Microsoft SDK 'dan bir Windows API 'sini veya API 'yi içeren bir hata görürseniz, bir API 'nin kaldırılması ve/veya yerini daha yeni, daha güvenli bir işlev ile yerine getirmek mümkündür.

Geçerli API kümesi ve belirli bir Windows API 'SI için desteklenen en düşük işletim sistemleri hakkında daha fazla bilgi için bkz. [MICROSOFT API ve başvuru kataloğu](https://msdn.microsoft.com/library) ve söz konusu API 'ye gitme.

### <a name="windows-version"></a>Windows sürümü

Windows API kullanan bir programı doğrudan veya dolaylı olarak yükseltirken, desteklemek için en düşük Windows sürümüne karar vermeniz gerekir. Çoğu durumda, Windows 7 iyi bir seçimdir. Daha fazla bilgi için bkz. [üstbilgi dosyası sorunları](porting-guide-spy-increment.md#header_file_problems). `WINVER` makrosu, programınızın üzerinde çalışmak üzere tasarlandığı en eski Windows sürümünü tanımlar. MFC programınız WINVER 'yi 0x0501 olmalı (Windows XP) olarak ayarlamışsa, derleyicinin kendisi bir XP moduna sahip olsa bile, MFC artık XP 'yi desteklemediği için bir uyarı alırsınız.

Daha fazla bilgi için bkz. [hedef Windows sürümü](porting-guide-spy-increment.md#updating_winver) ve [daha güncel olmayan üstbilgi dosyaları](porting-guide-spy-increment.md#outdated_header_files)güncelleştiriliyor.

## <a name="atl--mfc"></a>ATL/MFC

ATL ve MFC görece kararlı API 'lardır, ancak değişiklikler zaman zaman yapılır. Daha fazla bilgi için bkz [. C++ görsel değişiklik geçmişi 2003-2015](visual-cpp-change-history-2003-2015.md), Visual [Studio 'da Visual C++ için](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)yenilikler ve [ C++ Visual Studio 'da uygunluk geliştirmeleri](../overview/cpp-conformance-improvements.md).

### <a name="lnk-2005-_dllmain12-already-defined-in-msvcrtdlib"></a>LNK 2005 _DllMain@12 MSVCRTD. lib içinde zaten tanımlandı

Bu hata MFC uygulamalarında meydana gelebilir. CRT kitaplığı ve MFC Kitaplığı arasında bir sıralama sorunu olduğunu gösterir. MFC, New ve delete işleçleri sağlamak için önce bağlanmalıdır. Hatayı düzeltemedi, bu varsayılan kitaplıkları yoksaymak için `/NODEFAULTLIB` anahtarını kullanın: MSVCRTD. lib ve mfcs140d. lib. Daha sonra bu aynı kitaplıklar 'leri ek bağımlılıklar olarak ekleyin.

## <a name="32-vs-64-bit"></a>32 vs 64 bit

Özgün kodunuz 32-bit sistemler için derlenmişse, yeni bir 32 bit uygulamanın yanı sıra veya yerine 64 bit sürümü oluşturma seçeneğiniz vardır. Genel olarak, program derlemek için önce 32 bit modunda, sonra da 64 bit deneyirsiniz. 64-bit için derleme basittir, ancak bazı durumlarda 32 bit derlemeler tarafından gizlenen hataları ortaya çıkaralabilir.

Ayrıca, işaretçi boyutu, zaman ve boyut değerleriyle ilgili olası derleme zamanı ve çalışma zamanı sorunlarından ve printf ve scanf işlevlerinde biçim belirticilerine dikkat etmeniz gerekir. Daha fazla bilgi için bkz. [Visual C++ configure for 64-bit, x64 hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md) ve [genel C++ Visual 64-bit geçiş sorunları](../build/common-visual-cpp-64-bit-migration-issues.md). Ek geçiş ipuçları için bkz. [64 bit Windows Için Programlama Kılavuzu](/windows/win32/WinProg64/programming-guide-for-64-bit-windows).

## <a name="unicode-vs-mbcsascii"></a>Unicode vs MBCS/ASCII

Unicode, standartlaştırılmış olmadan önce, ASCII karakter kümesinde bulunmayan karakterleri temsil etmek için çok baytlı karakter kümesi (MBCS) kullandı. Daha eski MFC projelerinde, MBCS varsayılan ayardır ve böyle bir programı yükselttiğinizde, bunun yerine Unicode kullanmaya yönelik uyarılar görürsünüz. Unicode 'a dönüştürmeye karar verirseniz geliştirme maliyetine değer vermez, uyarıyı devre dışı bırakmayı veya yoksayabilirsiniz. Çözümünüzdeki tüm projeler için bunu devre dışı bırakmak için, **görünüm** > **Özellik Yöneticisi**açın, uyarıyı devre dışı bırakmak istediğiniz tüm projeler ' i seçin, ardından seçili öğelere sağ tıklayıp **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** ' **C++ ni > ** **Gelişmiş** > ' i seçin. **Belirli uyarıları devre dışı bırak** özelliğinde, açılan oku açın ve ardından **Düzenle**' yi seçin. Metin kutusuna 4996 girin. (' C ' önekini eklemeyin.) Özelliği kaydetmek için **Tamam** ' ı seçin ve ardından değişikliklerinizi kaydetmek için **Tamam** ' ı seçin.

Daha fazla bilgi için bkz. [MBCS 'Den Unicode 'A taşıma](porting-guide-spy-increment.md#porting_to_unicode). MBCS ile Unicode hakkında genel bilgi için bkz. [Internationalization](../c-runtime-library/internationalization.md) görsel [ C++ ve uluslararası hale getirme içindeki metin ve dizeler](../text/text-and-strings-in-visual-cpp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Projeleri Visual 'ın önceki sürümlerinden yükseltmeC++](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
