---
title: Bağlayıcı Araçları Hatası LNK2001
ms.date: 12/19/2019
f1_keywords:
- LNK2001
helpviewer_keywords:
- LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
ms.openlocfilehash: 59915b3aa0ad25b5638a43a6d09dccc2b42825ab
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230577"
---
# <a name="linker-tools-error-lnk2001"></a>Bağlayıcı Araçları Hatası LNK2001

> çözümlenmemiş dış sembol "*symbol*"

Derlenen kod, bir başvuru veya *sembol*çağrısı yapar. Sembol, bağlayıcı tarafından aranan herhangi bir kitaplık veya nesne dosyasında tanımlı değil.

Bu hata iletisi, önemli hata [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)tarafından izlenir. Hata LNK1120 onarmak için, önce tüm LNK2001 ve LNK2019 hatalarını düzeltir.

LNK2001 hataları almanın birçok yolu vardır. Hepsi, bağlayıcının *çözememesi*veya bir tanımı bulmak için bir işlev veya değişken *başvurusu* içerir. Derleyici, kodunuzun ne zaman bir sembol *bildirmediğini* tanımlayabilir, ancak *tanımlamaz* . Bunun nedeni, tanımın farklı bir kaynak dosyasında veya kitaplıkta olabilir. Kodunuz bir sembole başvuruyorsa, ancak hiçbir şekilde tanımlanmamışsa, bağlayıcı bir hata oluşturur.

## <a name="what-is-an-unresolved-external-symbol"></a>Çözümlenmemiş dış sembol nedir?

*Sembol* , bir işlevin veya genel değişkenin iç adıdır. Bu, derlenmiş bir nesne dosyasında ya da kitaplıkta kullanılan veya tanımlanmış olan addır. Genel bir değişken, depolama alanının kendisi için ayrıldığı nesne dosyasında tanımlanır. İşlev gövdesi için derlenmiş kodun yerleştirildiği nesne dosyasında bir işlev tanımlanır. *Dış simgeye* tek bir nesne dosyasında başvurulur, ancak farklı bir kitaplıkta veya nesne dosyasında tanımlanmıştır. *İçe aktarılmış bir sembol* , kendisini tanımlayan nesne dosyası veya kitaplık tarafından herkese açık şekilde oluşturulmuş bir simgedir.

Bir uygulama veya DLL oluşturmak için, kullanılan her simgenin bir tanımı olmalıdır. Bağlayıcı, her bir nesne dosyası tarafından başvurulan her dış sembol için eşleşen tanımı *çözümlemelidir*veya bulur. Bağlayıcı, bir dış sembolü çözümleyemezse bir hata oluşturur. Bu, bağlayıcının bağlantılı dosyaların hiçbirinde eşleşen bir içe aktarılmış sembol tanımı bulamadığı anlamına gelir.

## <a name="compilation-and-link-issues"></a>Derleme ve bağlantı sorunları

Bu hata oluşabilir:

- Projede bir kitaplığa bir başvuru eksik olduğunda (. LIB) veya nesnesi (. OBJ) dosyası. Bu sorunu onarmak için, projenize gerekli kitaplığa veya nesne dosyasına bir başvuru ekleyin. Daha fazla bilgi için bkz. [LIB Files as bağlayıcı girişi](../../build/reference/dot-lib-files-as-linker-input.md).

