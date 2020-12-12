---
description: Daha fazla bilgi edinin:/MP (birden çok Işlemle derleme)
title: /MP (Birden Çok Süreçle Derleme)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.MultiProcessorCompilation
helpviewer_keywords:
- -MP compiler option (C++)
- /MP compiler option (C++)
- MP compiler option (C++)
- cl.exe compiler, multi-process build
ms.openlocfilehash: d5d4441be505dfc1251b099aa95a6ce1544289ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137793"
---
# <a name="mp-build-with-multiple-processes"></a>/MP (Birden Çok Süreçle Derleme)

**/MP** seçeneği, komut satırındaki Kaynak dosyaları derlemek için toplam süreyi azaltabilir. **/MP** seçeneği, derleyicinin her biri ayrı bir işlemde kendi kendisinin bir veya daha fazla kopyasını oluşturmasına neden olur. Bu kopyalar, kaynak dosyaları aynı anda derler. Sonuç olarak, kaynak dosyaları derlemek için toplam süre önemli ölçüde azaltılabilir.

## <a name="syntax"></a>Syntax

> **/MP**[*processMax*]

## <a name="arguments"></a>Arguments

*processMax*<br/>
Seçim Derleyicinin oluşturabileceğiniz en fazla işlem sayısı.

*ProcessMax* bağımsız değişkeni 1 ile 65536 arasında olmalıdır. Aksi takdirde, derleyici uyarı iletisi **D9014** yayınlar, *processMax* bağımsız değişkenini yoksayar ve en fazla işlem sayısı olan 1 olduğunu varsayar.

