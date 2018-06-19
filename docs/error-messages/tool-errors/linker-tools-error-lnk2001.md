---
title: Bağlayıcı araçları hatası LNK2001 | Microsoft Docs
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2001
dev_langs:
- C++
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78dc0c0a3a030ecb88d7138484e2c64e145f69ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301788"
---
# <a name="linker-tools-error-lnk2001"></a>Bağlayıcı Araçları Hatası LNK2001
Çözümlenmemiş dış simgesi "*simgesi*"  
  
Derlenmiş kod bir başvuru veya çağrı yapar *simgesi*, ancak bu simge, herhangi bir bağlayıcıya belirtilen nesne dosyaları ve kitaplıkları tanımlanmamıştır.  
  
Bu hata iletisini önemli hatası tarafından izlenir [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). LNK1120 hatayı düzeltmek için tüm LNK2001 ve LNK2019 hataları düzeltmeniz gerekir.  
  
## <a name="possible-causes"></a>Olası nedenler  
  
Bu hatayı almak için birçok yolu vardır, ancak bunların tümünün bir işlevi veya bağlayıcı olamaz değişkeni bir başvuru içeren *gidermek*, veya için bir tanım bulunamıyor. Bir simge olmadığında derleyici tanımlayabilirsiniz *bildirilen*, ancak ne zaman onu değil *tanımlanan*, tanımı farklı bir kaynak dosya ya da kitaplık olabileceğinden. Bir simge başvurulan ancak hiç tanımlanmış, bağlayıcı bir hata oluşturur.  
  
### <a name="coding-issues"></a>Kodlama sorunları  
  
Bu hata, kaynak kodu veya modül-tanımlama (.def) eşleşmeyen durumda neden olabilir dosya. Örneğin, bir değişken adı `var1` bir C++'da kaynak dosyası ve olarak erişmeyi deneyin `VAR1` başka bir programda, bu hata oluşturulur. Bu sorunu gidermek için kullanım tutarlı bir şekilde yazıldığından ve adlarını ortası.  
  
Kullanan bir projede bu hata oluşabilir [işlev satır içi kullanım](../../error-messages/tool-errors/function-inlining-problems.md) kaynak dosyası yerine bir üstbilgi dosyası işlevleri tanımlarsanız. Satır içi işlevler bunları tanımlayan kaynak dosya dışında görülemeyen. Bu sorunu gidermek için burada bildirilen üstbilgilerinde satır içi işlevler tanımlayın.  
  
Kullanmadan bir C++ programı C işlevini çağırırsanız bu hataya neden bir `extern "C"` C işlevi bildirimi. Derleyici C ve C++ kodu için farklı iç simge adlandırma kuralları kullanır ve bu simgeleri çözülürken bağlayıcı arar iç simge adıdır. Bu sorunu gidermek için kullanmak bir `extern "C"` tüm bildirimleri için bu simgeleri C iç adlandırma kuralı kullanmak için derleyicisi neden C++ kodunuzda kullanılan C işlevlerin çevresinde sarmalayıcı. Derleyici Seçenekleri [/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) ve [tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) dosyalarını C++ veya C olarak sırasıyla bağımsız olarak dosya adı uzantısı derlemek derleyici neden. Bu seçenekler, iç işlev adları beklediğinizden farklı neden olabilir.  
  
Bu hata işlevleri veya dış bağlantı yok veri başvuru girişimi neden olabilir. C++, satır içi işlevler ve `const` verilere sahip iç bağlantı olarak açıkça belirtilmediği sürece `extern`. Bu sorunu gidermek için açık kullanmak `extern` simgeleri bildirimlerinde başvurduğu tanımlayan kaynak dosyası dışında.  
  
Bu hatanın nedeni bir [eksik işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md) tanımı. Bu hata bildirme, ancak yok tanımlamak, değişkenler, İşlevler veya sınıfları kodunuzda yaygındır. Derleyici, yalnızca bir işlev prototipi gerekir veya `extern` hata ancak bağlayıcı olmayan nesne dosyası oluşturmak için değişken bildirimi olamaz çözmek işlevi çağrısı veya değişkeni başvurusu işlevi kod veya değişken boşluk olduğundan ayrılmış. Bu sorunu gidermek için her başvurulan işlev ve değişken tam olarak bir kaynak dosya ya da, bağlantının içerdiği kitaplığı tanımlandığından emin olun.  
  
