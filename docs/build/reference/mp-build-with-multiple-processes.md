---
title: "-MP (birden çok süreçle derleme) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCCLCompilerTool.MultiProcessorCompilation
dev_langs: C++
helpviewer_keywords:
- -MP compiler option (C++)
- /MP compiler option (C++)
- MP compiler option (C++)
- cl.exe compiler, multi-process build
ms.assetid: a932b14a-74fe-4b45-84e4-6bf53f0f5e07
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ad914a9aa5e7207d1b39e4917a965d755564848
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mp-build-with-multiple-processes"></a>/MP (Birden Çok Süreçle Derleme)
**/MP** seçeneği, komut satırında kaynak dosyalarını derlemek için toplam süreyi azaltabilir. **/MP** seçeneği bir veya daha fazla kopyalarını, her ayrı bir işlemde oluşturmak derleyicinin neden olur. Daha sonra bu kopya kaynak dosyaları aynı anda derleyin. Sonuç olarak, kaynak dosyaları derleme için toplam süreyi önemli ölçüde azaltılabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/MP[processMax]  
```  
  
## <a name="arguments"></a>Arguments  
 `processMax`  
 (İsteğe bağlı) Derleyici oluşturabilirsiniz işlemlerin sayısı.  
  
 `processMax` Bağımsız değişkeni 1 ile 65536 aralığı gerekir. Aksi takdirde, uyarı iletisi derleyici sorunları `D9014`, yoksayar `processMax` bağımsız değişkeni ve en yüksek işlem sayısı 1 olduğunu varsayar.  
  
 Atlarsanız `processMax` bağımsız değişkeni, derleyici alır sayısını [etkili işlemciler](#effective_processors) bilgisayarınızın işletim sisteminden ve her işlemci için bir işlem oluşturur.  
  
## <a name="remarks"></a>Açıklamalar  
 **/MP** derleyici seçeneği derleme zaman çok sayıda dosya derleme zamanı önemli ölçüde azaltabilir. Derleme süresini kısaltmak için derleyici kadar oluşturur `processMax` kendisinin kopyalar ve aynı anda Kaynak dosyalarınız derlemek için bu kopyaları kullanır. **/MP** derlemeleri, ancak bağlama veya bağlama zamanı kodu oluşturma seçeneğini uygular. Varsayılan olarak **/MP** seçeneği kapalıdır.  
  
 Derleme zamanında geliştirme bir bilgisayar işlemci sayısını, derlemek için dosya sayısını ve g/ç kapasitesi gibi sistem kaynaklarının kullanılabilirliği bağlıdır. Deneme **/MP** belirli bir proje oluşturmak için en iyi ayarı belirlemek için seçeneği. Bu kararı vermenize yardımcı olacak öneriler için bkz: [yönergeleri](#guidelines).  
  
## <a name="incompatible-options-and-language-features"></a>Uyumsuz seçenekler ve dil özellikleri  
 **/MP** seçeneği, bazı derleyici seçenekleri ve dil özellikleri ile uyumlu değil. Uyumsuz derleyici seçeneği ile kullanırsanız **/MP** seçeneği, derleyici sorunları uyarı `D9030` ve yoksayar **/MP** seçeneği. Bir uyumsuz dil özelliğini kullanırsanız, derleyici hatası sorunları `C2813` sonra sona erer veya düzey seçeneği uyarı geçerli derleyici bağlı olarak devam eder.  
  
> [!NOTE]
>  Çoğu seçenek izin, eş zamanlı yürütme derleyicileri çıktılarını aynı anda konsol veya belirli bir dosyaya yazmak istediğiniz olduğundan uyumlu değil. Sonuç olarak, çıktı intermix ve bozuk. Bazı durumlarda, seçenekleri birleşimini performansı daha da kötüsü hale getirir.  
  
 Derleyici seçenekleri ve ile uyumlu dil özellikler aşağıdaki tabloda listelenmektedir **/MP** seçeneği:  
  
|Seçenek veya dil özelliği|Açıklama|  
|--------------------------------|-----------------|  
|[#import](../../preprocessor/hash-import-directive-cpp.md) önişlemci yönergesi|C++ sınıfları bir tür kitaplığı türlerinde dönüştürür ve ardından bu sınıfların bir üstbilgi dosyasına yazar.|  
|[/E](../../build/reference/e-preprocess-to-stdout.md), [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıktısı standart çıktıya kopyalar (**stdout**).|  
|[/GM derlemeyi](../../build/reference/gm-enable-minimal-rebuild.md)|Bir artımlı yeniden etkinleştirir.|  
|[/ showıncludes](../../build/reference/showincludes-list-include-files.md)|Standart hatayı INCLUDE dosyaların listesini yazar (**stderr**).|  
|[/Yc](../../build/reference/yc-create-precompiled-header-file.md)|Önceden derlenmiş başlık dosyası yazar.|  
  
## <a name="diagnostic-messages"></a>Tanılama iletileri  
 Uyumlu olmayan bir seçenek veya dil özelliğini belirtirseniz, **/MP** seçeneği, bir tanılama iletisi alırsınız. Aşağıdaki tabloda, iletileri ve derleyici davranışı listelenmektedir:  
  
|Tanılama iletisi|Açıklama|Derleyici davranışı|  
|------------------------|-----------------|-----------------------|  
|`C2813`|**#İmport** yönergesi ile uyumlu değil **/MP** seçeneği.|Derleme sürece biten bir [derleyici uyarı düzeyi](../../build/reference/compiler-option-warning-level.md) seçeneği, aksi takdirde belirtir.|  
|`D9014`|Geçersiz bir değer için belirtilen `processMax` bağımsız değişkeni.|Derleyici geçersiz değer yoksayar ve 1 değeri kabul eder.|  
|`D9030`|Belirtilen seçeneği ile uyumlu değil **/MP**.|Derleyici yoksayar **/MP** seçeneği.|  
  
##  <a name="guidelines"></a>Yönergeleri  
  
### <a name="measure-performance"></a>Ölçü performansı  
 Toplam derleme zamanında performansını ölçmek için kullanın. Derleme zamanında fiziksel saatiyle ölçebilirsiniz veya yapı başlar ve durdurduğunda arasındaki farkı hesaplar yazılımları kullanabilirsiniz. Bilgisayarınızda birden çok işlemci varsa, fiziksel bir saat daha doğru bir yazılım zaman ölçümü daha sonuçlar.  
  
###  <a name="effective_processors"></a>Etkili işlemcileri  
 Bir bilgisayar olarak da bilinen etkili işlemciler olan bir veya daha fazla sanal işlemci, her fiziksel işlemcilerin sahip olabilir. Her fiziksel işlemci bir veya birden çok çekirdeğe sahip olabilir ve işletim sistemi, hiper iş parçacığı için çekirdek etkinleştirirse her çekirdek iki sanal işlemci gibi görünüyor.  
  
 Örneğin, bir çekirdek sahip bir fiziksel işlemci varsa bir bilgisayarı bir etkili işlemci vardır ve hiper iş parçacığı devre dışıdır. Buna karşılık, bir bilgisayar, her biri iki çekirdeğe sahip, iki fiziksel işlemci sahiptir ve tüm çekirdeklerin etkin hiper iş parçacığı varsa sekiz etkili işlemciye sahip. Diğer bir deyişle, (8 etkili işlemci) (2 fiziksel işlemciler için) = x (fiziksel işlemci başına 2 Çekirdek) x (çekirdek nedeniyle hiper iş parçacığı başına 2 etkili işlemci).  
  
 Atlarsanız `processMax` değişkeninde **/MP** seçeneği, derleyici işletim sisteminden etkili işlemci sayısını alır ve ardından etkili işlemci başına bir işlem oluşturur. Ancak, derleyici, belirli bir işlemci, hangi işlemin yürütür garanti edemez; işletim sistemi kararı yapar.  
  
### <a name="number-of-processes"></a>İşlem sayısı  
 Derleyici kaynak dosyalarını derlemek için kullanacağı işlemlerin sayısı hesaplar. Değer komut satırında belirttiğiniz kaynak dosya sayısı ile açıkça veya örtük belirtin işlem sayısını ve daha düşük olduğunu **/MP** seçeneği. Sağlarsanız, en yüksek işlem sayısı açıkça ayarlayabilirsiniz `processMax` bağımsız değişkeni **/MP** seçeneği. Veya atlarsanız bir bilgisayarda, etkin işlemci sayısına eşittir varsayılan olarak kullanabileceğiniz `processMax` bağımsız değişkeni.  
  
 Örneğin, aşağıdaki komut satırını belirtin varsayın:  
  
 `cl /MP7 a.cpp b.cpp c.cpp d.cpp e.cpp`  
  
 Bu durumda, beş kaynak dosyaları ve yedi işlemlerin en küçük olmadığından derleyici beş işlemleri kullanır. Alternatif olarak, iki etkili işlemci bilgisayarınızda yüklüyse ve aşağıdaki komut satırını belirtin varsayın:  
  
 `cl /MP a.cpp b.cpp c.cpp`  
  
 Bu durumda işletim sistemini iki işlemci raporları; Bu nedenle, derleyici, hesaplama iki işlem kullanır. Sonuç olarak, iki işlem ve üç kaynak dosyaları daha az olduğu için derleyici iki süreçle derleme yürütülür.  
  
### <a name="source-files-and-build-order"></a>Kaynak dosyalarını ve derleme sırası  
 Kaynak dosyaları komut satırında göründükleri sırada derlenmemiş. Derleyici derleyici kopyalarını içeren işlemleri kümesi oluştursa, her bir işlemi yürüttüğünde işletim sistemi zamanlar. Sonuç olarak, kaynak dosyaları belirli bir sırada derlenecek garanti edemez.  
  
 Bir kaynak dosyası bir işlem, derlemek kullanılabilir duruma geldiğinde derlenir. İşlemler'den daha fazla dosya varsa, dosyaların ilk kümesi kullanılabilir işlemler tarafından derlenir. Bir işlem önceki dosya işleme tamamlandıktan ve kalan dosyaları biri üzerinde çalışmak için uygun olduğunda kalan dosyaları işlenir.  
  
 Aynı kaynak dosyada birden çok kez bir komut satırı belirtmeyin. Bir aracı otomatik olarak oluşturur, bu, örneğin, oluşabilecek bir [derleme görevleri dosyası](../../build/contents-of-a-makefile.md) bağımlılık bilgi projesinde dayanır. Belirtmezseniz, **/MP** seçeneği, derleyici dosyaların listesini sırayla işler ve her oluşumu dosyanın yeniden derler. Ancak, belirtirseniz **/MP** seçeneği, farklı derleyicileri aynı anda aynı dosyanın derleme. Sonuç olarak, farklı derleyicileri aynı anda aynı çıktı dosyasına yazma dener. Bir derleme çıktı dosyası için özel yazma erişim edinmeli ve başarılı ve diğer derleyiciler bir dosya erişim hatası ile başarısız olur.  
  
### <a name="using-type-libraries-import"></a>Tür kitaplıklarını (#import) kullanma  
 Derleyici kullanımını desteklemez [#import](../../preprocessor/hash-import-directive-cpp.md) ile yönerge **/MP** geçin. Mümkünse, bu sorunu geçici olarak çözmek için aşağıdaki adımları izleyin:  
  
-   Tüm taşımak `#import` yönergeleri, çeşitli kaynak dosyaları için bir veya daha fazla dosya ve bu dosyaları olmadan derleme **/MP** seçeneği. Sonucu oluşturulan üstbilgi dosyaları kümesidir.  
  