*ProcessMax* bağımsız değişkenini atlarsanız, derleyici bilgisayarınızdaki [etkin işlemcilerin](#effective_processors) sayısını işletim sisteminden alır ve her işlemci için bir işlem oluşturur.

## <a name="remarks"></a>Açıklamalar

**/MP** derleyici seçeneği, çok sayıda dosya derlerken derleme süresini önemli ölçüde azaltabilir. Derleme süresini geliştirmek için, derleyici kendisinin *en fazla processMax* kopyasını oluşturur ve ardından bu kopyaları, kaynak dosyalarınızı aynı anda derlemek için kullanır. **/MP** seçeneği derlemeler için geçerlidir ancak bağlama veya bağlama zamanı kod üretimi için kullanılamaz. Varsayılan olarak **/MP** seçeneği kapalıdır.

Derleme zamanında geliştirme bir bilgisayardaki işlemci sayısına, Derlenecek dosya sayısına ve g/ç kapasitesi gibi sistem kaynaklarının kullanılabilirliğine bağlıdır. Belirli bir projeyi oluşturmak için en iyi ayarı öğrenmek üzere **/MP** seçeneğini deneyin. Bu kararı vermenize yardımcı olacak öneriler için bkz. [yönergeler](#guidelines).

## <a name="incompatible-options-and-language-features"></a>Uyumsuz seçenekler ve dil özellikleri

**/MP** seçeneği bazı derleyici seçenekleri ve dil özellikleriyle uyumlu değildir. **/MP** seçeneğiyle uyumsuz bir derleyici seçeneği kullanırsanız, derleyici uyarı **D9030** ' ı yayınlar ve **/MP** seçeneğini yoksayar. Uyumsuz bir dil özelliği kullanırsanız, derleyici hata [C2813](../../error-messages/compiler-errors-2/compiler-error-c2813.md) sorun ve geçerli derleyici uyarı düzeyi seçeneğine bağlı olarak sona erer veya devam eder.

> [!NOTE]
> Çoğu seçenek, izin verildiğinde, eşzamanlı olarak çalıştırılan derleyicilerin çıktıları konsola veya belirli bir dosyaya aynı anda yazar. Sonuç olarak, çıkış birbirine karıştı ve karışacaktır. Bazı durumlarda, seçeneklerin birleşimi performansın daha kötüleştiğini getirir.

Aşağıdaki tabloda, **/MP** seçeneğiyle uyumsuz olan derleyici seçenekleri ve dil özellikleri listelenmektedir:

|Seçenek veya dil özelliği|Açıklama|
|--------------------------------|-----------------|
|[#import](../../preprocessor/hash-import-directive-cpp.md) Önişlemci yönergesi|Bir tür kitaplığındaki türleri C++ sınıflarına dönüştürür ve sonra bu sınıfları bir başlık dosyasına yazar.|
|[/e](e-preprocess-to-stdout.md), [/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıkışını standart çıktıya (**stdout**) kopyalar.|
|[/GM](gm-enable-minimal-rebuild.md)|Kullanım dışı. Artımlı yeniden derlemeyi etkinleştirilir.|
|[/showIncludes](showincludes-list-include-files.md)|Standart hata (**stderr**) için ekleme dosyaları listesini yazar.|
|[/YC](yc-create-precompiled-header-file.md)|Önceden derlenmiş bir üstbilgi dosyası yazar.|

## <a name="diagnostic-messages"></a>Tanılama Iletileri

**/MP** seçeneğiyle uyumsuz bir seçenek veya dil özelliği belirtirseniz, bir tanılama iletisi alırsınız. Aşağıdaki tabloda, derleyicisinin iletileri ve davranışı listelenmektedir:

|Tanılama İletisi|Açıklama|Derleyici davranışı|
|------------------------|-----------------|-----------------------|
|**C2813**|**#İmport** yönergesi **/MP** seçeneği ile uyumlu değil.|[Derleyici uyarı düzeyi](compiler-option-warning-level.md) seçeneği aksini belirtmediği takdirde derleme sonlanır.|
|**D9014**|*ProcessMax* bağımsız değişkeni için geçersiz bir değer belirtildi.|Derleyici geçersiz değeri yoksayar ve 1 değerini varsayar.|
|**D9030**|Belirtilen seçenek **/MP** ile uyumsuz.|Derleyici **/MP** seçeneğini yoksayar.|

## <a name="guidelines"></a><a name="guidelines"></a> Giderme

### <a name="measure-performance"></a>Ölçüm performansı

Performansı ölçmek için toplam derleme süresini kullanın. Derleme süresini fiziksel bir saatle ölçebilir veya yapı başladığında ve durdurulduğunda arasındaki farkı hesaplayan yazılımları kullanabilirsiniz. Bilgisayarınızda birden çok işlemci varsa, fiziksel saat bir yazılım süresi ölçümünden daha doğru sonuçlar verebilir.

### <a name="effective-processors"></a><a name="effective_processors"></a> Etkin Işlemciler

Bir bilgisayarda, fiziksel işlemcilerin her biri için *etkin işlemciler* olarak da bilinen bir veya daha fazla sanal işlemci olabilir. Her fiziksel işlemci bir veya daha fazla çekirdeğe sahip olabilir ve işletim sistemi çekirdek için hiper iş parçacığı etkinleştirmesine sahipse, her çekirdek iki sanal işlemci gibi görünür.

Örneğin, bir bilgisayarda tek bir çekirdek içeren bir fiziksel işlemcisi varsa ve hiper iş parçacığı devre dışı bırakılmışsa bir bilgisayarın etkin bir işlemcisi vardır. Buna karşılık, her birinin iki çekirdeği olan iki fiziksel işlemcisi varsa ve tüm çekirdekler hiper iş parçacığına sahipse, bir bilgisayarın sekiz etkin işlemcisi vardır. Diğer bir deyişle, (8 etkin işlemci) = (fiziksel işlemci başına 2 çekirdek) x (hiper iş parçacığı nedeniyle çekirdek başına 2 çekirdek) x (2 adet etkin işlemci).

**/MP** seçeneğinde *processMax* bağımsız değişkenini atlarsanız, derleyici işletim sisteminden etkili işlemci sayısını edinir ve sonra etkili işlemci başına bir işlem oluşturur. Ancak, derleyici belirli bir işlemcide hangi işlemin yürütüldüğünü garanti edemez; Bu karar, işletim sistemi tarafından yapılır.

### <a name="number-of-processes"></a>Işlem sayısı

Derleyici, kaynak dosyaları derlemek için kullanacağı işlem sayısını hesaplar. Bu değer, komut satırında belirttiğiniz kaynak dosya sayısının küçüktür ve **/MP** seçeneğiyle açıkça veya örtük olarak belirttiğiniz işlem sayısıdır. **/MP** seçeneğinin *processMax* bağımsız değişkenini sağlarsanız, en fazla işlem sayısını açık bir şekilde ayarlayabilirsiniz. Ya da varsayılan değeri, bir bilgisayardaki etkin işlemci sayısına eşit olan, *processMax* bağımsız değişkenini atlarsanız kullanabilirsiniz.

Örneğin, aşağıdaki komut satırını belirtdiğinizi varsayalım:

`cl /MP7 a.cpp b.cpp c.cpp d.cpp e.cpp`

Bu durumda, derleyici beş işlem kullanır çünkü bu, beş kaynak dosyası ve en fazla yedi işlem olur. Alternatif olarak, bilgisayarınızın iki etkin işlemciyi olduğunu ve aşağıdaki komut satırını belirtdiğinizi varsayalım:

`cl /MP a.cpp b.cpp c.cpp`

Bu durumda, işletim sistemi iki işlemciyi raporlar; Bu nedenle, derleyici hesaplamasında iki işlem kullanır. Sonuç olarak, derleme iki işlem ve üç kaynak dosyanın daha küçük olması nedeniyle derlemeyi iki işlemle yürütür.

### <a name="source-files-and-build-order"></a>Kaynak dosyalar ve derleme sırası

Kaynak dosyalar, komut satırında göründükleri sırada derlenmeyebilir. Derleyici derleyicinin kopyalarını içeren bir işlem kümesi oluştursa da, işletim sistemi her bir işlem yürütüldüğünde zamanlar. Sonuç olarak, kaynak dosyaların belirli bir sırada derlenip derlenemeyeceğini garanti edilemez.

Bir işlem derlemek için kullanılabilir olduğunda bir kaynak dosya derlenir. İşlemlerden daha fazla dosya varsa, ilk dosya kümesi kullanılabilir süreçler tarafından derlenir. Kalan dosyalar, bir işlem önceki bir dosyayı işlemeyi tamamladığında ve kalan dosyalardan birinde çalışmak için kullanılabilir olduğunda işlenir.

Bir komut satırında aynı kaynak dosyayı birden çok kez belirtmeyin. Bu durum, örneğin bir araç otomatik olarak bir projedeki bağımlılık bilgilerini temel alan [derleme görevleri dosyasını](contents-of-a-makefile.md) oluşturduğunda meydana gelebilir. **/MP** seçeneğini belirtmezseniz, derleyici dosya listesini sırayla işler ve dosyanın her oluşumunu yeniden derler. Ancak **/MP** seçeneğini belirtirseniz, farklı derleyiciler aynı anda aynı dosyayı derleyebilir. Sonuç olarak, farklı derleyiciler aynı anda aynı çıkış dosyasına yazmaya çalışacaktır. Bir derleyici, çıkış dosyasına özel yazma erişimi elde eder ve başarılı olur ve diğer derleyiciler bir dosya erişim hatası ile başarısız olur.

### <a name="using-type-libraries-import"></a>Tür kitaplıklarını kullanma (#import)

Derleyici, **/MP** anahtarıyla [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesinin kullanımını desteklemez. Mümkünse, bu sorunu geçici olarak çözmek için aşağıdaki adımları izleyin:

- `#import`Çeşitli kaynak dosyalarınızın tüm yönergelerini bir veya daha fazla dosyaya taşıyın ve ardından bu dosyaları **/MP** seçeneği olmadan derleyin. Sonuç, oluşturulan bir üst bilgi dosyası kümesidir.

- Kalan kaynak dosyalarınızda, oluşturulan üstbilgileri belirten [#include](../../preprocessor/hash-include-directive-c-cpp.md) yönergeler ekleyin ve ardından **/MP** seçeneğini kullanarak kalan kaynak dosyalarınızı derleyin.

### <a name="visual-studio-project-settings"></a>Visual Studio proje ayarları

#### <a name="the-msbuildexe-tool"></a>MSBUILD.exe aracı

Visual Studio, çözüm ve proje derlemek için [MSBuild.exe](/visualstudio/msbuild/msbuild-reference) aracını kullanır. MSBuild.exe aracının **/maxcpucount:**_Number_ (veya **/m:**_Number_) komut satırı seçeneği aynı anda birden çok proje oluşturabilir. Ve **/MP** derleyici seçeneği aynı anda birden çok derleme birimi oluşturabilir. Uygulamanız için uygun ise, hem **/MP** hem de **/maxcpucount** kullanarak çözümünüzün derleme süresini geliştirin.

Çözümünüzün derleme süresi kısmen, derlemeyi gerçekleştiren işlem sayısına bağlıdır. [/Maxcpucount](/visualstudio/msbuild/msbuild-command-line-reference) MSBuild seçeneğinin *Number* bağımsız değişkeni, aynı anda oluşturulacak en fazla proje sayısını belirtir. Benzer şekilde, **/MP** derleyici seçeneğinin *processMax* bağımsız değişkeni, aynı anda oluşturulacak en fazla derleme birimi sayısını belirtir. **/Maxcpucount** seçeneği *P* projelerini belirtiyorsa, **/MP** seçeneği *C* süreçlerini belirtiyorsa, aynı anda en fazla *P* x *C* işlemi yürütülür.

MSBuild veya **/MP** teknolojisinin kullanılıp kullanılmayacağını belirleme Kılavuzu aşağıdaki gibidir:

- Her projede birkaç dosya içeren çok sayıda proje varsa, MSBuild aracını kullanın.

- Her projede çok sayıda dosya içeren birkaç proje varsa **/MP** seçeneğini kullanın.

- Proje başına proje ve dosya sayısı dengeyse, hem MSBuild hem de **/MP** kullanın. İlk olarak **/maxcpucount** seçeneğini derlemek için proje sayısına ve **/MP** seçeneğini bilgisayarınızdaki işlemci sayısına ayarlayın. Performansı ölçün ve en iyi sonuçları verecek şekilde ayarlarınızı yapın. Toplam derleme süresi karşılanana kadar bu döngüyü tekrarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[#import yönergesi](../../preprocessor/hash-import-directive-cpp.md)<br/>
[Komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference)<br/>
[/ZF (Daha hızlı PDB oluşturma)](zf.md)<br/>