Bu hata dönüş ve parametre türleri veya işlev tanımı de eşleşmiyor çağırma kurallarını kullanan bir işlev çağrısı neden olabilir. C++ nesne dosyalarında [ad decoration](../../error-messages/tool-errors/name-decoration.md) ne zaman eşleşecek şekilde sembol yapılan çağrılar olarak kullanılan son düzenlenmiş işlevi adı çağırma, sınıf veya ad alanı kapsamı ve bir işlevin dönüş ve parametre türleri birleştirir diğer nesne dosyaları işlevinden çözümlenir. Bu sorunu gidermek için bildirim, tanım ve tüm işlev çağrıları aynı kapsamları, türleri ve çağırma kuralları kullandığınızdan emin olun.  
  
C++ kodu bu hata bir sınıf tanımı'nda bir işlev prototipi içerir, ancak başarısız olmasından kaynaklanabilir [uygulama dahil](../../error-messages/tool-errors/missing-function-body-or-variable.md) işlevinin ve ardından çağırın. Bu sorunu gidermek için bir sınıf üyeleri olarak bildirilen tüm adlı için bir tanım sağladığınızdan emin olun.  
  
Bu hata bir soyut taban sınıfından saf sanal işlevi çağırma girişimi neden olabilir. Saf sanal işlevi hiçbir taban sınıfı uygulama var. Bu sorunu gidermek için tüm sanal işlevler adlı uygulanan emin olun.  
  
Bir işlev içinde bildirilen bir değişken kullanmak deneyerek bu hataya neden olabilir ([yerel bir değişken](../../error-messages/tool-errors/automatic-function-scope-variables.md)) Bu işlev kapsamı dışında. Bu sorunu gidermek için kapsamında değil değişkeni başvurusunu kaldırın veya daha yüksek bir kapsama değişkeni taşıyın.  
  
CRT başlatma kodunu gerekli olduğunu belirten bir ileti oluşturan bir ATL projesinde sürümü oluştururken bu hata oluşabilir. Bu sorunu gidermek için aşağıdakilerden birini yapın  
  
-   Kaldırma `_ATL_MIN_CRT` dahil edilecek CRT başlatma kodunu izin vermek için önişlemci listesinden tanımlar. Bkz: [genel özellik sayfası (Proje)](../../ide/general-property-page-project.md) daha fazla bilgi için.  
  
-   Mümkünse, CRT başlatma kodunu gerektiren CRT işlevleri çağrıları kaldırın. Bunun yerine, Win32 eşdeğerlerine kullanın. Örneğin, `lstrcmp` yerine `strcmp`. CRT başlatma kodunu gerektiren bilinen bazı dize ve kayan nokta işlevleri işlevlerdir.  
  
### <a name="compilation-and-link-issues"></a>Derleme ve bağlantı sorunları  
  
Proje bir kitaplığına bir başvuru eksik olduğunda bu hata oluşabilir (. LIB) veya nesne (. OBJ) dosyası. Bu sorunu düzeltmek için gerekli kitaplık ya da nesne dosyası başvuru projenize ekleyin. Daha fazla bilgi için bkz: [bağlayıcı girişi olarak .lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md).  
  
Kullanırsanız, bu hata oluşabilir [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) veya [/Zl](../../build/reference/zl-omit-default-library-name.md) seçenekleri. Bu seçenekler belirttiğinizde, gerekli kodu içeren kitaplıkları bunları açıkça eklemiş sürece projeye bağlı değildir. Bu sorunu gidermek için açıkça bağlantı komut satırında kullandığınız tüm kitaplıkları içerir. Açıkça bu seçenekler kullandığınızda birçok eksik CRT veya standart kitaplığı işlev adları görürseniz, bağlantıyı CRT ve standart kitaplığı DLL'leri veya kitaplık dosyalarını içerir.  

Kullanarak derleme yaparsanız **/CLR** seçeneği, .cctor eksik başvuru olabilir. Bu sorunu gidermek için bkz: [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md) daha fazla bilgi için.  
  
Bir uygulamanın hata ayıklama sürümü oluştururken sürüm modu kitaplıklara bağlarsanız, bu hata oluşabilir. Benzer şekilde, seçenekleri kullanırsanız **/MTd** veya **/MDd** veya tanımlayın `_DEBUG` ve yayın kitaplıklara Bağla, diğer sorunları arasında birçok olası çözümlenmemiş externals beklemelisiniz. Hata ayıklama kitaplıklarla sürüm modu yapı bağlama de benzer sorunlara neden olur. Bu sorunu düzeltmek için hata ayıklama derlemelerinde hata ayıklama kitaplıkları kullanabilirsiniz ve perakende, perakende kitaplıklarında derlemeler emin olun.  
  