- Projenin bir kitaplığa başvurusu olduğunda (. LIB) veya nesnesi (. OBJ) dosyası başka bir kitaplıktan semboller gerektirir. Bağımlılığa neden olan işlevleri çağırmazsanız bile bu durum oluşabilir. Bu sorunu onarmak için, diğer kitaplığa projenize bir başvuru ekleyin. Daha fazla bilgi için, bkz. [bağlantı için klasik modeli anlama: rde için semboller alma](https://devblogs.microsoft.com/oldnewthing/20130108-00/?p=5623).

- [/Nodefaultlib](../../build/reference/nodefaultlib-ignore-libraries.md) veya [/zl](../../build/reference/zl-omit-default-library-name.md) seçeneklerini kullanırsanız. Bu seçenekleri belirttiğinizde, gerekli kodu içeren kitaplıklar, açıkça dahil etmediğiniz takdirde proje ile bağlantılı değildir. Bu sorunu onarmak için, bağlantı komut satırında kullandığınız tüm kitaplıkları açıkça ekleyin. Bu seçenekleri kullandığınızda çok sayıda CRT veya standart kitaplık işlevi adı görürseniz, doğrudan bu bağlantı içindeki CRT ve standart kitaplık dll 'Lerini veya kitaplık dosyalarını ekleyin.

- **/Clr** seçeneğini kullanarak derlerseniz. İçin eksik bir başvuru olabilir `.cctor` . Bu sorunu giderme hakkında daha fazla bilgi için bkz. [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).

- Bir uygulamanın hata ayıklama sürümünü oluştururken yayın modu kitaplıklarına bağlantı oluşturduysanız. Benzer şekilde, **/MTD** veya **/MDD** seçeneklerini kullanırsanız veya `_DEBUG` daha sonra yayın kitaplıklarına bağlantı oluşturduysanız, diğer sorunlar arasında çok sayıda çözümlenmemiş dışlar beklemeniz gerekir. Bir yayın modu derlemesini hata ayıklama kitaplıklarıyla bağlama de benzer sorunlara neden olur. Bu sorunu gidermek için, hata ayıklama derlemelerinizin hata ayıklama kitaplıklarını ve perakende derlemelerinizin perakende kitaplıklarını kullandığınızdan emin olun.

- Kodunuz bir Kitaplık sürümünden bir simgeye başvuruyorsa, ancak kitaplığın farklı bir sürümünü bağlarsınız. Genellikle, derleyicinin farklı sürümleri için oluşturulmuş nesne dosyalarını veya kitaplıklarını karıştıramazsınız. Bir sürümde gönderilen kitaplıklar, diğer sürümlere dahil olan kitaplıklarda bulunamayan simgeler içerebilir. Bu sorunu giderecek şekilde bağlamadan önce aynı derleyici sürümüne sahip tüm nesne dosyalarını ve kitaplıkları derleyin. Daha fazla bilgi için bkz. [C++ ikili uyumluluğu 2015-2019](../../porting/binary-compat-2015-2017.md).

- Kitaplık yollarının güncel olup olmadığı. **Araçlar > seçenekler > projeler > VC + + dizinleri** iletişim kutusu, **kitaplık dosyaları** seçimi altında, kitaplık arama sırasını değiştirmenize izin verir. Projenin Özellik sayfaları iletişim kutusundaki bağlayıcı klasörü, güncel olmayan yollar da içerebilir.

- Yeni bir Windows SDK yüklendiğinde (Belki de farklı bir konuma). Kitaplık arama sırasının yeni konumu göstermesi için güncelleştirilmeleri gerekir. Normal olarak, yolu varsayılan Visual C++ konumun önüne yeni SDK Include ve lib dizinlerine koymanız gerekir. Ayrıca, gömülü yollar içeren bir proje geçerli olan ancak güncel olmayan eski yollara işaret edebilir. Farklı bir konuma yüklenen yeni sürüm tarafından eklenen yeni işlevlere yönelik yolları güncelleştirin.

- Komut satırında derleme yaptıysanız ve kendi ortam değişkenlerinizi oluşturduysanız. Araçlar, kitaplıklar ve üst bilgi dosyalarına yönelik yolların tutarlı bir sürüme gitdiğini doğrulayın. Daha fazla bilgi için bkz [. komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)

## <a name="coding-issues"></a>Kodlama sorunları

Bu hatanın nedeni şunlar olabilir:

- Kaynak kodunuzda veya modül tanımı (. def) dosyasında eşleşmeyen durum. Örneğin, bir `var1` C++ kaynak dosyasında bir değişkeni adlandırın ve başka bir şekilde bir tane olarak erişmeyi denerseniz `VAR1` , bu hata oluşturulur. Bu sorunu onarmak için tutarlı olarak yazılmış ve küçük adları kullanın.

- [İşlev satır içi](../../error-messages/tool-errors/function-inlining-problems.md)kullanan bir proje. Bu durum, işlevleri bir **`inline`** başlık dosyası yerine bir kaynak dosyasında tanımlarken ortaya çıkabilir. Satır içine alınmış işlevler, bunları tanımlayan kaynak dosya dışında görülemez. Bu sorunu onarmak için, satır içi işlevleri bildirildiği üst bilgilerde tanımlayın.

- C işlevi için bir bildirim kullanmadan C++ programından bir C işlevi çağırma `extern "C"` . Derleyici, C ve C++ kodu için farklı dahili sembol adlandırma kuralları kullanır. İç sembol adı, sembolleri çözümlerken bağlayıcının ne şekilde göründüğünü. Bu sorunu gidermek için, `extern "C"` C++ kodunuzda kullanılan c işlevlerinin tüm bildirimlerinin etrafında bir sarmalayıcı kullanın ve bu, derleyicinin bu semboller Için C iç adlandırma kuralını kullanmasına neden olur. Dosya adı uzantısının ne olduğuna bakılmaksızın, [/TP](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) ve [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçenekleri derleyicinin dosyaları C++ veya C olarak derlemesine neden olur. Bu seçenekler, iç işlev adlarının beklediğiniz kadar farklı olmasına neden olabilir.

- Dış bağlantısı olmayan işlevlere veya verilere başvurma girişimi. C++ ' da, satır içi işlevler ve **`const`** verilerin açıkça olarak belirtilmedikçe iç bağlantısı vardır **`extern`** . Bu sorunu onarmak için, **`extern`** tanımlama kaynak dosyasının dışında başvurulan semboller üzerinde açık bildirimleri kullanın.

- [Eksik bir işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md) tanımı. Kodunuzda, değişkenleri, işlevleri veya sınıfları tanımlarken bu hata yaygındır. Derleyici, **`extern`** hata olmadan bir nesne dosyası oluşturmak için yalnızca bir işlev prototipi veya değişken bildirimine ihtiyaç duyuyor, ancak hiçbir işlev kodu veya değişken alanı ayrılmış olduğundan bağlayıcı işleve veya değişkene yapılan bir çağrıyı çözümleyemiyor. Bu sorunu onarmak için, bağlantı oluşturduğunuz bir kaynak dosyada veya kitaplıkta başvurulan her işlevi ve değişkeni tanımladığınızdan emin olun.

- Return ve Parameter türlerini kullanan bir işlev çağrısı veya işlev tanımındaki olanlarla eşleşmeyen çağırma kuralları. C++ nesne dosyalarında, [ad dekoratı](../../error-messages/tool-errors/name-decoration.md) çağırma kuralını, sınıf veya ad alanı kapsamını ve bir işlevin dönüş ve parametre türlerini kodluyor. Kodlanmış dize, son düzenlenmiş işlev adının bir parçası haline gelir. Bu ad, diğer nesne dosyalarındaki işleve yapılan çağrıları çözümlemek veya eşleştirmek için bağlayıcı tarafından kullanılır. Bu sorunu onarmak için, işlev bildirimi, tanım ve çağrıların tümünün aynı kapsamları, türleri ve çağırma kurallarını kullanmasını sağlayın.

- Bir sınıf tanımına bir işlev prototipi eklediğinizde ancak işlevin [uygulamasını eklemezseniz](../../error-messages/tool-errors/missing-function-body-or-variable.md) , çağıran C++ kodu. Bu sorunu onarmak için, çağırdığınız tüm sınıf üyeleri için bir tanım sağladığınızdan emin olun.

- Soyut bir temel sınıftan saf sanal işlevi çağırma girişimi. Saf sanal işlev temel sınıf uygulamasına sahip değildir. Bu sorunu onarmak için, tüm çağrılan sanal işlevlerin uygulandığından emin olun.

- Bu işlevin kapsamı dışında bir işlev içinde ([yerel bir değişken](../../error-messages/tool-errors/automatic-function-scope-variables.md)) belirtilen bir değişken kullanılmaya çalışılıyor. Bu sorunu onarmak için kapsamda olmayan değişkene başvuruyu kaldırın veya değişkeni daha yüksek bir kapsama taşıyın.

- ATL projesinin yayın sürümünü yapılandırdığınızda, CRT başlangıç kodunun gerekli olduğunu belirten bir ileti üretir. Bu sorunu onarmak için aşağıdakilerden birini yapın,

  - Ön `_ATL_MIN_CRT` işlemci listesinden kaldır CRT başlangıç kodunun eklenmesine izin vermek için tanımlar. Daha fazla bilgi için bkz. [genel özellik sayfası (proje)](../../build/reference/general-property-page-project.md).

  - Mümkünse, CRT başlangıç kodu gerektiren CRT işlevlerine yapılan çağrıları kaldırın. Bunun yerine, Win32 eşdeğerlerini kullanın. Örneğin `strcmp` yerine `lstrcmp` kullanın. CRT başlangıç kodu gerektiren bilinen işlevler, bazı dize ve kayan nokta işlevleridir.

## <a name="consistency-issues"></a>Tutarlılık sorunları

Şu anda derleyici satıcıları arasında ya da aynı derleyicinin farklı sürümleri arasında [C++ ad dekorasyonu](../../error-messages/tool-errors/name-decoration.md) için standart yoktur. Farklı derleyiciler ile derlenen nesne dosyaları aynı adlandırma şemasını kullanmıyor olabilir. Bunları bağlamak hata LNK2001 neden olabilir.

Farklı modüllerde [satır içi ve satır içi derleme seçeneklerini KARıŞTıRMA](../../error-messages/tool-errors/function-inlining-problems.md) LNK2001 neden olabilir. Function ıntıl özelliği açık (**/OB1** veya **/Ob2**) ile bir C++ Kitaplığı oluşturulursa, ancak işlevleri açıklayan karşılık gelen üstbilgi dosyası ( **`inline`** anahtar sözcük olmadan) kapalıysa, bu hata oluşur. Bu sorunu onarmak için, **`inline`** diğer kaynak dosyalarına dahil ettiğiniz başlık dosyasında bulunan işlevleri tanımlayın.

`#pragma inline_depth`Derleyici yönergesini kullanırsanız, [2 veya daha büyük bir değer](../../error-messages/tool-errors/function-inlining-problems.md)ayarlamış olduğunuzdan emin olun ve [/OB1](../../build/reference/ob-inline-function-expansion.md) veya [/Ob2](../../build/reference/ob-inline-function-expansion.md) derleyici seçeneğini de kullandığınızdan emin olun.

Bu hata, yalnızca kaynak DLL oluştururken/NOENTRY bağlantı seçeneğini atlarsanız oluşabilir. Bu sorunu onarmak için, bağlantı komutuna/NOENTRY seçeneğini ekleyin.

Projenizde yanlış/SUBSYSTEM veya/ENTRY ayarları kullanırsanız bu hata ortaya çıkabilir. Örneğin, bir konsol uygulaması yazarsanız ve/SUBSYSTEM: WINDOWS belirtirseniz, için çözümlenmemiş bir dış hata oluşturulur `WinMain` . Bu sorunu onarmak için, bu seçenekleri proje türü ile değiştirdiğinizden emin olun. Bu seçenekler ve giriş noktaları hakkında daha fazla bilgi için bkz. [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) ve [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçenekleri.

## <a name="exported-def-file-symbol-issues"></a>Aktarılmış. def dosyası sembol sorunları

Bir. def dosyasında listelenen bir dışarı aktarma bulunamazsa bu hata oluşur. Bunun nedeni dışa aktarma olmaması, yanlış yazılması veya C++ ile düzenlenmiş adlar kullanılması olabilir. . Def dosyası düzenlenmiş adlar almaz. Bu sorunu onarmak için, gereksiz dışarı aktarmaları kaldırın ve `extern "C"` dışarı aktarılan semboller için bildirimleri kullanın.

## <a name="use-the-decorated-name-to-find-the-error"></a>Hatayı bulmak için düzenlenmiş adı kullanın

C++ derleyicisi ve bağlayıcı, Name *-değiştirmeyi*olarak da bilinen [ad dekorasyonu](../../error-messages/tool-errors/name-decoration.md)kullanır. Ad dekorasyonu, sembol adında bir değişkenin türü hakkında ek bilgiler kodlar. İşlevin sembol adı, dönüş türünü, parametre türlerini, kapsamı ve çağırma kuralını kodluyor. Bu düzenlenmiş ad, bağlayıcının dış sembolleri çözümlemek için aradığı sembol adıdır.

Bir işlev veya değişkenin bildirimi işlevin veya değişkenin tanımıyla *tam olarak* eşleşmiyorsa bir bağlantı hatası oluşur. Bunun nedeni, herhangi bir farkın eşleşme sembol adının bir parçası haline gelir. Hem çağıran kodda hem de tanımlama kodunda aynı üstbilgi dosyası kullanılıyorsa bile hata oluşabilir. Farklı derleyici bayraklarını kullanarak kaynak dosyaları derlerseniz, oluşabilecek bir yol vardır. Örneğin, kodunuz çağırma kuralını kullanacak şekilde derlenmişse **`__vectorcall`** , ancak varsayılan **`__cdecl`** veya çağırma kuralını kullanarak istemcilerin bunu aramasını bekleyen bir kitaplığa bağlantı oluşturduysanız **`__fastcall`** . Bu durumda, çağırma kuralları farklı olduğundan semboller eşleşmez.

Nedeni bulmanıza yardımcı olmak için, hata iletisinde adın iki sürümü gösterilmektedir. Hem "kolay ad", kaynak kodunda kullanılan adı ve düzenlenmiş adı (parantez içinde) görüntüler. Düzenlenmiş adı nasıl yorumlayabileceğinizi bilmeniz gerekmez. Yine de arama yapabilir ve diğer düzenlenmiş adlarla karşılaştırabilirsiniz. Komut satırı araçları beklenen sembol adını ve gerçek sembol adını bulmanıza ve karşılaştırmanıza yardımcı olabilir:

- DUMPBIN komut satırı aracının [/dışarı aktarmalar](../../build/reference/dash-exports.md) ve [/Symbols](../../build/reference/symbols.md) seçenekleri burada faydalıdır. Bunlar,. dll ve nesne veya kitaplık dosyalarınızda hangi simgelerin tanımlandığını keşfetmenize yardımcı olabilir. Alınan düzenlenmiş adların bağlayıcının aradığı düzenlenmiş adlarla eşleştiğini doğrulamak için semboller listesini kullanabilirsiniz.

- Bazı durumlarda, bağlayıcı yalnızca bir sembol için düzenlenmiş adı rapor edebilir. Düzenlenmiş bir adın açıklanmamalıdır biçimini almak için, UNDNAME komut satırı aracını kullanabilirsiniz.

## <a name="additional-resources"></a>Ek kaynaklar

Daha fazla bilgi için, ["tanımsız başvuru/çözümlenmemiş dış sembol hatası nedir ve nasıl düzeltilir?"](https://stackoverflow.com/q/12573816/2002113)sorusuna Stack Overflow bakın.
