---
title: Microsoft ile ilgili bir sorun bildirme C++ araç takımı
ms.date: 06/21/2019
ms.technology: cpp-ide
author: corob-msft
ms.author: corob
ms.openlocfilehash: 13826349836e4c58b7d6a7ce8936186930bc7100
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344378"
---
# <a name="how-to-report-a-problem-with-the-microsoft-c-toolset-or-documentation"></a>Microsoft ile ilgili bir sorun bildirme C++ araç veya belge

Microsoft sorunlar bulursanız C++ (MSVC) derleyici, bağlayıcı veya diğer araçları ve kitaplıkları istiyoruz hakkında bunları da bilmek. Sorunu belgelerimizde olduğunda, bu konuda, çok bilmek istiyoruz.

## <a name="how-to-report-a-c-toolset-issue"></a>Bir C++ araç takımı sorun bildirme

Bir sorun hakkında bize bildirmek için en iyi yolu, bize keşfettiğinize göre sorunun açıklamasını içeren bir rapor göndermektir. Tüm Ayrıntılar programınızın nasıl oluşturacağınız hakkında sahip olması gerekir. Ve bunu içermelidir bir *yineleme*, kendi makinelerinde sorunu yeniden oluşturmak için kullanabileceğiniz eksiksiz bir test çalışması. Bu bilgiler sorun bizim kodun içinde vardır ve ortamınız için yerel olmayan hızla doğrulamamıza olanak tanır. Bu derleyicinin ve nedenini tanılamak için diğer sürümleri etkilenmediğinizi yardımcı olur.

Aşağıdaki bölümlerde, iyi bir rapor kılan hakkında okuyun. Bir yineleme, buldunuz sorun türü için oluşturma ve raporunuzu ürün ekibine göndermek nasıl açıklanmaktadır. Raporlarınızı bize ve sizin gibi diğer geliştiriciler için önemlidir. Microsoft geliştirmemize yardımcı olmak için teşekkür ederiz C++!

## <a name="how-to-prepare-your-report"></a>Raporunuzu hazırlamayı öğrenin

Bize tam bilgi bulunamadı sorunu yeniden oluşturmak zor olduğundan, yüksek kaliteli rapor oluşturmak önemlidir. Daha iyi raporunuzu, daha etkili bir şekilde biz yeniden oluşturabilir ve sorunu tanılayın.

En azından raporunuza içermesi gerekir:

- Tam sürüm bilgisi kullandığınız araç.

- Kodunuzu derlemek için kullanılan tam cl.exe komut satırı.

- Bulunan sorunun ayrıntılı bir açıklaması.

- Bir yineleme: sorunu gösteren bir tam, Basitleştirilmiş, kendi içindeki kaynak kod örneği.

İçin okumaya devam ihtiyacımız belirli bilgiler hakkında daha fazla bilgi edinin ve burada bulabilirsiniz ve nasıl iyi bir yineleme oluşturun.

### <a name="the-toolset-version"></a>Araç takımının sürüm

Tam sürüm bilgilerini ve hedef mimari soruna neden olan araç ihtiyacımız var. Biz, yineleme aynı araç takımı karşı bizim makinelerde sınayabilmeniz olmasıdır. Sorunu yeniden oluşturabileceğinizi, bu bilgileri ayrıca diğer hangi sürümlerinin araç araştırmak için bir başlangıç noktası olan aynı sorunu sağlıyor.

#### <a name="to-report-the-full-version-of-your-compiler"></a>Rapora derleyicinizin tam sürümü

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir. Örneğin, üzerinde x64 x64 için Visual Studio 2017 kullanarak yapı hedefleri seçin **x64 VS 2017 için yerel Araçlar komut istemi**. Daha fazla bilgi için [Geliştirici komut istemi kısayolları](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts).

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /Bv**.

Çıkış şuna benzemelidir:

```Output
C:\Users\username\Source>cl /Bv
Microsoft (R) C/C++ Optimizing Compiler Version 19.14.26428.1 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

Compiler Passes:
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\cl.exe:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c1xx.dll:      Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\c2.dll:        Version 19.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\link.exe:      Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\mspdb140.dll:  Version 14.14.26428.1
 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Tools\MSVC\14.14.26428\bin\HostX86\x86\1033\clui.dll: Version 19.14.26428.1

cl : Command line error D8003 : missing source filename
```

Kopyalayıp raporunuzda tüm çıktıyı yapıştırın.

### <a name="the-command-line"></a>Komut satırı

Tam komut satırı, cl.exe ve tüm bağımsız değişkenleri, kodunuzu derlemek için kullanılan, ihtiyacımız var. Biz bunu tam olarak aynı şekilde bizim makinelerde oluşturmanıza yardımcı olacak olmasıdır. Buldunuz sorun yalnızca belirli bir bağımsız değişken veya bağımsız değişken bileşimine oluştururken olabileceğinden önemlidir.

Sorunla karşılaştığınız hemen sonra bu bilgileri bulmak için en iyi derleme günlüğünde yerdir. Komut satırı sorunu katkıda bulunan tam olarak aynı bağımsız değişkenleri içeren sağlar.

