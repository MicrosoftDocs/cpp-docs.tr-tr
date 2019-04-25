---
title: Bağlayıcı Araçları Hatası LNK2001
ms.date: 05/17/2017
f1_keywords:
- LNK2001
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
ms.openlocfilehash: 824fa9108e6322b1bcf77d6c28c7fb843b743833
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161023"
---
# <a name="linker-tools-error-lnk2001"></a>Bağlayıcı Araçları Hatası LNK2001

Çözümlenmemiş dış sembol "*sembol*"

Derlenmiş kod başvurusu veya çağrı yapar *sembol*, ancak herhangi bir bağlayıcıya belirtilen nesne dosyaları ve kitaplıkları sembol tanımlı değil.

Bu hata iletisini önemli hata tarafından izlenir [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Tüm LNK2001 ve LNK2019 LNK1120 hatayı düzeltmek için hataları düzeltmeniz gerekir.

## <a name="possible-causes"></a>Olası nedenler

Bu hatayı almak için birçok yolu vardır, ancak bunların tümünü bir işlev ya da bağlayıcı olamaz değişken başvuru içeren *çözmek*, veya bir tanımı için bulunamadı. Bir sembol olmadığında derleyici tanımlayabilirsiniz *bildirilen*, ancak değil zaman *tanımlanan*, tanımı farklı kaynak dosya veya kitaplık içinde olabilir. Bir sembol başvurulan ancak hiçbir zaman tanımlanmış, bağlayıcı bir hata oluşturur.

### <a name="coding-issues"></a>Kodlama sorunları

Kaynak kodu veya modül-tanımlama (.def) eşleşmeyen bir durumda bu hatayı neden olabilir dosya. Örneğin, bir değişken adı `var1` olarak erişmeyi deneyin ve bir C++'da kaynak dosyası `VAR1` başka birinde bu hata oluşur. Bu sorunu gidermek için kullanım tutarlı bir şekilde yazılmış ve adları büyük/küçük harfleri.

Kullanan bir proje içinde bu hata oluşabilir [işlevi satır içi kullanım](../../error-messages/tool-errors/function-inlining-problems.md) bir kaynak dosyası yerine bir üstbilgi dosyası işlevleri tanımlar. Satır içine alınmış işlevleri bunları tanımlayan kaynak dosyasının dışında görülemez. Bu sorunu gidermek için burada bildirildikleri üst bilgilerinde satır içine alınmış işlevleri tanımlayın.

Kullanmadan bir C++ programı C işlev çağrı yaparsanız bu hataya neden olabilir bir `extern "C"` C işlev bildirimi. Derleyici C ve C++ kodu için farklı iç simge adlandırma kuralları kullanır ve bu sembolleri çözülürken bağlayıcı arar iç simge adıdır. Bu sorunu gidermek için kullanmak bir `extern "C"` C işlevlerini C iç adlandırma kuralları için bu simgeleri kullanmak derleyicinin C++ kodunuzu kullanılan tüm bildirimleri çevresinde sarmalayıcı. Derleyici Seçenekleri [/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) ve [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) dosyalarını C++ ya da C, sırasıyla, dosya adı uzantısına bakmaksızın derlemek derleyicinin neden olur. Bu seçenekler, iç işlev adlarını beklediğinizden farklı neden olabilir.

Bu hata işlevleri veya dış bağlantıya sahip olmayan veri başvurmak için bir denemede neden olabilir. C++, satır içi işlevleri ve `const` veri olarak açıkça belirtilmediği sürece iç bağlantıya sahip `extern`. Bu sorunu gidermek için açık kullanın `extern` sembolleri bildirimlerinde adlandırılan tanımlama kaynak dosyanın dışında.

Bu hataya neden olabilir bir [eksik işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md) tanımı. Bu hatayı bildirmek, ancak olmayan tanımlama, değişkenler, İşlevler veya sınıflar kodunuzda yaygındır. Derleyici, yalnızca bir işlev prototipi gerekir veya `extern` hata ancak bağlayıcı olmayan bir nesne dosyası oluşturmak için değişken bildirimi çözümleyemiyor işlevine bir çağrı veya değişken başvurusu işlev kodu veya değişken boşluk olmadığından ayrılmış. Bu sorunu gidermek için her başvurulan işlevde ve değişken tam olarak bir kaynak dosyası veya kitaplığı, bağlantının içerdiği tanımlandığından emin olun.

Parametre türleri ya da bu işlev tanımında eşleşmeyen çağırma kurallarını kullanan bir işlev çağrısı bu hataya neden olabilir. C++ nesne dosyalarında [ad düzenlemesi](../../error-messages/tool-errors/name-decoration.md) ne zaman eşleştirmek için Sembol çağrılar gibi kullanılan son düzenlenmiş işlevi adı içine çağırma kuralı, sınıf veya ad alanı kapsamı ve bir işlevin dönüş ve parametre türleri içerir. diğer nesne dosyalarını işlevden çözülmüş. Bu sorunu gidermek için bildiriminin, tanımının ve tüm işlev çağrıları aynı kapsamları, türleri ve çağırma kuralları kullandığınızdan emin olun.

Bir sınıf tanımında bir işlev prototipi içerir, ancak başarısız olduğunda, C++ kodunda bu hata oluşabilir [uygulaması dahil](../../error-messages/tool-errors/missing-function-body-or-variable.md) işlevi ve ardından çağırın. Bu sorunu gidermek için bir sınıfın üyeleri olarak bildirilen bir tanımı tüm adlı sunduğunuzdan emin olun.

Bu hata soyut bir temel sınıftan saf sanal işlevi çağırma girişimi neden olabilir. Saf sanal işlev hiçbir taban sınıf uygulamasını sahiptir. Bu sorunu gidermek için tüm sanal işlevlerin çağrılma uygulanan emin olun.

Bir işlev içinde bildirilen bir değişken kullanmayı deneyerek bu hataya neden olabilir ([yerel bir değişken](../../error-messages/tool-errors/automatic-function-scope-variables.md)), bu işlevin kapsamı dışında. Bu sorunu gidermek için kapsam içinde değil değişkeni referansı kaldırın veya değişkeni daha yüksek bir kapsama taşıyın.

CRT başlatma kodunu gerekli olduğunu belirten bir ileti üretme sürümü bir ATL projesi oluşturduğunuzda, bu hata oluşabilir. Bu sorunu düzeltmek için aşağıdakilerden birini yapın

- Kaldırma `_ATL_MIN_CRT` önişlemci listesinden dahil edilecek CRT başlatma kodunu izin verecek şekilde tanımlar. Bkz: [genel özellik sayfası (Proje)](../../build/reference/general-property-page-project.md) daha fazla bilgi için.

- Mümkünse, CRT başlatma kodunu gerektiren bir CRT işlevleri çağrıları kaldırın. Bunun yerine, bunların Win32 eşdeğerlerini kullanın. Örneğin, `lstrcmp` yerine `strcmp`. CRT başlatma kodunu gerektiren bilinen bazı dize ve kayan nokta işlevleri işlevlerdir.

### <a name="compilation-and-link-issues"></a>Derleme ve bağlantı sorunları

Proje bir kitaplığa bir başvuru eksik olduğunda bu hata oluşabilir (. LIB) veya nesne (. OBJ) dosyası. Bu sorunu çözmek için projeniz için gereken bir kitaplık veya nesne dosyasına bir başvuru ekleyin. Daha fazla bilgi için [bağlayıcı girişi olarak .lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md).

Kullanıyorsanız bu hata oluşabilir [/nodefaultlıb](../../build/reference/nodefaultlib-ignore-libraries.md) veya [/Zl](../../build/reference/zl-omit-default-library-name.md) seçenekleri. Bu seçeneği belirttiğinizde, bunları açıkça eklemiş sürece gerekli kodu içeren kitaplıkları projeye bağlanmaz. Bu sorunu gidermek için açıkça bağlantı komut satırına kullandığınız tüm kitaplıkları içerir. Açıkça birçok eksik CRT veya standart kitaplığı işlev adlarını görürseniz, bu seçeneği kullandığınızda bağlantıdaki CRT ve standart kitaplık DLL'lerini veya kitaplık dosyalarını içerir.

Kullanarak derleme yaparsanız **/CLR** seçeneği, .cctor başvuru eksik olabilir. Bu sorunu gidermek için bkz: [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md) daha fazla bilgi için.

Uygulama hata ayıklama sürümü oluşturma sırasında sürüm modu kitaplıklara bağlarsanız, bu hata oluşabilir. Benzer şekilde, seçenekleri kullanıyorsanız **/mtd** veya **/MDd** veya tanımlama `_DEBUG` ve ardından sürüm kitaplıklarına bağlanması, başka sorunlar arasında birçok olası çözümlenmemiş dışlar beklemelisiniz. Sürüm modu yapı ile hata ayıklama kitaplıklarını bağlama de benzer sorunlara neden olur. Bu sorunu gidermek için hata ayıklama yapılarınızda hata ayıklama kitaplıklarını kullan ve perakende kitaplıklarında, perakende derlemeleri emin olun.

Bu hata, kodunuzu kitaplığa bir sürümünden bir sembole başvuruyor, ancak bağlayıcı kitaplığa farklı bir sürümünü sağlamanız oluşabilir. Genellikle, nesne dosyalarında veya kitaplıklarındaki derleyicinin farklı sürümleri için oluşturulan karıştırılamaz. Yeni bir sürümde sevk kitaplıkları, önceki sürümler ve tam tersini dahil kitaplıklarında bulunamayan semboller içerebilir. Bu sorunu gidermek için nesne dosyaları ve kitaplıkları ile aynı sürümünü derleyici bunları birbirine bağlayarak önce oluşturun.

- Araçlar &#124; seçenekleri &#124; projeleri &#124; VC ++ dizinleri iletişim kutusunda kitaplık dosyaları seçimin Kitaplığı arama sırası değiştirmenize olanak sağlar. Bağlayıcı klasörü proje özellik sayfaları iletişim kutusunda, süresi dolmuş olabilir yolları de içerebilir.

- Bu sorun, yeni bir SDK'sı (belki de farklı bir konuma) yüklüyse ve arama sırasını yeni konumunu gösterecek şekilde güncelleştirilmez görünebilir. Yeni SDK'ye mi yolu normalde koymanız gerekir ve lib varsayılan Visual C++ konumun önüne dizinleri içerir. Ayrıca, katıştırılmış yolları içeren bir proje hala geçerli, ancak farklı bir konuma yüklenen yeni sürümü tarafından eklenen yeni işlevler için güncel olan eski yollar işaret edebilir.

- Komut satırında yapı ve ortam değişkenlerini oluşturdunuz, Araçlar, kitaplıklar ve üst bilgi dosyaları yolları tutarlı bir sürüme Git doğrulayın. Daha fazla bilgi için [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)

Şu an için bir standart olan [C++ adlandırma](../../error-messages/tool-errors/name-decoration.md) derleyici satıcılar veya bir derleyicinin farklı sürümleri arasında bile. Bu nedenle, diğer derleyicilerle derlenmiş nesne dosyaları bağlantılandırma değil aynı adlandırma düzeni oluşturmak ve bu nedenle hatası LNK2001 neden.

[Karıştırma satır içi hem de satır içi derleme seçenekleri](../../error-messages/tool-errors/function-inlining-problems.md) farklı modülleri LNK2001 neden olabilir. Bir C++ Kitaplığı satır içi işlev açık olarak oluşturulursa (**/Ob1** veya **/ob2**) ancak işlevlerini açıklayan ilgili başlık dosyası inlining'i kapalı (hiçbir `inline` anahtar sözcüğü), bu hata gerçekleşir. Bu sorunu gidermek için işlevleri tanımlayın `inline` üstbilgi dosyasında diğer kaynak dosyaları içerir.

Kullanırsanız `#pragma inline_depth` derleyici yönergesi emin olduğunuz bir [değeri 2 veya daha fazla küme](../../error-messages/tool-errors/function-inlining-problems.md)ve ayrıca kullandığınızdan emin olun [/Ob1](../../build/reference/ob-inline-function-expansion.md) veya [/ob2](../../build/reference/ob-inline-function-expansion.md) derleyici seçeneği.

BAĞLANTIYI atlarsanız, bu hata oluşabilir, yalnızca kaynak DLL oluştururken/NOENTRY seçeneği. Bu sorunu gidermek için bağlantı komutuna/NOENTRY seçeneği ekleyin.

Projenizde yanlış/Subsystem veya/Entry ayarları kullanıyorsanız bu hata oluşabilir. Bir konsol uygulaması yazma ve /SUBSYSTEM:WINDOWS belirtin, örneğin, bir çözümlenmemiş dış hata için oluşturulan `WinMain`. Bu sorunu gidermek için proje türü seçenekleri eşleştiğinden emin olun. Bu seçenekleri ve giriş noktaları hakkında daha fazla bilgi için bkz. [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) ve [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçenekleri.

### <a name="exported-symbol-issues"></a>Dışarı aktarılan sorunları

Bu hata, .def dosyasında listelenen bir dışarı aktarım bulunamadı oluşur. Yok, yanlış yazılmış veya C++ ile düzenlenmiş adları kullanan olmasından kaynaklanabilir. Düzenlenmiş adları .def dosyası almaz. Bu sorunu gidermek için gereksiz dışarı aktarmaları kaldırın ve kullanmak `extern "C"` bildirimleri için verilen simgeler.

## <a name="what-is-an-unresolved-external-symbol"></a>Bir çözümlenmemiş dış sembol nedir?

A *sembol* bir işlev veya derlenen nesne dosyası veya kitaplığı tarafından dahili olarak kullanılan genel değişkenin adı. Bir sembol *tanımlanan* derlenen kod için işlev gövdesi burada yerleştirilir burada depolama ayrılır genel değişken veya işlev için nesne dosyasına. Bir *dış sembol* bir sembol bu *başvurulan*, diğer bir deyişle, kullanılan veya bir nesne dosyasında çağrıldı, ancak farklı bir kitaplık veya nesne dosyasında tanımlanmış. Bir *sembolü dışarı* bir nesne dosyası veya tanımlayan kitaplığı tarafından genel olarak kullanıma sunulacak. Bağlayıcı gerekir *çözmek*, veya eşleşen tanımı için bir uygulama veya DLL bağlandığında, bir nesne dosyası tarafından başvurulan tüm dış sembol bulunamadı. Bağlayıcı eşleşen dışarı aktarılan bir sembol herhangi bir bağlantılı dosyaları bularak bir dış sembol çözümlenemiyor bir hata oluşturur.

## <a name="use-the-decorated-name-to-find-the-error"></a>Hatayı bulmak için düzenlenmiş adı kullanın.

C++ Derleyici ve bağlayıcı kullanımı [ad düzenlemesi](../../error-messages/tool-errors/name-decoration.md)olarak da bilinen *ad değiştirmeyi*, bir değişken türü veya dönüş türü, parametre türleri, kapsam ve arama hakkında ek bilgilerin kodlamak için Sembol adı bir işlevde kuralı. Bu düzenlenmiş adı bağlayıcının dış simgeleri çözme arar sembolü adıdır.

Ek bilgi sembol adı bir parçası olur çünkü bir işlev veya değişken bildirimi işlev veya değişken tanımı tam olarak eşleşmiyor, bir bağlantı hatası ortaya çıkabilir. Kaynak dosyaları derleme sırasında farklı derleyici bayraklarına kullanılıyorsa aynı üstbilgi dosyasına hem çağıran kod hem de tanımlama kodu kullanıldığında bile bu durum oluşabilir. Örneğin, kodunuzu kullanmak için derlenirse bu hatayı alabilir `__vectorcall` çağırma kuralı, ancak istemciler varsayılan kullanarak çağırmak için beklediği kitaplığa bağlantı `__cdecl` veya `__fastcall` çağırma kuralı. Çağırma Kuralları farklı olduğundan bu durumda, simgeler ile eşleşmiyor.

Bu tür bir hatayı nedenini bulmanıza yardımcı olmak için bağlayıcı hata iletisi, hem "kolay adı" kaynak kodu ve (parantezlerdeki) düzenlenmiş adı çözümlenmemiş dış sembol için kullanılan gösterir. Düzenlenmiş diğer adlar ile karşılaştırmak için düzenlenmiş adı çevirmek nasıl bilmeniz gerekmez. Beklenen simge adı ve gerçek sembol adı karşılaştırmak için derleyici ile içerdiği komut satırı araçları kullanabilirsiniz:

- [/EXPORTS](../../build/reference/dash-exports.md) ve [/SEMBOLLER](../../build/reference/symbols.md) DUMPBIN komut satırı aracı seçenekleri simgelerin, .dll ve nesne veya kitaplık dosyalarında tanımlanan keşfetmenize yardımcı olabilir. Dışarı aktarılan adları eşleşen bağlayıcı arar düzenlenmiş adları düzenlenmiş olduğunu doğrulamak için bunu kullanabilirsiniz.

Bazı durumlarda, bağlayıcı, yalnızca bir sembol için düzenlenmiş adı bildirebilirsiniz. Tamamlanmamış şeklinde düzenlenmiş adı almak için UNDNAME komut satırı aracını kullanabilirsiniz.

## <a name="additional-resources"></a>Ek kaynaklar

Stack Overflow soru LNK2001 olası nedenleri ve çözümleri hakkında daha fazla bilgi için bkz. [tanımlanmamış başvuru/çözümlenmemiş dış sembol hata nedir ve nasıl düzeltirim bunu?](http://stackoverflow.com/q/12573816/2002113).