-   Geriye kalan içinde kaynak dosyaları, Ekle [#include](../../preprocessor/hash-include-directive-c-cpp.md) oluşturulan üstbilgileri belirtin ve ardından, kalan derleme yönergeleri kaynak dosyaları kullanarak **/MP** seçeneği.  
  
### <a name="visual-studio-project-settings"></a>Visual Studio Proje ayarları  
  
#### <a name="the-msbuildexe-tool"></a>MSBUILD.exe aracı  
 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]kullanan [MSBuild.exe](/visualstudio/msbuild/msbuild-reference) çözümler ve projeler derleme aracı. **/Maxcpucount:** `number` (veya **/m:**`number`) MSBuild.exe aracı komut satırı seçeneği, aynı anda birden çok proje oluşturabilir. Ve **/MP** derleyici seçeneği, aynı anda birden çok derleme biriminden oluşturabilir. Uygulamanız için uygun olup olmadığını veya ikisini birden kullanarak çözümünüzün yapı süresini kısaltmak **/MP** ve **/maxcpucount**.  
  
 Derleme zamanı çözümünüzün kısmen yapı gerçekleştirmek işlemleri sayısına bağlıdır. `number` Bağımsız değişkeni [/maxcpucount](/visualstudio/msbuild/msbuild-command-line-reference) MSBuild seçeneği, aynı anda oluşturmak için projeleri üst sınırını belirtir. Benzer şekilde, `processMax` bağımsız değişkeni **/MP** derleyici seçeneği, aynı anda oluşturmak için derleme birimleri en fazla sayısını belirtir. Varsa **/maxcpucount** seçeneği belirtir *P* projeleri ve **/MP** seçeneği belirtir *C* işler, en fazla *P* x*C* işlemler aynı anda yürütün.  
  
 Mı kullanılacağına karar verme için kılavuz `MSBuild` veya **/MP** teknolojisi aşağıdaki gibidir:  
  