Kodunuzu bir kitaplık bir sürümünden bir simgeye başvuruyor, ancak bağlayıcı kitaplığa farklı bir sürümünü sağlayın bu hata oluşabilir. Genellikle, nesne dosyaları ya da farklı derleyici sürümler için yerleşik kitaplıkları karıştıramazsınız. Yeni bir sürümünde sevk kitaplıkları önceki sürümleri ve tam tersini içinde yer alan kitaplıklarında bulunamıyor simgeleri içerebilir. Bu sorunu gidermek için tüm nesne dosyaları ve kitaplıkları derleyici aynı sürümü ile bunları birlikte bağlamadan önce oluşturun.  
  
-  Araçlar &#124; seçenekleri &#124; projeleri &#124; kitaplık dosyaları seçimi altında VC ++ dizinleri iletişim kutusu Kitaplığı arama sırası değiştirmenize olanak sağlar. Projenin özellik sayfaları iletişim kutusu bağlayıcı klasöründe, güncel yollarını içerebilir.  
  
-  Bu sorun, yeni bir SDK (belki farklı bir konuma) yüklendiğinde ve arama sırasını yeni konumunu gösterecek şekilde güncelleştirilmez görünebilir. Normalde, yeni bir SDK yolun yerleştirileceği lib dizinleri varsayılan Visual C++ konumu önünde ve içerir. Ayrıca, katıştırılmış yollarını içeren bir proje hala geçerlidir, ancak farklı bir konuma yüklenen yeni sürümü tarafından eklenen yeni işlevsellik için güncel eski yolları işaret edebilir.  
  
-   Komut satırında yapı ve ortam değişkenlerini oluşturduysanız, Araçlar, kitaplıklar ve başlık dosyaları yollara tutarlı bir sürüme Git doğrulayın. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
  
Şu an için bir standart olan [C++ adlandırma](../../error-messages/tool-errors/name-decoration.md) derleyici satıcılar veya bile bir derleyici farklı sürümleri arasında. Bu nedenle, diğer derleyicileri ile derlenen nesne dosyaları bağlama değil aynı adlandırma şeması oluşturabilir ve hatası LNK2001 neden olur.  
  
[Karıştırma satır içi ve dışı satır içi derleme seçenekleri](../../error-messages/tool-errors/function-inlining-problems.md) farklı modülleri LNK2001 neden olabilir. C++ Kitaplığı işlev satır içi kullanım açık ile oluşturulup oluşturulmadığını (**/Ob1** veya **/Ob2**) ancak işlevleri açıklayan ilgili üstbilgi dosyası satır içi kullanım kapalı (hiçbir `inline` anahtar sözcüğü), bu hata oluşur. Bu sorunu gidermek için işlevleri tanımlama `inline` üstbilgi dosyasında diğer kaynak dosyaları içerir.  
  
Kullanırsanız `#pragma inline_depth` derleyici yönergesi emin olduğunuz bir [değeri 2 veya daha büyük kümesinin](../../error-messages/tool-errors/function-inlining-problems.md)ve ayrıca kullandığınızdan emin olun [/Ob1](../../build/reference/ob-inline-function-expansion.md) veya [/Ob2](../../build/reference/ob-inline-function-expansion.md) derleyici seçeneği.  
  
BAĞLANTIYI unutursanız, bu hata oluşabilir yalnızca kaynak DLL oluşturduğunuzda /NOENTRY seçeneği. Bu sorunu gidermek için /NOENTRY seçeneğini bağlantı komutuna ekleyin.  
  
