---
title: Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)
ms.date: 05/03/2019
ms.assetid: 2c99a8cb-098f-4a9d-bf2c-b80fd06ace43
ms.openlocfilehash: 44fcb6776118e829fe7c96e54f3f51615604ac31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368479"
---
# <a name="overview-of-potential-upgrade-issues-visual-c"></a>Olası Yükseltme Sorunlarına Genel Bakış (Visual C++)

Yıllar içinde, Microsoft C++ derleyicisi, C++ dilinin kendisi, C++ Standart Kitaplığı, C çalışma zamanı (CRT) ve MFC ve ATL gibi diğer kitaplıklarda yapılan değişikliklerle birlikte birçok değişiklik yaşadı. Sonuç olarak, Visual Studio'nun önceki bir sürümünden bir uygulamayı yükseltirken derleyici ve bağlayıcı hataları ve daha önce temiz bir şekilde derlenmiş kod daki uyarılarla karşılaşabilirsiniz. Orijinal kod tabanı ne kadar eskise, bu tür hatalar için potansiyel de o kadar büyük tür. Bu genel bakış, karşılaşabileceğiniz en yaygın sorun sınıflarını özetler ve daha ayrıntılı bilgilere bağlantılar sağlar.

> [!NOTE]
> Geçmişte, Visual Studio'nun çeşitli sürümlerini kapsayan yükseltmelerin her seferinde kademeli olarak bir sürüm yapılmasını tavsiye ettik. Artık bu yaklaşımı önermiyoruz. Kod tabanı ne kadar eski olursa olsun Visual Studio'nun en güncel sürümüne yükseltmenin neredeyse her zaman daha kolay olduğunu gördük.

Yükseltme işlemi yle ilgili sorular veya vcupgrade@microsoft.comyorumlar .

## <a name="library-and-toolset-dependencies"></a>Kitaplık ve araç kümesi bağımlılıkları

> [!NOTE]
> Bu bölüm Visual Studio 2013 ve daha önce siyle oluşturulmuş uygulamalar ve kütüphaneler için geçerlidir. Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019'da kullanılan araç setleri ikili uyumludur. Daha fazla bilgi için Visual [Studio 2015 ile Visual Studio 2019 arasındaki C++ İkili Uyumluluk'a](binary-compat-2015-2017.md)bakın.

Bir uygulamayı Visual Studio'nun yeni bir sürümüne yükseltirken, hem tavsiye edilir hem de birçok durumda uygulamanın bağlantı verdiği tüm kitaplıkları ve DL'leri yükseltmek gerekir. Kaynak koduna erişiminiz olması veya kitaplık satıcısının derleyicinin aynı ana sürümüyle derlenmiş yeni ikili dosyalar sağlayabileceğini gerektirir. Bu koşullardan biri doğruysa, ikili uyumluluk ayrıntılarıyla ilgilenen bu bölümü atlayabilirsiniz. Durum böyle değilse, yükseltilmiş uygulamanızdaki kitaplıkları kullanamayabilirsiniz. Bu bölümdeki bilgiler, yükseltmeye devam edip edemeyeceğiniz konusunda anlamanıza yardımcı olacaktır.

### <a name="toolset"></a>Araç Takımı

.obj ve .lib dosya biçimleri iyi tanımlanmıştır ve nadiren değişir. Bazen bu dosya biçimlerine eklemeler yapılır, ancak bu eklemeler genellikle daha yeni araç kümelerinin nesne dosyalarını ve eski araç kümeleri tarafından üretilen kitaplıkları kullanma yeteneğini etkilemez. Burada büyük bir istisna / [GL (Tüm Program Optimizasyonu)](../build/reference/gl-whole-program-optimization.md)kullanarak derlemek eğer. 'yi kullanarak `/GL`derlerseniz, ortaya çıkan nesne dosyası yalnızca onu üretmek için kullanılan araç kümesi kullanılarak bağlanabilir. Bu nedenle Visual Studio 2017 (v141) derleyicisi ile `/GL` bir nesne dosyası üretiyorsanız ve kullanıyorsanız Visual Studio 2017 (v141) bağlantısını kullanarak bağlamanız gerekir. Bunun nedeni, nesne dosyalarının içindeki iç veri yapılarının araç kümesinin ana sürümlerinde kararlı olmaması ve yeni araç kümelerinin eski veri biçimlerini anlamamasıdır.

