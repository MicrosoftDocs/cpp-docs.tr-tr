---
title: /MP (Birden Çok Süreçle Derleme)
ms.date: 02/22/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.MultiProcessorCompilation
helpviewer_keywords:
- -MP compiler option (C++)
- /MP compiler option (C++)
- MP compiler option (C++)
- cl.exe compiler, multi-process build
ms.openlocfilehash: d0a3e50ca75535d505e46c0e454a8e0902b1ffb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562090"
---
# <a name="mp-build-with-multiple-processes"></a>/MP (Birden Çok Süreçle Derleme)

**/MP** seçeneği, komut satırında kaynak dosyalarını derlemek için toplam süreyi azaltabilir. **/MP** seçeneği her ayrı bir işlemde kendisinin, bir veya birden çok kopya oluşturmak derleyicinin neden olur. Ardından bu kopyaları, aynı anda kaynak dosyaları derleyin. Sonuç olarak, kaynak dosyaları oluşturmak için toplam süreyi önemli ölçüde azaltılabilir.

## <a name="syntax"></a>Sözdizimi

> **/MP**[*processMax*]

## <a name="arguments"></a>Arguments

*processMax*<br/>
(İsteğe bağlı) Derleyici oluşturabilirsiniz işlemlerin sayısı.

*ProcessMax* bağımsız değişkeni 1 ile 65536 arasında aralığı gerekir. Aksi halde, derleyici uyarı iletisi yayınlar **D9014**, yoksayar *processMax* bağımsız değişkeni ve en fazla işlem sayısını 1 olduğunu varsayar.