Projenizde yanlış /SUBSYSTEM veya/Entry ayarları kullanırsanız, bu hata oluşabilir. Bir konsol uygulaması yazma ve /SUBSYSTEM:WINDOWS belirtirseniz, örneğin, çözülmemiş bir dış hata için oluşturulan `WinMain`. Bu sorunu gidermek için proje türü seçenekleri eşleştiğinden emin olun. Bu seçenekler ve giriş noktaları hakkında daha fazla bilgi için bkz: [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) ve [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçenekleri.  
  
### <a name="exported-symbol-issues"></a>Dışarı aktarılan simgesi sorunları  
  
Bu hata, bir .def dosyasında listelenen verme bulunamadı oluşur. Yok, yanlış yazılmış veya donatılmış C++ adları kullanır olmasından kaynaklanabilir. Düzenlenmiş adlar .def dosyası almaz. Bu sorunu gidermek için gereksiz dışarı kaldırın ve kullanmak `extern "C"` dışarı aktarılan sembolleri bildirimleri.  
  
## <a name="what-is-an-unresolved-external-symbol"></a>Çözülmemiş bir dış sembolü nedir?  
  
A *simgesi* bir işlevi veya dahili bir derlenmiş nesne dosyası veya kitaplığı tarafından kullanılan genel değişkeni addır. Bir simge *tanımlanan* dosyasında işlev gövdesi için derlenmiş kod nereye yerleştirilir burada depolama ayrılır genel değişkeni ya da bir işlev nesnesi. Bir *dış simgesi* bir simge o *başvurulan*, diğer bir deyişle, kullanılan veya bir nesne dosyasında çağrıldı, ancak farklı bir kitaplık veya nesne dosyasında tanımlanmış. Bir *simgesi dışarı* nesne dosyası veya tanımlayan kitaplığı tarafından genel olarak kullanılabilir hale getirileceğini biridir. Bağlayıcı gerekir *gidermek*, veya eşleşen tanımı, bir uygulama veya DLL'e bağlandığında bir nesne dosyası tarafından başvurulan her dış simgesi bulunamıyor. Bir dış sembolü eşleşen bir dışarı aktarılan simge bağlantılı dosyalardan birini bularak çözümlenemiyor olduğunda bağlayıcı bir hata oluşturur.    
  
## <a name="use-the-decorated-name-to-find-the-error"></a>Düzenlenmiş adı hata bulmak için kullanın
  
C++ derleyicisi ve bağlayıcı kullanımı [Adlandır](../../error-messages/tool-errors/name-decoration.md), olarak da bilinen *ad bozma*, bir değişken türü veya dönüş türü, parametre türleri, kapsam ve arama hakkında ek bilgi kodlamak için sembol adını işlevinde kuralı. Bağlayıcı dış simgeleri çözümlemek için arar sembol adını bu düzenlenmiş adıdır.  
  
Ek bilgi sembol adını parçası haline gelir olduğundan, bir işlev veya değişken bildirimi tam olarak işlev veya değişken tanımını eşleşmiyor, bir bağlantı hatası ortaya çıkabilir. Farklı derleyici bayrakları kaynak dosyalarını derlerken kullanılıyorsa, aynı üstbilgi dosyası çağıran kodu ve tanımlayıcı kod içinde kullanılan olsa bile bu durum oluşabilir. Örneğin, kodunuzu kullanmak için derlenmiş ise, bu hatayı alabilirsiniz `__vectorcall` çağırma, ancak bağlantı varsayılan kullanarak aramak üzere istemciler bekliyor bir kitaplığı `__cdecl` veya `__fastcall` çağırma. Çağırma kurallarını farklı olduğundan bu durumda, simgeler ile eşleşmiyor.   
  
Bu tür bir hata nedenini bulmanıza yardımcı olmak için bağlayıcı hata iletisi, her iki "kolay adı," kaynak kodu ve düzenlenmiş adını (parantez içinde) çözümlenmemiş dış sembol için kullanılan adını gösterir. Düzenlenmiş diğer adları ile karşılaştırmak için düzenlenmiş adı Çevir bilmenize gerek yoktur. Beklenen simge adı ve gerçek sembol adını Karşılaştırılacak derleyicisi ile birlikte komut satırı araçlarını kullanabilirsiniz:  

-   [/EXPORTS](../../build/reference/dash-exports.md) ve [/SYMBOLS](../../build/reference/symbols.md) DUMPBIN komut satırı aracı seçenekleri hangi simgeleri .dll ve nesne veya kitaplık dosyalarınızda tanımlanan keşfetmenize yardımcı olabilir. Bu, dışa aktarılan düzenlenmiş bağlayıcı arar adları adları eşleşme donatılmış olduğunu doğrulamak için kullanabilirsiniz.  
  
Bazı durumlarda, bağlayıcı, yalnızca bir simge için düzenlenmiş ad bildirebilirsiniz. Düzenlenmiş adının ve form almak için UNDNAME komut satırı aracını kullanabilirsiniz.  
  
## <a name="additional-resources"></a>Ek kaynaklar  
  
Yığın taşması soru LNK2001 için olası nedenler ve çözümler hakkında daha fazla bilgi için bkz: [tanımsız başvuru/çözümlenmemiş dış simgesi hata nedir ve nasıl ı düzelt?](http://stackoverflow.com/q/12573816/2002113).  