#### <a name="to-report-the-contents-of-the-command-line"></a>Komut satırının içeriğini bildirmek için

1. Bulun **CL.command.1.tlog** dosya ve açın. Varsayılan olarak, bu dosya, Belgeler klasöründe bulunan \\Visual Studio *sürüm*\\projeleri\\*SolutionName* \\ *ProjectName*\\*yapılandırma*\\*ProjectName*.tlog\\CL.command.1.tlog, veya kullanıcı klasörünüzün altında \\Kaynak\\depoları\\*SolutionName*\\*ProjectName*\\*yapılandırma* \\ *ProjectName*.tlog\\CL.command.1.tlog. Başka bir yapı sistemi kullanıyorsanız veya projeniz için varsayılan konum değiştirdiyseniz, farklı bir konumda olabilir.

   Bu dosya içinde her ayrı satırlarda onları, derlemek için kullanılan komut satırı bağımsız değişkenleri ardından, kod dosyaları kaynak adlarını bulabilirsiniz.

1. Sorunun gerçekleştiği kaynak kodu dosyasının adını içeren satırı bulun. Aşağıdaki satırda karşılık gelen cl.exe komut satırı bağımsız değişkenlerini alır.

Kopyalayıp raporunuzda tüm komut satırı yapıştırabilirsiniz.

### <a name="a-description-of-the-problem"></a>Sorun açıklaması

Buldunuz sorunun ayrıntılı bir açıklaması ihtiyacımız var. Makinelerimiz aynı etkisini görüyoruz doğrulayabilmemiz olmasıdır. Ayrıca bazen bizim için ne yapmaya çalıştığınızı ve olmasını beklediğinizi bilmek yararlıdır.

İyi bir açıklama sağlar **tam hata iletileri** araç takımı veya çalışma zamanı davranışı görürsünüz. Biz düzgün sorun yeniden olduğunu doğrulamak için bu bilgiye ihtiyacımız var. Dahil **tüm** çıkışı, derleyicinin yalnızca son hata iletisi. Soruna raporu açan her şeyi görmek ihtiyacımız var. Komut satırı derleyicisini kullanarak sorunu çoğaltabilirsiniz ise, derleyici çıkışını tercih edilir. IDE ve diğer yapı sistemi bakın veya yalnızca ilk satır bir hata iletisinin yakalama hata iletilerini filtreleyebilirsiniz.

Derleyici geçersiz kod kabul eder ve bir tanılama oluşturmaz sorun olması durumunda, raporunuza dahil.

Çalışma zamanı davranışı sorun bildir, eklenecek bir **tam kopya** hangi program yazdırır ve görmeyi beklediğiniz. İdeal olarak, çıktı bildiriminde kendisi, örneğin, ekleyeceğiz `printf("This should be 5: %d\n", actual_result);`. Programınızı kilitlenmesine veya yanıt vermemeye başlıyor, bu da söz.

Tüm keşfettiğinize göre belgele gibi bulunan sorunu çözmemize yardımcı olabilecek diğer ayrıntıları tanılamak ekleyin. Raporunuzda başka bir yerde bulunan bilgileri kullanmamasını deneyin.

### <a name="the-repro"></a>Yineleme

A *yineleme* tam ve müstakil kaynak kod bir örnektir. Sorunu tekrarlanarak gösteren, bulduk, bu nedenle adı. Böylece hata bizim makinelerde üretebileceği istiyorduk ihtiyacımız var. Kodun kendisi tarafından derleyen ve çalışan temel bir yürütülebilir dosyayı oluşturmak için yeterli olmalıdır. Veya, *misiniz* derlemek ve çalıştırmak, sizin için sorun buldunuz. Bir yineleme, bir kod parçacığı değildir. Tam işlevleri ve sınıfları ve tüm gerekli içermesi # standart üstbilgi için bile include.

#### <a name="what-makes-a-good-repro"></a>İyi bir yineleme yapan nedir

İyi bir yineleme aşağıdaki gibidir:

- **En az.** Oluşturmalar, olabildiğince az henüz yine de tam olarak bulunan sorun gösterilmektedir. Oluşturmalar karmaşık veya gerçekçi olması gerekmez. Bunlar yalnızca standart veya belgelenmiş derleyici uygulaması için uygun kodu görüntülemeniz gerekir. Bir tanılama eksik, uyumlu olmayan kodu, yineleme göstermelidir. Sorun göstermek için yeterli kod yalnızca içeren basit, için öz oluşturmalar idealdir. Kaldırın veya kodu basitleştirmek ve uyumlu kalır ve ayrıca sorun değiştirmeden bırakın, ardından bunu yapın. Karşı çalışan kod örneklerini eklemeniz gerekmez.