-   Her proje birkaç dosyaları ile çok sayıda proje varsa `MSBuild` aracı.  
  
-   Her proje içinde çok sayıda dosya birkaç projelerle varsa **/MP** seçeneği.  
  
-   Proje ve proje başına dosyalarının sayısını dengeli varsa, her ikisini de kullanmanız `MSBuild` ve **/MP**. Başlangıçta ayarlamak **/maxcpucount** derleme seçeneği projeleri sayısına ve **/MP** bilgisayarınızdaki işlemci sayısı için seçeneği. Performansı ölçme ve en iyi sonuçlar için ayarlarınızı yapın. Toplam derleme süresiyle memnun olana kadar bu döngü yineleyin.  
  
#### <a name="the-gm-compiler-option"></a>/Gm derleyici seçeneği  
 Varsayılan olarak, bir projeyi derleme etkinleştirir **/GM derlemeyi** derleyici seçeneği (artımlı derlemeler) hata ayıklama yapıları ve onu yayımı için derlemeleri devre dışı bırakır. Bu nedenle, **/MP** derleyici seçeneği otomatik olarak devre dışıdır hata ayıklama derlemelerinde varsayılan çakıştığından **/GM derlemeyi** derleyici seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md)   
 [Komut Satırı Başvurusu](/visualstudio/msbuild/msbuild-command-line-reference)