Atlarsanız *processMax* bağımsız değişkeni, derleyici sayısını alır [etkili İşlemci](#effective_processors) işletim sisteminden bilgisayarınızdaki ve her işlemci için bir işlem oluşturur.

## <a name="remarks"></a>Açıklamalar

**/MP** derleyici seçeneği, derleme yaparken birçok dosya derleme süresi önemli ölçüde azaltabilirsiniz. Yapı süresini kısaltmak için derleyici en fazla oluşturur *processMax* kendisinin kopyalar ve aynı zamanda kaynak dosyalarını derlemek için bu kopyaları'i kullanır. **/MP** seçeneği, derlemeleri, ancak bağlama veya bağlama sırasında kod oluşturma için uygulanır. Varsayılan olarak **/MP** seçenek kapalıdır.

Derleme zamanında geliştirme bir bilgisayardaki işlemci sayısını, derleme için dosya sayısını ve g/ç kapasitesi gibi sistem kaynaklarının bağlıdır. Denemeler **/MP** belirli bir projeyi oluşturmak için en iyi ayarını belirlemek üzere seçeneği. Bu kararı vermenize yardımcı olmak daha fazla öneri için bkz. [yönergeleri](#guidelines).

## <a name="incompatible-options-and-language-features"></a>Uyumsuz seçenekler ve dil özellikleri

**/MP** seçeneği, bazı derleyici seçenekleri ve dil özellikleri ile uyumlu değil. Uyumsuz derleyici seçeneği ile kullanırsanız **/MP** seçeneği, derleyicinin uyarı sorunları **D9030** ve yoksayar **/MP** seçeneği. Uyumsuz dil özelliği kullanırsanız, derleyici hata verir [C2813](../../error-messages/compiler-errors-2/compiler-error-c2813.md) sonra sona erer veya uyarı düzeyi seçeneği geçerli derleyici bağlı olarak devam eder.

> [!NOTE]
> Çoğu seçenekleri uyumsuz olduğu izin, eş zamanlı yürütme derleyiciler çıktılarını aynı anda konsola veya belirli bir dosya yazmalısınız. Sonuç olarak, çıktı intermix ve bozuk. Bazı durumlarda, seçenek birleşimi performansı daha da kötüsü hale getirir.

Aşağıdaki tablo, derleyici seçenekleri ve ile uyumsuz dil özelliklerini listeler **/MP** seçeneği:

|Seçeneği veya dil özelliği|Açıklama|
|--------------------------------|-----------------|
|[#import](../../preprocessor/hash-import-directive-cpp.md) önişlemci yönergesi|Bir tür kitaplığındaki tür C++ sınıflarına dönüştürür ve ardından söz konusu sınıfın bir üst bilgi dosyasına yazar.|
|[/E](../../build/reference/e-preprocess-to-stdout.md), [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıktısını standart çıktıya kopyalar (**stdout**).|
|[/Gm](../../build/reference/gm-enable-minimal-rebuild.md)|Bir artımlı yeniden etkinleştirir.|
|[/ showıncludes](../../build/reference/showincludes-list-include-files.md)|Standart hatayı ekleme kodu dosyalarının bir listesini yazar (**stderr**).|
|[/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Önceden derlenmiş üst bilgi dosyasına yazar.|

## <a name="diagnostic-messages"></a>Tanılama iletileri

Uyumlu olmayan bir seçenek veya dil özelliği belirtirseniz **/MP** seçeneği, bir tanılama iletisi alırsınız. Aşağıdaki tabloda, iletileri ve derleyici davranışı listelenmektedir:

|Tanılama iletisi|Açıklama|Derleyici davranışı|
|------------------------|-----------------|-----------------------|
|**C2813**|**#İmport** yönergesi ile uyumlu değil **/MP** seçeneği.|Derleme sürece biten bir [derleyici uyarı düzeyini](../../build/reference/compiler-option-warning-level.md) seçeneği, aksi takdirde belirtir.|
|**D9014**|Geçersiz bir değer için belirtilen *processMax* bağımsız değişken.|Derleyici, geçersiz bir değer yok sayar ve 1 değeri kabul eder.|
|**D9030**|Belirtilen seçeneği ile uyumlu **/MP**.|Derleyicinin yoksaydığı **/MP** seçeneği.|

## <a name="guidelines"></a> Yönergeleri

### <a name="measure-performance"></a>Ölçü performans

Performansını ölçmek için toplam derleme zamanını kullanın. Bir fiziksel saatiyle derleme zamanını ölçebilirsiniz veya derleme başlar ve durur arasındaki farkı hesaplar yazılımları kullanabilirsiniz. Bilgisayarınızda birden çok işlemci varsa, fiziksel bir saat daha doğru sonuçlar yazılım zaman ölçümü daha verimli.

### <a name="effective_processors"></a> Etkili işlemcileri

Bir bilgisayar olarak da bilinen olan bir veya daha fazla sanal işlemci, olabilir *etkili İşlemci*, her biri kendi fiziksel işlemcilerin için. Her fiziksel işlemci, bir veya daha fazla çekirdeğe sahip olabilir ve her bir temel işletim sistemi, hiper iş parçacığı için çekirdek etkinleştirirse, iki sanal işlemciler gibi görünüyor.

Örneğin, bir çekirdek içeren bir fiziksel işlemci varsa olan bir bilgisayarda etkin bir işlemci ve hiper iş parçacığı devre dışı bırakıldı. Buna karşılık, bir bilgisayar, her biri iki çekirdek sahip, iki fiziksel işlemciyi varsa ve hiper iş parçacıklı çekirdekleri sahip sekiz etkili işlemciye sahip. Diğer bir deyişle, (8 etkili işlemci) (2 fiziksel işlemci) = x (fiziksel işlemci başına 2 Çekirdek) x (2 etkin işlemci çekirdeği nedeniyle hiper iş parçacığı başına).

Atlarsanız *processMax* değişkeninde **/MP** seçeneği, derleyicinin işletim sisteminden etkili işlemci sayısını alır ve ardından etkili işlemci başına bir işlem oluşturur. Ancak, derleyicinin hangi işlemin belirli bir işlemci üzerinde yürütür garanti edemez; işletim sistemi, karar verir.

### <a name="number-of-processes"></a>İşlem sayısı

Derleyici kaynak dosyalarını derlemek için kullanacağı işlem sayısını hesaplar. Değer, komut satırında belirttiğiniz kaynak dosya sayısını ve açıkça veya dolaylı olarak belirlediğiniz işlemlerin sayısı daha düşük olduğunu **/MP** seçeneği. Açıkça sağlarsanız maksimum işlem sayısını ayarlayabilirsiniz *processMax* bağımsız değişkeni **/MP** seçeneği. Veya atlarsanız bir bilgisayarda, sayısına eşit etkili işlemcileri için varsayılan, kullanabileceğiniz *processMax* bağımsız değişken.

Örneğin, aşağıdaki komut satırını belirtin varsayalım:

`cl /MP7 a.cpp b.cpp c.cpp d.cpp e.cpp`

Bu durumda, beş kaynak dosyaları ve en fazla yedi işlemden daha düşük olduğundan derleyici beş işlemleri kullanır. Alternatif olarak, bilgisayarınızda iki etkili işlemciye sahip ve aşağıdaki komut satırını belirtin varsayalım:

`cl /MP a.cpp b.cpp c.cpp`

Bu durumda işletim sistemini iki işlemci bildirir; Bu nedenle, derleyici iki işlem ile kendi hesaplamaya kullanır. Sonuç olarak, iki işlem ile üç kaynak dosyaların ve daha düşük olduğundan derleyici derleme iki işlem ile çalıştırır.

### <a name="source-files-and-build-order"></a>Kaynak dosyaları ve derleme sırası

Kaynak dosyaları, komut satırında göründükleri sırayla derlenmeyebilir. Derleyici, derleyici bir kopyasını içeren işlemler kümesi oluşturur, ancak her bir işlemi yürüttüğünde işletim sistemi zamanlar. Sonuç olarak, kaynak dosyaları belirli bir sırada derlenecek garanti edemez.

Bir işlem bu derleme kullanılabilir olduğunda, bir kaynak dosyası derlenir. Daha fazla dosyalardan işlemler varsa, ilk dosya kümesini kullanılabilir işlemler tarafından derlenir. Bir işlem önceki dosya işleme tamamlandıktan ve kalan dosyaları biri üzerinde çalışmak için uygun olduğunda kalan dosyaları işlenir.

Aynı kaynak dosyası birden çok kez bir komut satırında belirtmeyin. Bir aracı otomatik olarak oluşturursa Bu, örneğin, durum ortaya çıkabilir bir [derleme görevleri dosyası](../../build/contents-of-a-makefile.md) bağımlılık bilgileri projesinde dayanır. Siz belirtmezseniz **/MP** seçeneği, derleyicinin dosyaların listesini sıralı olarak işlediğinden ve her oluşumu dosyanın yeniden derler. Ancak, belirtirseniz **/MP** seçeneği, farklı derleyiciler aynı anda aynı dosyanın derleme. Sonuç olarak, farklı derleyiciler aynı anda aynı çıktı dosyasına yazma dener. Bir derleyici özel çıkış dosyası yazma erişim kazanmak ve başarılı ve diğer derleyiciler bir dosya erişim hatası ile başarısız olur.

### <a name="using-type-libraries-import"></a>Tür kitaplıklarını (#import) kullanma

Derleyici kullanımını desteklemiyor [#import](../../preprocessor/hash-import-directive-cpp.md) yönergesi ile **/MP** geçin. Mümkünse, bu sorunu çözmek için aşağıdaki adımları izleyin:

- Tüm taşımak `#import` yönergeleri, çeşitli kaynak dosyaları için bir veya daha fazla dosya ve ardından bu dosyalar olmadan derleme **/MP** seçeneği. Oluşturulan üst bilgi dosyaları sonucudur.

- Kalan içindeki kaynak dosyaları, ekleme [#include](../../preprocessor/hash-include-directive-c-cpp.md) oluşturulan üst bilgileri belirtin ve ardından kalan derleme yönergeleri kaynak dosyaları kullanarak **/MP** seçeneği.

### <a name="visual-studio-project-settings"></a>Visual Studio Proje ayarları

#### <a name="the-msbuildexe-tool"></a>MSBUILD.exe aracının

Visual Studio kullanan [MSBuild.exe](/visualstudio/msbuild/msbuild-reference) çözümler ve projeler oluşturmak için aracı. **/Maxcpucount:**_numarası_ (veya **/m:**_numarası_) MSBuild.exe aracının komut satırı seçeneği, birden çok proje oluşturabilirsiniz aynı anda. Ve **/MP** derleyici seçeneği, aynı anda birden çok derleme birimi oluşturabilirsiniz. Uygulamanız için uygun durumda, çözümünüzün derleme süresi veya her ikisini kullanarak geliştirmek **/MP** ve **/maxcpucount**.

Derleme süresi çözümünüzün kısmen derlemeyi gerçekleştirmek işlemlerin sayısına bağlıdır. *Numarası* bağımsız değişkeni [/maxcpucount](/visualstudio/msbuild/msbuild-command-line-reference) MSBuild seçeneği projeleri aynı anda en fazla sayısını belirtir. Benzer şekilde, *processMax* bağımsız değişkeni **/MP** derleyici seçeneği, aynı anda oluşturmak için derleme biriminden maksimum sayısını belirtir. Varsa **/maxcpucount** seçeneği belirtir *P* projeleri ve **/MP** seçeneği belirtir *C* işler, en fazla *P*  x *C* işlemler aynı anda yürütme.

MSBuild kullanılacak karar yönelik yönerge veya **/MP** teknoloji aşağıdaki gibidir:

- Birçok projeleriyle her projedeki bazı dosyalar varsa, MSBuild Aracı'nı kullanın.

- Her proje içinde çok fazla dosya içeren birkaç projeler varsa, kullanmak **/MP** seçeneği.

- Projeleri ve dosyaları proje başına sayısını dengeli hem MSBuild kullanın ve **/MP**. Başlangıçta ayarladığınız **/maxcpucount** derleme proje sayısı seçeneğine ve **/MP** bilgisayarınızda işlemci sayısını seçeneği. Performansı ölçme ve en iyi sonuçları elde etmek üzere ayarlarınızı yapın. Toplam derleme süresiyle memnun olana kadar bu döngüyü tekrarlayın.

#### <a name="the-gm-compiler-option"></a>/Gm derleyici seçeneği

Varsayılan olarak, bir projeyi derleme etkinleştirir **/GM derlemeyi** derleyici seçeneği (artımlı derlemeleri) hata ayıklama yapıları ve sürüm için yapıların devre dışı bırakır. Bu nedenle, **/MP** derleyici seçeneği otomatik olarak devre dışıdır hata ayıklama yapılarında varsayılan ile çakıştığı için **/GM derlemeyi** derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[#import yönergesi](../../preprocessor/hash-import-directive-cpp.md)<br/>
[Komut Satırı Başvurusu](/visualstudio/msbuild/msbuild-command-line-reference)<br/>
[/ZF (Daha hızlı PDB oluşturma)](zf.md)<br/>