- **Kendi içinde.** Oluşturmalar gereksiz bağımlılıkları kaçınmanız gerekir. Sorun olmadan üçüncü taraf kitaplıklar yeniden oluşturabiliyorsanız, bunu yapın. Basit çıkış deyimleri yanı sıra herhangi bir kitaplık kodu olmadan sorunu yeniden oluşturabileceğinizi varsa (örneğin, `puts("this shouldn't compile");`, `std::cout << value;`, ve `printf("%d\n", value);`), bunu yapın. Örnek bir tek kaynak kod dosyasına başvuru kullanıcı üst bilgileri olmadan sıkıştırılmış durumunda idealdir. Biz sorunun olası bir katılımcı olarak göz önünde bulundurmanız gereken kod miktarını azaltarak bize artık çok yararlı olur.

- **Karşı derleyici en son sürümü.** Oluşturmalar en son güncelleştirmesini en son sürüme mümkün olduğunda araç kullanmanız gerekir. Veya sonraki bir güncelleştirme veya sonraki ana sürümüne ait en son yayın öncesi sürümünü kullanın. Araç takımı eski sürümlerini bulabilirsiniz sorunları daha yeni sürümlerinde genellikle düzelttik. Düzeltmeleri backported olağanüstü durumlarda yalnızca eski sürümleri için olan.

- **Diğer derleyiciler karşı kullanıma** varsa. Taşınabilir C++ kodu içeren oluşturmalar davranışı diğer derleyiciler karşı mümkünse doğrulamanız gerekir. C++ Standart program doğruluk sonuçta belirler ve derleyici mükemmel bir seçimdir. Ancak, Clang ve GCC, kodunuzu bir tanılama olmadan kabul edin ve MSVC değil, büyük olasılıkla bizim derleyicisindeki bir hata buldunuz. (Diğer bir olasılık Unix ve Windows davranış veya C++ standartları uygulama farklı düzeylerde farklılıkları dahil vb..) Ardından tüm derleyiciler kodunuz reddettiğinizde, kodunuzun yanlış olduğundan emin olma olasılığı yüksektir. Farklı hata iletilerini görme sorunu kendiniz tanılamaya yardımcı olabilir.

   Kodunuzu karşı test etmek için çevrimiçi derleyiciler listesini bulabilirsiniz [çevrimiçi C++ Derleyicileri](https://isocpp.org/blog/2013/01/online-c-compilers) ISO C++ Web sitesi ya da bu seçkin [çevrimiçi C++ Derleyicileri listesi](https://arnemertz.github.io/online-compilers/) GitHub üzerinde. Belirli bazı örnekler [Wandbox](https://wandbox.org/), [derleyici Gezgini](https://godbolt.org/), ve [Coliru](https://coliru.stacked-crooked.com/).

   > [!NOTE]
   > Microsoft ile çevrimiçi derleyicisindeki Web siteleri bağlı değil. Birçok çevrimiçi derleyicisindeki Web siteleri, kişisel bir proje olarak çalıştırılır. Bunu okuyun, ancak diğerleri kullanabileceğiniz bir arama bulmanız gerekir sitelerin bazıları kullanılamıyor olabilir.

Sorunları derleyici, bağlayıcı ve kitaplıklarında, kendisini özellikle yollarını göstermektedir eğilimindedir. Ne tür bir yineleme raporunuzda içermelidir. karşılaştığınız sorun türünü belirler. Uygun bir yineleme araştırmak için hiçbir şey sahibiz. Birkaç tür karşılaşabileceğiniz sorunlar aşağıda verilmiştir. Yineleme türü oluşturma adımları her türden bir soruna bildirmek için kullanmalısınız yönergeler dahil ediyoruz.

#### <a name="frontend-parser-crash"></a>Kilitlenme ön uç (ayrıştırıcı)

Ön uç kilitlenmeler, derleyici ayrıştırma işlemi sırasında oluşur. Genellikle, derleyici yayan [önemli hata C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md)ve kaynak kodu dosyası ve satır numarası hatanın gerçekleştiği başvuruları. Genellikle msc1.cpp adlı bir dosya söz edilen, ancak bu ayrıntı yoksayabilirsiniz.

Kilitlenme bu tür için sağlayan bir [yineleme önceden işlenmiş](#preprocessed-repros).

Bu tür bir kilitlenme için derleyici çıktı örneği aşağıda verilmiştir:

```Output
SandBoxHost.cpp
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        fatal error C1001: An internal error has occurred in the compiler.
(compiler file 'msc1.cpp', line 1369)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):
        note: This diagnostic occurred in the compiler generated function
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted
        to send an error report to Microsoft later.
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

#### <a name="backend-code-generation-crash"></a>Kilitlenme arka uç (kod oluşturma)

Arka uç kilitlenmeleri kod derleyici oluşturma aşaması sırasında oluşur. Genellikle, derleyici yayan [önemli hata C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md), değil kaynak kodu dosyasının başvuru ve satır numarası sorunla ilişkili. Genellikle bir dosya derleyici bahsetmeleri\\utc\\src\\p2\\main.c, ancak bu ayrıntı yok sayabilirsiniz.

Kilitlenme bu tür için sağlayan bir [bağlantı yineleme](#link-repros) bağlama sırasında kod oluşturma (LTCG) kullanıyorsanız, etkin **/GL** cl.exe komut satırı bağımsız değişkeni. Aksi takdirde, sağlayan bir [yineleme önceden işlenmiş](#preprocessed-repros) yerine.

Hangi LTCG kullanılmayan bir arka uç kilitlenme için derleyici çıktı örneği aşağıda verilmiştir. Derleyici çıktınız aşağıdakine benzer olacaktır, sağlamanız bir [yineleme önceden işlenmiş](#preprocessed-repros).

```Output
repro.cpp
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:
        An internal error has occurred in the compiler.
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)
To work around this problem, try simplifying or changing the program near the
        locations listed above.
Please choose the Technical Support command on the Visual C++
Help menu, or open the Technical Support help file for more information
INTERNAL COMPILER ERROR in
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'
    Please choose the Technical Support command on the Visual C++
    Help menu, or open the Technical Support help file for more information
```

Çizgi ile başlayan, **iç derleyici hatası** link.exe, bahsetmeleri cl.exe yerine LTCG etkinleştirildi. Sağlayan bir [bağlantı yineleme](#link-repros) bu durumda. LTCG derleyici hata iletisindeki etkin olup açık olmadığı durumlarda, komut satırı bağımsız değişkenlerini inceleyin. Bunları, derleme oturum için bir önceki adımda kopyaladığınız **/GL** komut satırı bağımsız değişkeni.

#### <a name="linker-crash"></a>Bağlayıcı kilitlenme

Bağlayıcı kilitlenmeleri derleyici çalıştırdıktan sonra bağlama işlemi sırasında oluşur. Genellikle, bağlayıcı yayar [Bağlayıcı araçları hatası LNK1000](../error-messages/tool-errors/linker-tools-error-lnk1000.md).

> [!NOTE]
> Çıkış C1001 bahsetmeleri veya bağlama zamanı kod oluşturmayı içerir, başvurmak [arka uç (kod oluşturma) kilitlenme](#backend-code-generation-crash) yerine.

Kilitlenme bu tür için sağlayan bir [bağlantı yineleme](#link-repros).

Bu tür bir kilitlenme için derleyici çıktının bir örneği aşağıda verilmiştir:

```Output
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2

  Version 14.00.22816.0

  ExceptionCode            = C0000005
  ExceptionFlags           = 00000000
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)
        "z:\tools\bin\x64\link.exe"
  NumberParameters         = 00000002
  ExceptionInformation[ 0] = 0000000000000000
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF

CONTEXT:

  Rax    = 0000000000000400  R8     = 0000000000000000
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690
  Rdx    = 000000655F97E270  R11    = 0000000000000400
  Rsp    = 000000655F97E248  R12    = 0000000000000000
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000
  Rsi    = 000000655DF82580  R14    = 000000655F97F390
  Rdi    = 0000000000000000  R15    = 0000000000000000
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206
  SegCs  = 0000000000000033  SegDs  = 000000000000002B
  SegSs  = 000000000000002B  SegEs  = 000000000000002B
  SegFs  = 0000000000000053  SegGs  = 000000000000002B
  Dr0    = 0000000000000000  Dr3    = 0000000000000000
  Dr1    = 0000000000000000  Dr6    = 0000000000000000
  Dr2    = 0000000000000000  Dr7    = 0000000000000000
```

Artımlı bağlamayı etkindir ve sonra yalnızca başarılı ilk bağlantı kilitlenme oluştu ise diğer bir deyişle, bir sonraki artımlı bağlantı dayandığı yalnızca ilk tam bağlantıya sonra da kitaplığı ve nesne (.obj) bir kopyasını kaynağına karşılık gelen (.lib) dosyaları belirtin ilk bağlantı tamamlandıktan sonra değiştirilen dosyalar.

#### <a name="bad-code-generation"></a>Hatalı kod oluşturma

Hatalı kod oluşturma nadir olarak rastlanıyor. Derleyici, uygulamanızın çalışma zamanında çökmesine neden yanlış kod yanlışlıkla oluşturduğunda gerçekleşir. Bunun yerine, doğru kodu oluşturmak veya derleme zamanında bir sorunu algıla. Sorun düşünüyorsanız, sonuçlar hatalı kod oluşturma buldunuz, raporunuzu aynı şekilde işlem bir [arka uç (kod oluşturma) kilitlenme](#backend-code-generation-crash).

Kilitlenme bu tür için sağlayan bir [bağlantı yineleme](#link-repros) kullanıyorsanız **/GL** cl.exe komut satırı bağımsız değişkeni. Sağlayan bir [yineleme önceden işlenmiş](#preprocessed-repros) Aksi takdirde.

## <a name="how-to-generate-a-repro"></a>Bir yineleme oluşturma

Sorunun kaynağını izlemenize yardımcı olmak için bir [iyi yineleme](#what-makes-a-good-repro) yaşamsal önem taşır. Tüm oluşturmalar belirli türdeki özetlenen adımları uygulamadan önce mümkün olduğunca sorunu gösteren kod Daralt deneyin. Bağımlılıklar, gerekli üst bilgileri ve kitaplıkları simge durumuna küçültür veya ortadan kaldırmak deneyin. Mümkünse, kullanılan önişlemci tanımlarını ve derleyici seçenekleri sınırlayın.

Raporu farklı türde sorunları için kullanacağınız oluşturmalar çeşitli türleri oluşturmak için yönergeler aşağıda verilmiştir.

### <a name="preprocessed-repros"></a>Önceden işlenmiş oluşturmalar

A *yineleme önceden işlenmiş* bir sorunu gösteren bir tek bir kaynak dosyası. Bunu C önişlemcisinin çıktısından oluşturulur. Oluşturmak için kullanmak **/P** özgün yineleme kaynak dosyada derleyici seçeneği. Bu seçenek satır içleri dahil edilen üst bilgileri ek kaynak ve üstbilgi dosyaları bağımlılıkları kaldırın. Seçeneği, makrolar, #ifdef koşullular ve yerel ortamınızda bağımlı diğer önişlemci komutlarını da giderir.

> [!NOTE]
> Genellikle zaten sorunu düzelttik olup olmadığını görmek için en son, devam eden kararlılığımızın yerine istediğimizden, önceden işlenmiş oluşturmalar hataları standart kitaplığı kararlılığımızın bir sonucu olabilir sorunları için faydalı değildir. Bu durumda, yineleme önişle yoktur ve azaltırsanız olamaz, tek bir kaynak dosyası, sorunu kodunuzu veya benzer bir .zip dosyasına paketleyin veya bir IDE proje yineleme kullanmayı düşünün. Daha fazla bilgi için [diğer oluşturmalar](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Bir kaynak kodu dosyası ön işleme için

1. Açıklandığı gibi bir yineleme oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir.

1. Repro projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /P** *bağımsız değişkenleri* *filename.cpp*. İçin *bağımsız değişkenleri*, yukarıda yakalanan değişkenleri listesini kullanın. *filename.cpp* yineleme kaynak dosyanın adıdır. Bu komut, komut satırı yineleme için kullanılır, ancak derleme önişlemci geçişi sonrasında kesiliyor çoğaltır. Önceden işlenmiş kaynak koduna Yazar sonra *filename.i*.

İşleniyorsa bir C++/CX kaynak kodu dosyası veya kullanmakta olduğunuz C++ modülleri özelliğinin, bazı ek adımlar gereklidir. Daha fazla bilgi için aşağıdaki bölümlere bakın.

Önceden işlenmiş dosyayı oluşturduğunuza göre sonra da emin olmak için iyi bir fikirdir, önceden işlenmiş dosyayı derlerken sorunu hala oluşturmalar.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Önceden işlenmiş dosya hala oluşturmalar hatayı doğrulamak için

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl** *bağımsız değişkenleri* **/TP** *filename.i* derlemek için cl.exe bildirmek için önceden işlenmiş dosyayı farklı bir C++ kaynak dosyası. *Bağımsız değişkenleri* aynı bağımsız değişken yukarıda, ancak tüm yakalanan **/D** ve **/I** bağımsız değişkenleri kaldırıldı. Bunlar zaten önceden işlenmiş dosyayı dahil edilmiş olmasıdır. *filename.i* , önceden işlenmiş dosya adıdır.

1. Sorunu yeniden olduğunu onaylayın.

Son olarak, önceden işlenmiş yineleme ekleme *filename*.i raporunuza.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Önceden işlenmiş C++/CX WinRT/UWP kod oluşturmalar

C + kullanıyorsanız +/ CX yürütülebilir dosyanızı oluşturmak için oluşturma ve önceden işlenmiş istiyorduk doğrulamak için gereken bazı ek adımlar vardır.

#### <a name="to-preprocess-ccx-source-code"></a>Ön işleme için C++/CX kaynak kodu

1. Önceden işlenmiş kaynak dosyası açıklandığı oluşturma [bir kaynak kodu dosyası ön işleme için](#to-preprocess-a-source-code-file).

1. Oluşturulan arama _filename_.i dosyası **#using** yönergeleri.

1. Tüm başvurulan dosyaların listesini olun. Tüm Windows bırakın\*mscorlib.dll .winmd dosyaları ve platform.winmd dosyaları.

Önceden işlenmiş dosyayı yine de sorunu yakalandığı doğrulamak hazırlamak için

1. Önceden işlenmiş dosya için yeni bir dizin oluşturun ve yeni dizine kopyalayın.

1. .Winmd dosyaları kopyalayın, **#using** yeni dizine listesi.

1. Bir boş vccorlib.h dosyasını yeni dizine oluşturun.

1. Kaldırmak için önceden işlenmiş dosyayı düzenleyin **#using** mscorlib.dll için yönergeleri.

1. Yalnızca tam dosya adları kopyalanan .winmd dosyaları için mutlak yollar değiştirmek için önceden işlenmiş dosyayı düzenleyin.

Önceden işlenmiş dosyayı yine yukarıdaki sorun yakalandığı onaylayın.

### <a name="preprocessed-c-modules-repros"></a>Önceden işlenmiş olan C++ modülleri oluşturmalar

C++ derleyicisinin modülleri özelliğinin kullanıyorsanız, oluşturma ve önceden işlenmiş istiyorduk doğrulamak için gereken farklı adımlar vardır.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Bir modül kullanan bir kaynak kodu dosyası ön işleme

1. Açıklandığı gibi bir yineleme oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir.

1. Repro projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /P** *bağımsız değişkenleri* *filename.cpp*. *Bağımsız değişkenleri* yukarıdaki yakalanan bağımsız değişkenidir ve *filename.cpp* modülünü kullanan kaynak dosyasının adıdır.

1. Modül arabirimi (.ifc çıkış) yerleşik yineleme projesini içeren dizine geçin.

1. Bir modül arabirimi oluşturmak için kullanılan komut satırı bağımsız değişkenlerini yakalar.

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /P** *bağımsız değişkenleri* *modulename.ixx*. *Bağımsız değişkenleri* yukarıdaki yakalanan bağımsız değişkenidir ve *modulename.ixx* modül arabirimi oluşturan dosyanın adıdır.

Önceden işlenmiş dosya ürettiğiniz sonra önceden işlenmiş dosyayı kullanırken sorun hala oluşturmalar emin olmak için iyi bir fikirdir.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Önceden işlenmiş dosya hala oluşturmalar hatayı doğrulamak için

1. Geliştirici konsol penceresinde geri yineleme projenizi içeren dizine geçin.

1. Komutu girdikten **cl** *bağımsız değişkenleri* **/TP** *filename*.i C++ kaynak dosyası gibi önceden işlenmiş dosya derlemek için yukarıdaki gibi.

1. Sorunu hala tarafından önceden işlenmiş dosyayı yeniden onaylayın.

Son olarak, önceden işlenmiş yineleme dosya ekleme (*filename*.i ve *modulename*.i) raporunuza .ifc çıkış yanı sıra.

### <a name="link-repros"></a>Bağlantı oluşturmalar

A *bağlantı yineleme* bağlayıcı tarafından oluşturulan içeriği tarafından belirtilen bir dizinin **bağlantı\_yineleme** ortam değişkeni. Bu bağlantı zamanında ortaya çıkan bir sorun topluca gösteren derleme yapıtları içerir. Bağlama sırasında kod oluşturma (LTCG) içeren bir arka uç kilitlenme veya bir bağlayıcı kilitlenme örneklerindendir. Bu derleme yapıları olan sorunu yeniden kombinasyonlarına bağlayıcı gerekli olanlar. Bu ortam değişkeni kullanarak bir bağlantı yineleme kolayca oluşturulabilir. Bu bağlayıcı'nın yerleşik bir yineleme oluşturma yeteneği sağlar.

#### <a name="to-generate-a-link-repro"></a>Bir bağlantı yineleme oluşturmak için

1. Açıklandığı gibi bir yineleme oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir.

1. Geliştirici komut istemi konsol penceresinde yineleme projenizi içeren dizine geçin.

1. Girin **mkdir linkrepro** bağlantı yineleme için bir dizin oluşturmak için.

1. Komutu girdikten **bağlantı ayarlayın\_yineleme linkrepro =** ayarlamak için **bağlantı\_yineleme** oluşturduğunuz dizine ortam değişkeni. Genellikle daha karmaşık projeler için olduğu gibi farklı bir dizinden derleme çalışırsa ayarlayın **bağlantı\_yineleme** linkrepro dizinine tam yolu için bunun yerine.

1. Geliştirici komut istemi konsol penceresinde, Visual Studio'da aracındaki Projeyi derlemek için komutu girin **devenv**. Bu değeri sağlar **bağlantı\_yineleme** ortam değişkenidir Visual Studio'da görünür. Komut satırından Projeyi derlemek için yineleme derleme çoğaltmak için yukarıda yakalanan komut satırı bağımsız değişkenlerini kullanın.

1. Repro projenizi derleyin ve beklenen sorunu oluştu onaylayın.

1. Derleme yapmak için kullanılan Visual Studio'yu kapatın.

1. Geliştirici komut istemi konsol penceresinde komutu girin **bağlantı ayarlayın\_yineleme =** temizlemek için **bağlantı\_yineleme** ortam değişkeni.

Son olarak, tüm linkrepro dizin bir .zip dosyasına veya benzer sıkıştırarak yineleme paketini ve raporunuza ekleyin.

### <a name="other-repros"></a>Diğer oluşturmalar

Tek bir kaynak dosyası ya da önceden işlenmiş yineleme sorun indiremezsiniz ve sorun bağlantısını yineleme gerektirmez, biz bir IDE proje araştırabilirsiniz. Tüm kılavuzuna nasıl iyi bir yineleme oluşturmak hala geçerlidir: Kod nerede depolandığının minimal ve müstakil olmalıdır. Sorun, en son araçlarımızı gerçekleşmesi gerektiğini ve uygunsa, diğer derleyicilerde görülür olmaması gerekir.

Minimal bir IDE proje olarak, yineleme oluşturun, sonra tüm dizin yapısının bir .zip dosyasına veya benzer sıkıştırarak paketini ve raporunuza ekleyin.

## <a name="ways-to-send-your-report"></a>Raporunuzu gönderme yolları

Birkaç raporunuzu bize almak için iyi bir yolu var. Visual Studio'nun yerleşik kullanabileceğiniz [sorun rapor](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017), veya [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sayfaları. Ayrıca bir **ürün geri bildirimi** bu sayfanın alt kısmındaki düğmesi. Seçim, yerleşik araçlar, ekran görüntüleri yakalamanızı ve raporunuzu düzenlemek için IDE içinde kullanmak istediğinize bağlıdır. Doğrudan değil tercih ederseniz, geliştirici topluluğu Web sitesini kullanabilirsiniz.

> [!NOTE]
> Raporunuzu nasıl gönderdiğiniz bağımsız olarak Microsoft, gizliliğinize saygı duyar. Microsoft tüm veri gizlilik yasalarına ve düzenlemelerine uyumluluğa taahhüt eder. Biz bize verileri nasıl kabul hakkında daha fazla bilgi için bkz: [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement).

### <a name="use-the-report-a-problem-tool"></a>Sorun raporu kullanın

**Sorun bildir** araçtır Visual Studio'da Visual Studio kullanıcıların yalnızca birkaç tıklama ile yaşayabileceğiniz sorunları için bir yol. Bu, buldunuz sorun hakkında ayrıntılı bilgi göndermek için basit bir form açılır. Ayrıca IDE'den çıkmadan sonra raporunuzu gönderebilirsiniz.

Sorununuzu aracılığıyla raporlama **sorun bildir** araçtır IDE'den kolay. Başlık Çubuğu'ndan seçerek erişebildiğinizi **geri bildirim gönder** yanındaki simge **Hızlı Başlat** arama kutusu. Veya, menü çubuğunda Bul **yardımcı** > **geri bildirim gönder** > **sorun bildir**.

Önce bir sorunu bildirmek seçtiğinizde, benzer sorunlarla ilgili Geliştirici topluluğu arayın. Sorununuzu daha önce bildirilen durumunda rapora oylamak ve açıklamalar ile ek özellikleri ekleyin. Benzer bir sorun görmüyorsanız seçin **yeni sorun bildirme** düğme Visual Studio geri bildirim iletişim kutusunun alt kısmında ve sorununuzu bildirmek için adımları izleyin.

### <a name="use-the-visual-studio-developer-community-pages"></a>Visual Studio Geliştirici topluluğu sayfalarını kullanma

Visual Studio Geliştirici topluluğu sayfaları sorunları bildirme ve Visual Studio ve C++ Derleyici, araçları ve kitaplıkları için çözüm bulmak için başka bir uygun yoldur. Belirli bir geliştirici topluluğu sayfa için [Visual Studio](https://developercommunity.visualstudio.com/spaces/8/index.html), [Mac için Visual Studio](https://developercommunity.visualstudio.com/spaces/41/index.html), [.NET](https://developercommunity.visualstudio.com/spaces/61/index.html), [ C++ ](https://developercommunity.visualstudio.com/spaces/62/index.html), [Azure DevOps Hizmetleri](https://developercommunity.visualstudio.com/spaces/21/index.html), ve [TFS](https://developercommunity.visualstudio.com/spaces/22/index.html).

Altındaki Topluluk sekmelerin her sayfanın üst kısmındaki arama kutusuna var. Benzer bir sorun bildirin gönderilerini bulmak için kullanabilirsiniz. Bir çözüm bulabilirsiniz veya sorununuz için ilgili diğer yararlı bilgiler zaten mevcuttur. Birisi aynı sorunla daha önce ardından oylamak ve açıklama üzerinde bildirmediyse, rapor yerine yeni bir sorun raporu oluşturun. Yorum yapmak için oy verin veya yeni bir sorun bildirmek için Visual Studio hesabınızda oturum açmak için istenebilir. İlk kez oturum açarken, profilinize Geliştirici topluluğu uygulama erişimi vermek kabul etmeniz gerekir.

C++ Derleyici, bağlayıcı ve diğer araçlar ve kitaplıkların kullanımı ile ilgili sorunlar için [C++](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfası. Sorununuz için arama yapın ve bunu önce bildirilen taşınmadığından, seçim **sorun bildir** arama kutusunun yanındaki düğmeyi. Repro kodunuzu ve komut satırı, ekran görüntüleri, ilgili tartışmalar için bağlantıları ve düşündüğünüz faydalı ve ilgili diğer bilgileri içerebilir.

> [!TIP]
> Diğer tür sorunları için ilgisiz Visual Studio'da bulabileceğiniz C++ (örneğin, kullanıcı Arabirimi sorunları, bozuk bir IDE işlevsellik veya genel kilitlenme), bir araç takımı kullanın **sorun bildir** IDE'de araç. Ekran görüntüsü özelliklerini ve, buldunuz soruna neden UI eylemlerini kaydedin yeteneğini nedeniyle en iyi seçenek budur. Bu tür hatalara da üzerinde aranabilir [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) site. Daha fazla bilgi için [Visual Studio ile ilgili bir sorun bildirme](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017).

### <a name="reports-and-privacy"></a>Raporlar ve gizlilik

**Tüm raporlar ve yorumlar ve yanıt bilgileri varsayılan olarak herkese görünür**. Normalde, sorunları, çözümler ve diğer kullanıcıların bulduğunuz geçici çözümleri görmek tüm topluluğuna izin verdiğinden bir faydası olur. Ancak, verileriniz veya kimliğini, gizlilik veya fikri mülkiyet hakları nedeniyle, genel yapma hakkında endişeleriniz varsa seçeneğiniz vardır.

Kimliğinizi göstermeden hakkında endişeleriniz varsa [yeni bir Microsoft hesabı oluşturma](https://signup.live.com/) ilgili tüm ayrıntıları ifşa değil. Raporunuzu oluşturmak için bu hesabı kullanın.

**Özel bir başlık ya da genel ilk rapor içeriğinin tutmak istediğiniz herhangi bir şey yerleştirmeyin.** Bunun yerine, ayrıntıları özel olarak ayrı bir açıklama için göndereceğiz varsayalım. Raporunuzu ve doğru kişiye yönlendirildiğinden emin olmak için dahil **cppcompiler** sorun raporunuzu Konu listesinde. Sorun raporu oluşturulduktan sonra artık kimlerin görebileceğini yanıtlar ve eklerini belirtmek mümkündür.

#### <a name="to-create-a-problem-report-for-private-information"></a>Özel bilgiler için bir sorun raporu oluşturmak için

1. Oluşturduğunuz bir raporda seçin **açıklama ekleme** özel, sorunun tanımı oluşturmak için.

1. Yanıt Düzenleyicisi'nde, aşağıdaki dropdown denetimi kullanın **Gönder** ve **iptal** yanıtınız hedef kitlesini belirtmek için düğmeler. Yalnızca belirttiğiniz kişilerin bu özel yanıtlar ve tüm görüntüleri, bağlantıları veya kod içine dahil görebilirsiniz. Seçin **Moderatörler ve özgün posteri Viewable** Microsoft çalışanları ve kendiniz için görünürlük sınırlamak için.

1. Açıklama ve tüm diğer bilgileri, görüntüleri ve dosya ekleri, yineleme için gereken ekleyin. Seçin **Gönder** özel olarak bu bilgileri göndermek düğmesi.

   En fazla 10 dosyaları ve ekli dosya çubuğunda 2GB sınırlaması yoktur. Tüm büyük karşıya yüklenmesi için istek bir yükleme URL'si, özel açıklama.

Bu açıklamayı altında bus'dan belirttiğiniz aynı kısıtlı görünürlük vardır. Yanıtları dropdown denetimi kısıtlı görünürlük durumunu doğru şekilde göstermiyor bile geçerlidir.

Gizliliğinizi korumak ve hassas bilgilerinizi genel görünümü dışında tutmak için dikkatli olun. Microsoft tüm etkileşim yanıtlara kısıtlı yorum altında tutun. Diğer açıklamaları yanıtlar hassas bilgilerin yanlışlıkla açığa neden olabilir.

## <a name="how-to-report-a-c-documentation-issue"></a>Bir C++ belgeleri sorun bildirme

GitHub sorunları belgelerimizde bildirilen sorunları izlemek için kullanırız. Şimdi GitHub sorunları doğrudan bu sayede bir içerik sayfasından Yazıcılar ve ürün ekipleri ile çok daha zengin bir şekilde etkileşim oluşturabilirsiniz. Bir belge, hatalı kod örneği, karmaşık bir açıklama, kritik bir atlama veya bile yalnızca bir yazım yanlışı ile ilgili bir sorun görürseniz, kolayca bize bildirin. Seçin ve sayfayı kaydırın **belgeler hakkında geri bildirimde bulunmak için oturum açın**. Zaten yoksa, bir GitHub hesabı oluşturmanız gerekir. Bir GitHub hesabı varsa, tüm bizim belgeleri sorunları ve bunların durumunu görebilirsiniz. Bildirdiğiniz sorun için değişiklik yapıldığında bildirimleri ayrıca Al. Daha fazla bilgi için [A yeni geri bildirim sistemi geliyor docs.microsoft.com](/teamblog/a-new-feedback-system-is-coming-to-docs).

Belge geri bildirim düğmesi kullandığınızda Github'da bir belge sorunu oluşturun. Sorunu, sorunu oluşturduğunuz sayfası hakkında bazı bilgiler otomatik olarak doldurulur. Sorun bu bilgileri düzenlemeyin şekilde bulunduğu nasıl biliyoruz olmasıdır. Yalnızca bir önerilen düzeltme yanlış ve isterseniz yenilikler hakkında ayrıntıları ekleyin. [Bizim C++ açık kaynak olan belgeleri](https://github.com/MicrosoftDocs/cpp-docs/), bu yüzden bir düzeltme kendinize göndermek istiyorsanız, aşağıdakileri yapabilirsiniz. Belgelerimize nasıl katkıda bulunabileceğinizi hakkında daha fazla bilgi için bkz. bizim [katkıda Kılavuzu](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) GitHub üzerinde.