C++'Da kararlı bir uygulama ikili arabirimi (ABI) yoktur. Ancak Visual Studio, bir sürümün tüm küçük sürümleri için kararlı bir C++ ABI'ye aittir. Visual Studio 2015 (v140), Visual Studio 2017 (v141) ve Visual Studio 2019 (v142) sadece küçük versiyonlarına göre değişiklik gösterir. Hepsi 14 aynı ana sürüm numarasına sahip. Daha fazla bilgi için Visual [Studio 2015 ile Visual Studio 2019 arasındaki C++ İkili Uyumluluk'a](binary-compat-2015-2017.md)bakın.

C++ bağlantısına sahip dış sembollere sahip bir nesne dosyanız varsa, bu nesne dosyası araç kümesinin farklı bir ana sürümü tarafından üretilen nesne dosyalarıyla doğru şekilde bağlantı kurmayabilir. Birçok olası sonuç vardır: bağlantı tamamen başarısız olabilir (örneğin, isim dekorasyonu değiştiyse). Bağlantı başarılı olabilir ve işler çalışma zamanında çalışmayabilir (örneğin, tür düzeni değiştiyse). Ya da birçok durumda, işler işe yarayabilir ve hiçbir şey ters gitmez. Ayrıca, C++ ABI kararlı olmasa da, C ABI ve COM için gerekli C++ ABI alt kümesi kararlıdır.

Bir alma kitaplığına bağlanırsanız, Visual Studio'nun ABI uyumluluğunu koruyan daha sonraki herhangi bir sürümü çalışma zamanında kullanılabilir. Örneğin, uygulamanız Visual Studio 2015 Update 3 araç seti kullanılarak derlenmiş ve bağlantılıysa, 2015, 2017 ve 2019 kitaplıkları geriye doğru ikili uyumluluğu koruduğu için visual studio 2017 veya Visual Studio 2019 yeniden dağıtılabilir olarak kullanabilirsiniz. Tersi doğru değildir: Uyumlu bir ABI'leri olsa bile, araç kümesinin önceki bir sürümü için kodunuzu oluşturmak için kullandığınızdan daha fazla yeniden dağıtılabilir kullanamazsınız.

### <a name="libraries"></a>Kitaplıklar

Visual Studio C++ kitaplıkları üstbilgi dosyalarının belirli bir sürümünü kullanarak bir kaynak dosya derlerseniz (üstbilgi #including tarafından), ortaya çıkan nesne dosyası kitaplıkların aynı sürümüyle bağlantılı olmalıdır. Bu nedenle, örneğin, kaynak dosyanız Visual Studio 2015 \<Update 3 immintrin.h> ile derlenmişse, Visual Studio 2015 Update 3 vcruntime kitaplığına bağlantı vermelisiniz. Benzer şekilde, kaynak dosyanız Visual Studio 2017 sürüm 15.5 \<iostream> ile derlenmişse, Visual Studio 2017 sürüm 15.5 Standart C++ kitaplığı, msvcprt ile bağlantı kurmanız gerekir. Karıştırma ve eşleştirme desteklenmez.

C++ Standart Kitaplığı için, Visual Studio 2010'dan beri `#pragma detect_mismatch` standart üstbilgide kullanılması yla karıştırma ve eşleştirmeye açıkça izin verilmemiştir. Uyumsuz nesne dosyalarını bağlamaya çalışırsanız veya yanlış standart kitaplıkla bağlantı kurmaya çalışırsanız, bağlantı başarısız olur.

CRT için karıştırma ve eşleştirme hiçbir zaman desteklenmedi, ancak en azından Visual Studio 2015 ve Universal CRT'ye kadar işe yaradı, çünkü API yüzeyi zaman içinde çok fazla değişmedi. Universal CRT geriye doğru uyumluluğu kırdı, böylece gelecekte geriye doğru uyumluluğu koruyabiliyoruz. Başka bir deyişle, gelecekte yeni, sürümlü Evrensel CRT ikililerini tanıtma gibi bir planımız yok. Bunun yerine, varolan Evrensel CRT artık yerinde güncelleştirilir.

Microsoft C Runtime üstbilgilerinin eski sürümleriyle derlenen nesne dosyaları (ve kitaplıklar) ile kısmi bağlantı uyumluluğu sağlamak için Visual Studio 2015 ve sonraki sürümlerle birlikte bir kitaplık, legacy_stdio_definitions.lib sağlarız. Bu kitaplık, Evrensel CRT'den kaldırılan işlevlerin ve veri dışaaklarının çoğu için uyumluluk sembolleri sağlar. legacy_stdio_definitions.lib tarafından sağlanan uyumluluk sembolleri kümesi, Windows SDK'da yer alan kitaplıklarda bulunan tüm bağımlılıklar da dahil olmak üzere çoğu bağımlılığı karşılamak için yeterlidir. Ancak, uyumluluk sembolleri sağlamak mümkün değildir Evrensel CRT kaldırıldı bazı semboller vardır. \_ \_Bu semboller bazı işlevleri (örneğin,\_iob func) ve veri \_ \_\_\_\_dışa \_ \_aktarımlarını (örneğin, imp iob,\_\_\_imp pctype, \_ \_imp\_\_\_mb\_cur\_max) içerir.

C Runtime üstbilgilerinin eski bir sürümüyle oluşturulmuş statik bir kitaplığınız varsa, aşağıdaki eylemleri şu sırayla öneririz:

1. Universal CRT ile bağlantı kurmak için Visual Studio'nun yeni sürümünü ve Evrensel CRT üsterlerini kullanarak statik kitaplığı yeniden oluşturabilirsiniz. Bu yaklaşım tam olarak desteklenen (ve böylece en iyi) seçenektir.

1. Statik kitaplığı yeniden oluşturamıyorsanız (veya yeniden oluşturmak istemiyorsanız), eski\_stdio\_tanımları.lib ile bağlantı yapmayı deneyebilirsiniz. Statik kitaplığınızın bağlantı-zaman bağımlılıklarını karşılarsa, [Evrensel CRT'de yapılan davranış değişikliklerinden](visual-cpp-change-history-2003-2015.md#BK_CRT)olumsuz etkilenmediğinden emin olmak için statik kitaplığı ikilide kullanıldığı gibi kapsamlı bir şekilde sınamak isteyeceksiniz.

1. Statik kitaplığınız bağımlılıkları eski\_stdio\_definitions.lib tarafından karşılanmazsa veya kitaplık yukarıda belirtilen davranış değişiklikleri nedeniyle Evrensel CRT ile çalışmıyorsa, statik kitaplığınızı Microsoft C Runtime'ın doğru sürümüyle bağlantı kuracağınız bir DLL'ye kapsüllemenizi öneririz. Örneğin, statik kitaplık Visual Studio 2013 kullanılarak oluşturulmuşsa, visual studio 2013 ve Visual Studio 2013 C++ kitaplıklarını kullanarak bu DLL'yi oluşturmak isteyebilirsiniz. Kitaplığı bir DLL'ye oluşturarak, Microsoft C Runtime'ın belirli bir sürümüne olan bağımlılığı olan uygulama ayrıntısını kapsüllersiniz. DLL arabiriminin, örneğin, Bir DOSYA*yı DLL sınırı boyunca döndürerek veya yer değiştirme yle ayrılan bir işaretçiyi döndürerek ve arayanın onu serbest etmesini bekleyerek, c runtime kullandığı ayrıntıları sızdırmadığına dikkat etmek istersiniz.

Tek bir işlemde birden fazla CRT kullanımı kendi başına sorunlu değildir (gerçekten de, çoğu işlem birden fazla CRT DLLyükleme sona erecek; örneğin, Windows işletim sistemi bileşenleri msvcrt.dll bağlıdır ve CLR kendi özel CRT bağlıdır). Farklı CRT'lerden karışık durum ortaya çıktığında sorunlar ortaya çıkar. Örneğin, msvcr110.dll!malloc kullanarak bellek ayırmamalı ve msvcr120.dll!free kullanarak bu belleği ayırmaya çalışmamalısınız ve msvcr110!fopen kullanarak bir DOSYAyı açmaya çalışmamalısınız ve msvcr120!fread kullanarak bu DOSYAdan okumaya çalışmamalısınız. Durumu farklı CRT'lerden karmakarışık hale getirmediğiniz sürece, tek bir işlemde birden çok CRT'yi güvenli bir şekilde yükleyebilirsiniz.

Daha fazla bilgi için [kodunuzu Evrensel CRT'ye yükseltin' e](upgrade-your-code-to-the-universal-crt.md)bakın.

## <a name="errors-due-to-project-settings"></a>Proje ayarları nedeniyle hatalar

Yükseltme işlemini başlatmak için Visual Studio'nun en son sürümünde eski bir proje/çözüm/çalışma alanı açın. Visual Studio, eski proje ayarlarını temel alan yeni bir proje oluşturur. Eski projede kitaplık varsa veya standart olmayan konumlara sabit kodlanmış yollar içeriyorsa, proje varsayılan ayarları kullandığında bu yollardaki dosyaların derleyici tarafından görülemaması mümkündür. Daha fazla bilgi için [Linker OutputFile ayarına](porting-guide-spy-increment.md#linker_output_settings)bakın.

Genel olarak, proje bakımını basitleştirmek ve yükseltilmiş kod derlemenizi mümkün olan en kısa sürede elde etmeye yardımcı olmak için proje kodunuzu düzgün bir şekilde düzenlemek için harika bir zaman. Kaynak kodunuz zaten iyi düzenlenmişse ve eski projeniz Visual Studio 2010 veya sonraki lerle derlenmişse, hem eski hem de yeni derleyicide derlemeyi desteklemek için yeni proje dosyasını el ile düzenleyebilirsiniz. Aşağıdaki örnek, Visual Studio 2015 ve Visual Studio 2017 için nasıl derlenenleri gösterir:

```xml
<PlatformToolset Condition="'$(VisualStudioVersion)'=='14.0'">v140</PlatformToolset>
<PlatformToolset Condition="'$(VisualStudioVersion)'=='15.0'">v141</PlatformToolset>
```

### <a name="lnk2019-unresolved-external"></a>LNK2019: Çözülmemiş harici

Çözülmemiş semboller için proje ayarlarınızı düzeltmeniz gerekebilir.

- Kaynak dosya varsayılan olmayan bir konumdaysa, projedeki dahil dizinlerine yolu eklediniz mi?

- Dış bir .lib dosyasında tanımlanmışsa, proje özelliklerinde lib yolunu belirttiniz mi ve .lib dosyasının doğru sürümü orada mı bulunuyor?

- Visual Studio'nun farklı bir sürümüyle derlenmiş bir .lib dosyasına bağlanmaya mı çalışıyorsunuz? Bu nedenle, kitaplık ve araç kümesi bağımlılıkları ile ilgili önceki bölüme bakın.

- Çağrı yerindeki bağımsız değişken türleri gerçekten işlevin varolan aşırı yüküyle eşleşmiyor mu? İşlevin imzasındaki ve işlevi çağıran koddaki herhangi bir yazı tipi için temel türleri doğrulayın.

Çözülmemiş sembol hatalarını gidermek için, ikili olarak tanımlanan simgeleri incelemek için dumpbin.exe'yi kullanmayı deneyebilirsiniz. Kitaplıkta tanımlanan simgeleri görüntülemek için aşağıdaki komut satırını deneyin:

```cmd
dumpbin.exe /LINKERMEMBER somelibrary.lib
```

### <a name="zcwchar_t-wchar_t-is-native-type"></a>/Zc:wchar_t (wchar_t Yerel Tür)

(Microsoft Visual C++ 6.0 ve daha önce, **wchar_t** yerleşik bir tür olarak uygulanmadı, ancak wchar.h'de imzasız kısa için typedef olarak beyan edildi.) C++ standardı, **wchar_t** yerleşik bir tür olması gerekir. Typedef sürümünü kullanmak taşınabilirlik sorunlarına neden olabilir. Visual Studio'nun önceki sürümlerinden yükseltme yapıp c2664 derleyici hatasıyla karşılaşırsanız, kod bir **wchar_t** **imzasız kısaya**dolaylı olarak dönüştürmeye `/Zc:wchar_t-`çalışıyorsa, kodu ayar yerine hatayı düzeltmek için değiştirmenizi öneririz. Daha fazla bilgi için [bkz: /Zc:wchar_t (wchar_t Yerli Türüdür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

### <a name="upgrading-with-the-linker-options-nodefaultlib-entry-and-noentry"></a>Bağlantı seçenekleri /NODEFAULTLIB, /ENTRY ve /NOENTRY ile yükseltme

`/NODEFAULTLIB` Bağlayıcı seçeneği (veya Tüm Varsayılan Kitaplıkları Yoksay özelliği) bağlayıcıya CRT gibi varsayılan kitaplıklara otomatik olarak bağlanmamasını söyler. Bu, her kitaplığın giriş olarak ayrı ayrı listelenilmesi gerektiği anlamına gelir. Bu kitaplık listesi, **Project Properties** iletişim kutusunun **Bağlayıcı** bölümündeki **Ek Bağımlılıklar** özelliğinde verilir.

Varsayılan kitaplıklardan bazılarının içeriği yeniden diziliş olduğundan, bu seçeneği kullanan projeler yükseltme yaparken bir sorun sunar. Her kitaplığın **Ek Bağımlılıklar** özelliğinde veya bağlayıcı komut satırında listelenilmesi gerektiğinden, tüm geçerli adları kullanmak için kitaplıkların listesini güncelleştirmeniz gerekir.

Aşağıdaki tablo, Visual Studio 2015'ten itibaren içeriği değişen kitaplıkları gösterir. Yükseltmek için, ikinci sütundaki yeni kitaplık adlarını ilk sütundaki kitaplıklara eklemeniz gerekir. Bu kütüphanelerin bazıları ithalat kütüphaneleri, ama bu önemli olmamalıdır.

|||
|-|-|
|Kullanıyorsanız:|Bu kitaplıkları kullanmanız gerekir:|
|libcmt.lib|libcmt.lib, libucrt.lib, libvcruntime.lib|
|libcmtd.lib|libcmtd.lib, libucrtd.lib, libvcruntimed.lib|
|msvcrt.lib|msvcrt.lib, ucrt.lib, vcruntime.lib|
|msvcrtd.lib|msvcrtd.lib, ucrtd.lib, vcruntimed.lib|

Varsayılan kitaplıkları atlayarak da `/ENTRY` etkisi `/NOENTRY` olan seçeneği veya seçeneği kullanırsanız, aynı sorun da geçerlidir.

## <a name="errors-due-to-improved-language-conformance"></a>Gelişmiş dil uyumluluğu nedeniyle hatalar

Microsoft C++ derleyicisi, yıllar içinde C++ standardına uygunluğunu sürekli olarak iyileştirmiştir. Derleyici daha önce göz ardı ettiği veya açıkça izin verdiği bir hatayı doğru şekilde işaretlediği için, önceki sürümlerde derlenen kod Visual Studio'nun sonraki sürümlerinde derlenmeyi başaramayabilir.

Örneğin, `/Zc:forScope` anahtar MSVC tarihinin başlarında tanıtıldı. Döngü değişkenleri için uygun olmayan davranışlara izin verir. Bu anahtar artık amortismana kaldırılmış ve gelecekteki sürümlerde kaldırılabilir. Kodunuzu yükseltirken bu anahtarı kullanmamanız önerilir. Daha fazla bilgi için [bkz: /Zc:forScope- amortismana hazır.](porting-guide-spy-increment.md#deprecated_forscope)

Yükseltme yaparken görebileceğiniz ortak bir derleyici hatasının bir örneği, const olmayan bir bağımsız değişkenin const parametreye geçirilmesidir. Derleyicinin eski sürümleri her zaman bir hata olarak işaretlemedi. Daha fazla bilgi için [derleyicinin daha katı dönüşümlerine](porting-guide-spy-increment.md#stricter_conversions)bakın.

Belirli uygunluk iyileştirmeleri hakkında daha fazla bilgi için Visual [Studio'daki Visual C++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md) ve [C++ uyumluluk geliştirmelerine](../overview/cpp-conformance-improvements.md)bakın.

## <a name="errors-involving-stdinth-integral-types"></a>stdint.h> integral türlerini içeren \<hatalar

\<stdint.h> üstbilgi, yerleşik integral türlerinin aksine tüm platformlarda belirli bir uzunluğa sahip olması garanti edilen typedefs ve makroları tanımlar. Bazı örnekler `uint32_t` `int64_t`ve . \<Stdint.h> başlığı Visual Studio 2010'da eklenmiştir. 2010'dan önce yazılmış kod bu türler için özel tanımlar sağlamış olabilir ve \<bu tanımlar her zaman stdint.h> tanımlarıyla tutarlı olmayabilir.

Hata C2371 ise ve `stdint` bir tür söz konusuysa, bu büyük olasılıkla türün kodunuzda veya üçüncü taraf bir lib dosyasında bir üstbilgide tanımlandığı anlamına gelir. Yükseltme yaparken, stdint.h> \<türlerinin özel tanımlarını ortadan kaldırmanız gerekir, ancak önce yeni sorunlar sunmadığınızdan emin olmak için özel tanımları geçerli standart tanımlarla karşılaştırmalısınız.

Söz konusu türün tanımlandığı yeri görmek için **F12** **(Tanıya Git)** tuşuna basabilirsiniz.

[/showIncludes](../build/reference/showincludes-list-include-files.md) derleyici seçeneği burada yararlı olabilir. Projeniz için **Özellik Sayfaları** iletişim kutusunda **C/C++** > **Gelişmiş** sayfasını açın ve **Gösterir'i** **Evet**olarak ayarlayın. Ardından projenizi yeniden oluşturun `#include`ve çıkış penceresindeki s listesini görün. Her üstbilgi, onu içeren üstbilginin altına girintilir.

## <a name="errors-involving-crt-functions"></a>CRT işlevlerini içeren hatalar

Yıllar içinde C çalışma zamanında birçok değişiklik yapıldı. Işlevlerin birçok güvenli sürümü eklendi ve bazıları kaldırıldı. Ayrıca, bu makalede daha önce açıklandığı gibi, Microsoft'un CRT uygulaması Visual Studio 2015'te yeni ikili dosyalara ve ilişkili .lib dosyalarına yeniden eklenmiştir.

Bir hata bir CRT işlevi içeriyorsa, visual [c++ değişiklik geçmişi 2003 - 2015](visual-cpp-change-history-2003-2015.md) veya [C++ uygunluk geliştirmelerini Visual Studio'da](../overview/cpp-conformance-improvements.md) arayayın ve bu makalelerin ek bilgi içerip içermediğini görün. Hata LNK2019 ise, çözümlenmemiş dış işlevin kaldırılmadı emin olun. Aksi takdirde, işlevin hala var olduğundan eminseniz ve arama kodu doğruysa, `/NODEFAULTLIB`projenizin kullanıp kullanmadığını denetleyin. Bu nedenle, projenin yeni evrensel (UCRT) kitaplıklarını kullanması için kitaplıkların listesini güncelleştirmeniz gerekir. Daha fazla bilgi için, Kitaplık ve bağımlılıklar hakkında yukarıdaki bölüme bakın.

Hata `printf` içeriyorsa `scanf`veya stdio.h dahil olmadan özel olarak her iki işlevi tanımlamadığınızdan emin olun. Bu ysa, özel tanımları kaldırın veya\_eski\_stdio definitions.lib bağlantı. Bu kitaplığı Özellik **Sayfaları** iletişim kutusunda Ek **Bağımlılıklar** özelliğinde **Configuration Properties** > **Linker** > **Girişi**altında ayarlayabilirsiniz. Windows SDK 8.1 veya daha önce bağlantı\_kuruyorsanız, eski stdio\_definitions.lib ekleyin.

Hata biçim dize bağımsız değişkenleri içeriyorsa, derlemenin standardı zorlama konusunda daha katı olması büyük olasılıkladır. Daha fazla bilgi için değişiklik geçmişine bakın. Burada yapılan hatalara dikkat edin, çünkü bunlar bir güvenlik riski temsil edebilir.

## <a name="errors-due-to-changes-in-the-c-standard"></a>C++ standardındaki değişikliklerden kaynaklanan hatalar

C++ standardı nın kendisi her zaman geriye dönük uyumlu olmayan şekillerde gelişmiştir. Hareket semantik, yeni anahtar kelimeler ve diğer dil ve standart kitaplık özelliklerinin C++11'inde giriş, derleyici hatalarına ve hatta farklı çalışma zamanı davranışına neden olabilir.

Örneğin, eski bir C++ programı iostream.h üstbilgisini içerebilir. Bu başlık C++ tarihinin başlarında küçümsenir ve sonunda Visual Studio'dan tamamen kaldırıldı. Bu durumda, iostream \<> kullanmanız ve kodunuzu yeniden yazmanız gerekir. Daha fazla bilgi için [bkz.](porting-guide-spy-increment.md#updating_iostreams_code)

### <a name="c4838-narrowing-conversion-warning"></a>C4838: dönüşüm uyarısını daraltma

C++ standardı artık imzalanmamış integral değerlerinden yapılan dönüşümlerin dönüşümleri daraltma olarak kabul edilir olduğunu belirtir. Derleyici bu uyarıyı Visual Studio 2015'ten önce yükseltmedi. Daralmanın kodunuzu doğru etkilemediğinden emin olmak için her oluşumu inceleyin.

## <a name="warnings-to-use-secure-crt-functions"></a>Güvenli CRT işlevlerini kullanma uyarıları

Yıllar geçtikçe, C çalışma zamanı işlevlerinin güvenli sürümleri tanıtıldı. Eski, güvenli olmayan sürümler hala kullanılabilir olmasına rağmen, güvenli sürümleri kullanmak için kodunuzu değiştirmeniz önerilir. Derleyici, güvenli olmayan sürümlerin kullanımı için bir uyarı yayımlar. Bu uyarıları devre dışı bırakmayı veya yoksaymayı seçebilirsiniz. Çözümünüzdeki tüm projeler için uyarıyı devre dışı bırakıp, Özelliği **Görüntüle** > **Yöneticisi'ni**açın, uyarıyı devre dışı bırakıp, ardından seçili öğelere sağ tıklayın ve **Özellikler'i**seçin. **Yapılandırma Özellikleri** > **C/C++** > **Gelişmiş**altında **Özellik Sayfaları** iletişim kutusunda, Belirli Uyarıları Devre **Dışı'** yı seçin. Açılan ok'a tıklayın ve sonra **Edit'e**tıklayın. Metin kutusuna 4996 girin. ('C' önekini eklemeyin.) Daha fazla bilgi [için Güvenli CRT'yi kullanmak için Taşıma'ya](porting-guide-spy-increment.md#porting_to_secure_crt)bakın.

## <a name="errors-due-to-changes-in-windows-apis-or-obsolete-sdks"></a>Windows API'lerinde veya eski SDK'larda yapılan değişikliklerden kaynaklanan hatalar

Yıllar geçtikçe, Windows API'leri ve veri türleri eklendi ve bazen değiştirildi veya kaldırıldı. Ayrıca, çekirdek işletim sistemine ait olmayan diğer SDK'lar geldi ve gitti. Bu nedenle, eski programlar artık var olmayan API'lere çağrı içerebilir. Ayrıca, artık desteklenmeyen diğer Microsoft SDK'larında API'lere yapılan çağrıları da içerebilir. Eski bir Microsoft SDK'dan bir Windows API veya API içeren bir hata görürseniz, bir API kaldırılmış ve/veya yerine daha yeni, daha güvenli bir işlev getirilmiş olabilir.

Geçerli API kümesi ve belirli bir Windows API'si için desteklenen minimum işletim sistemleri hakkında daha fazla bilgi için [Microsoft API ve başvuru kataloğuna](https://msdn.microsoft.com/library) bakın ve söz konusu API'ye gidin.

### <a name="windows-version"></a>Windows sürümü

Windows API'sını doğrudan veya dolaylı olarak kullanan bir programı yükseltirken, destekleyecek en az Windows sürümüne karar vermeniz gerekir. Çoğu durumda, Windows 7 iyi bir seçimdir. Daha fazla bilgi için [Üstbilgi dosyası sorunlarına](porting-guide-spy-increment.md#header_file_problems)bakın. Makro, `WINVER` programınızın üzerinde çalışmak üzere tasarladığı en eski Windows sürümünü tanımlar. MFC programınız WINVER'i 0x0501 (Windows XP) olarak ayarlarsa, derleyicinin xp modu na rağmen MFC artık XP'yi desteklemediği için bir uyarı alırsınız.

Daha fazla bilgi için bkz: Hedef Windows Sürümü ve [Daha eski üstbilgi dosyalarını](porting-guide-spy-increment.md#outdated_header_files) [güncelleştirme.](porting-guide-spy-increment.md#updating_winver)

## <a name="atl--mfc"></a>ATL / MFC

ATL ve MFC nispeten kararlı API'lerdir, ancak değişiklikler bazen yapılır. Daha fazla bilgi için Visual [C++ change history 2003 - 2015](visual-cpp-change-history-2003-2015.md), [Visual Studio'da Visual C++ için Yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)ve Visual [Studio'daki C++ uyumluluk geliştirmelerine](../overview/cpp-conformance-improvements.md)bakın.

### <a name="lnk-2005-_dllmain12-already-defined-in-msvcrtdlib"></a>LNK 2005 _DllMain@12 zaten MSVCRTD.lib tanımlanan

Bu hata MFC uygulamalarında oluşabilir. CRT kitaplığı ile MFC kitaplığı arasında bir sipariş sorunu gösterir. MFC'ye yeni ve silme işleçleri sağlaması için önce bağlanılması gerekir. Hatayı düzeltmek için, `/NODEFAULTLIB` bu varsayılan kitaplıkları yoksay: MSVCRTD.lib ve mfcs140d.lib için anahtarı kullanın. Sonra ek bağımlılıklar olarak bu aynı libs ekleyin.

## <a name="32-vs-64-bit"></a>32 vs 64 bit

Orijinal kodunuz 32 bit sistemler için derlenmişse, yeni bir 32 bit uygulama yerine veya ek olarak 64 bit sürümü oluşturma seçeneğiniz vardır. Genel olarak, önce programınızı 32 bit modunda derlemeye almalı ve ardından 64 bit denemelisiniz. 64 bit için derleme basittir, ancak bazı durumlarda 32 bit yapılar tarafından gizlenmiş hataları ortaya çıkarabilir.

Ayrıca, işaretçi boyutu, zaman ve boyut değerleri ve printf ve scanf işlevlerinde biçim belirteçleri ile ilgili olası derleme zamanı ve çalışma zamanı sorunları nın farkında olmalısınız. Daha fazla bilgi için bkz: [64 bit, x64 hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md) ve [Ortak Görsel C++ 64 bit Geçiş Sorunları](../build/common-visual-cpp-64-bit-migration-issues.md)için Visual C++'ı yapılandırın. Ek geçiş ipuçları [için, 64 bit Windows için Programlama Kılavuzu'na](/windows/win32/WinProg64/programming-guide-for-64-bit-windows)bakın.

## <a name="unicode-vs-mbcsascii"></a>Unicode vs MBCS/ASCII

Unicode standartlaştırılmadan önce, birçok program ASCII karakter kümesine dahil edilmeyen karakterleri temsil etmek için Multibyte Karakter Kümesi'ni (MBCS) kullandı. Eski MFC projelerinde, MBCS varsayılan ayardı ve böyle bir programı yükselttiğinde, bunun yerine Unicode'u kullanmanızı tavsiye eden uyarılar görürsünüz. Unicode'a dönüştürmenin geliştirme maliyetine değmediğine karar verirseniz uyarıyı devre dışı bırakmayı veya yok saymayı seçebilirsiniz. Çözümünüzdeki tüm projeler için devre dışı bırakmayı, **Özelliği Görüntüle** > **Yöneticisi'ni**açın, uyarıyı devre dışı bırakıp, ardından seçili öğelere sağ tıklayın ve **Özellikler'i**seçin. Özellik **Sayfaları** iletişim kutusunda, **Yapılandırma Özellikleri** > **C/C++** > **Gelişmiş'i**seçin. Belirli **Uyarıları Devre Dışı Bırak** özelliğinde açılır okaçık ve sonra **Edit'i**seçin. Metin kutusuna 4996 girin. ('C' önekini eklemeyin.) Özelliği kaydetmek için **Tamam'ı** seçin, ardından değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

Daha fazla bilgi için [MBCS'den Unicode'a taşıma](porting-guide-spy-increment.md#porting_to_unicode)ya da taşıma 'ya bakın. MBCS ve Unicode hakkında genel bilgi için [Visual C++ ve Internationalization'da Metin ve Strings'e](../text/text-and-strings-in-visual-cpp.md) bakın. [Internationalization](../c-runtime-library/internationalization.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'nin önceki sürümlerinden projeleri yükseltme](upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br/>
[Visual Studio’deki C++ uyumluluk geliştirmeleri](../overview/cpp-conformance-improvements.md)
