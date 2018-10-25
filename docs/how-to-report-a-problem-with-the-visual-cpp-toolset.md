---
title: Visual C++ araç takımı ile ilgili bir sorun bildirme | Microsoft Docs
ms.date: 06/21/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2ca0f4aa5f3965adc97e4cdaef09e01646e8809
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062125"
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset-or-documentation"></a>Visual C++ araç takımı veya belgeleri ile ilgili bir sorun bildirme

Microsoft Visual C++ Derleyici, bağlayıcı, veya diğer araçları ve kitaplıklarını sorunlarla karşılaşırsanız, bunları hakkında bilmek istiyoruz. Sorunu belgelerimizde ise, bu konuda, çok bilmek istiyoruz.

## <a name="how-to-report-a-c-toolset-issue"></a>Bir C++ araç takımı sorun bildirme

Bize nasıl programınızı oluşturuyorsunuz ve hakkında bir açıklama önce karşılaştığınız, sorunun ayrıntılarını içeren bir rapor göndermek için bir sorun hakkında bize bildirmek için en iyi yolu olan *yineleme*, yeniden oluşturmak için kullanabileceğiniz eksiksiz bir test çalışması kendi makinelerinde sorun oluştu. Bu bilgiler sorun bizim kodun içinde vardır ve ortamınız için derleyicinin diğer sürümlerini etkiler olup olmadığını belirlemek için ve nedenini tanılamak için yerel değil hızla doğrulamamıza olanak tanır.

Aşağıdaki bölümlerde, iyi bir rapor kılan, buldunuz sorun türü için bir yineleme oluşturmayı ve raporunuzda ürün ekibine göndermek nasıl hakkında bilgi edinin. Raporlarınızı bize ve sizin gibi diğer geliştiriciler için önemlidir. Visual C++ geliştirmemize yardımcı olmak için teşekkür ederiz!

## <a name="how-to-prepare-your-report"></a>Raporunuzu hazırlamayı öğrenin

Tüm bilgiler olmadan kendi makinelerinde karşılaştığınız sorunu yeniden oluşturmak oldukça zor olduğundan, yüksek kaliteli rapor oluşturma önemlidir. Daha iyi raporunuzu, daha etkili bir şekilde biz mümkün yeniden oluşturun ve sorunu tanılayın.

En azından raporunuza içermelidir

- Tam sürüm bilgisi kullandığınız araç.

- Kodunuzu derlemek için kullanılan tam cl.exe komut satırı.

- Karşılaştığınız sorunun ayrıntılı bir açıklaması.

- Bir yineleme: sorunu gösteren bir tam, Basitleştirilmiş, kendi içindeki kaynak kod örneği.

İçin okumaya devam ihtiyacımız belirli bilgiler hakkında daha fazla bilgi edinin ve burada bulabilirsiniz ve nasıl iyi bir yineleme oluşturun.

### <a name="the-toolset-version"></a>Araç takımının sürüm

Tam sürüm bilgilerini ve sorun neden olur ve böylece müşterilerimize makinelere karşı aynı araç takımı, yineleme sınayabiliriz araç hedef mimari ihtiyacımız var. Sorunu yeniden oluşturabileceğinizi, bu bilgileri bize ayrıca diğer hangi sürümlerinin araç takımı ek aynı sorunu araştırmak için bir başlangıç noktası sunar.

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>Kullanmakta olduğunuz Derleyici tam sürümünü bildirmek için

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir. Örneğin, üzerinde x64 x64 için Visual Studio 2017 kullanarak yapı hedefleri seçin **x64 VS 2017 için yerel Araçlar komut istemi**. Daha fazla bilgi için [Geliştirici komut istemi kısayolları](build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /Bv**.

Çıktı şuna benzer görünmelidir:

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

Tam biz bunu tam olarak aynı şekilde bizim makinelerde oluşturabilmeleri, kodunuzu derlemek için kullanılan komut satırı (cl.exe ve tüm bağımsız değişkenleri) ihtiyacımız var. Karşılaştığınız sorunu yalnızca belirli bir bağımsız değişken veya bağımsız değişken bileşimine oluştururken olabileceğinden, bu önemlidir.

Bu bilgileri bulmak için en iyi derleme günlüğünde sorunlu hemen sonra yerdir. Bu komut satırı sorunu katkıda bulunan tam olarak aynı bağımsız değişkenler içeren sağlar.

#### <a name="to-report-the-contents-of-the-command-line"></a>Komut satırının içeriğini bildirmek için

1. Bulun **CL.command.1.tlog** dosya ve açın. Varsayılan olarak, bu dosya, Belgeler klasöründe bulunan \\Visual Studio *sürüm*\\projeleri\\*SolutionName* \\ *ProjectName*\\*yapılandırma*\\*ProjectName*.tlog\\CL.command.1.tlog, veya kullanıcı klasörünüzün altında \\Kaynak\\depoları\\*SolutionName*\\*ProjectName*\\*yapılandırma* \\ *ProjectName*.tlog\\CL.command.1.tlog. Başka bir yapı sistemi kullanırsanız veya varsayılan konumu, projeniz için değiştirdiyseniz, farklı bir konumda olabilir.

   İçinde bu dosya, kaynak kodu dosyaları her ayrı satırlarda onları, derlemek için kullanılan komut satırı bağımsız değişkenleri ardından adlarını bulabilirsiniz.

1. Sorunun gerçekleştiği kaynak kodu dosyasının adını içeren satırı bulun; aşağıdaki satırda karşılık gelen cl.exe komut satırı bağımsız değişkenlerini alır.

Kopyalayıp raporunuzda tüm komut satırı yapıştırabilirsiniz.

### <a name="a-description-of-the-problem"></a>Sorun açıklaması

Biz makinelerimiz aynı etkisini görüyoruz doğrulayabilir karşılaştığınız sorunun ayrıntılı bir açıklaması ihtiyacımız; Bunun da bazen yararlı bize ne yapmaya çalıştığınızı ve olmasını beklediğinizi bilmek için.

Lütfen **tam hata iletileri** araç takımı veya gördüğünüz tam çalışma zamanı davranışı. Biz düzgün sorun yeniden olduğunu doğrulamak için bu bilgiye ihtiyacımız var. Lütfen dahil **tüm** çıkışı, derleyicinin yalnızca son hata iletisi. Soruna raporu açan her şeyi görmek ihtiyacımız var. Komut satırı derleyicisini kullanarak sorunu çoğaltabilirsiniz ise, derleyici çıkışını tercih edilir; IDE ve diğer yapı sistemi bakın veya yalnızca ilk satır bir hata iletisinin yakalama hata iletilerini filtreleyebilirsiniz.

Lütfen sorunu derleyici geçersiz kod kabul eder ve bir tanılama oluşturmaz, Bu raporda unutmayın.

Çalışma zamanı davranışı sorun bildir, eklenecek bir **tam kopya** program yazdırır ve görmeyi beklediğiniz. Bu çıkış deyiminde kendisi, örneğin, ideal olarak, katıştırılmış `printf("This should be 5: %d\n", actual_result);`. Programınızı kilitlenmesine veya yanıt vermemeye başlıyor, bu da söz.

Tüm alamadığınızı görebilirsiniz belgele gibi karşılaştığınız sorunu çözmemize yardımcı olabilecek diğer ayrıntıları tanılama ekleyin. Raporunuzda başka bir yerde bulunan bilgileri yinelemekten kaçının.

### <a name="the-repro"></a>Yineleme

Bir yineleme tekrarlanarak önce karşılaştığınız sorunu gösteren bir tam ve müstakil kaynak kod örneği olduğunu (Bu nedenle adı). Böylece hata bizim makinelerde üretebileceği istiyorduk ihtiyacımız var. Kodu derler ve çalıştırır ya da çalıştırmak ve derleme basit bir yürütülebilir dosyayı oluşturmak için kendisi tarafından kullanılmıyorsa, buldunuz sorun için yeterli olmalıdır. Bir yineleme, bir kod parçacığı değil; tam işlevleri ve sınıfları olması ve tüm gerekli içeren # standart üstbilgi için bile include.

#### <a name="what-makes-a-good-repro"></a>İyi bir yineleme yapan nedir

İyi bir yineleme aşağıdaki gibidir:

- **En az.** Oluşturmalar, olabildiğince az henüz yine de tam olarak karşılaştığınız sorunu gösterir. Oluşturmalar karmaşık veya gerçekçi olması gerekmez; Bunlar yalnızca standart veya belgelenmiş derleyici uygulaması veya bir tanılama eksik olması durumunda uyan kodu, uyumlu olmayan kodu göstermek için gerekir. Sorun göstermek için yeterli kodu içeren basit, için öz oluşturmalar idealdir. Lütfen kaldırın veya kod basitleştirebilir ve uyumlu kalır ve ayrıca sorun değiştirmeden bırakın, bunu yapın. Karşı çalışan kod örnekleri gerekmez.

- **Kendi içinde.** Oluşturmalar gereksiz bağımlılıkları kaçınmanız gerekir. Sorun olmadan üçüncü taraf kitaplıklar yeniden oluşturabiliyorsanız, lütfen bunu yapın. Basit çıkış deyimleri yanı sıra herhangi bir kitaplık kodu olmadan sorunu yeniden oluşturabileceğinizi varsa (örneğin, `puts("this shouldn't compile");`, `std::cout << value;`, ve `printf("%d\n", value);` sorunsuz), lütfen bunu yapın. Örnek bir tek kaynak kod dosyasına başvuru kullanıcı üst bilgileri olmadan sıkıştırılmış durumunda idealdir. Biz sorunun olası bir katılımcı olarak göz önünde bulundurmanız gereken kod miktarını azaltarak bize artık çok yararlı olur.

- **Karşı derleyici en son sürümü.** Oluşturmalar en son güncelleştirmeye araç takımı en son sürümünü veya sonraki güncelleştirmesi veya sonraki ana sürümüne, mümkün olduğunda en son yayın öncesi sürümünü kullanmanız gerekir. Araç eski sürümlerinde karşılaşabileceğiniz sorunlara daha yeni sürümlerde çok sık düzelttik. Düzeltmeleri backported olağanüstü durumlarda yalnızca eski sürümleri için olan.

- **Diğer derleyiciler karşı kullanıma** varsa. Taşınabilir C++ kodu içeren oluşturmalar davranışı diğer derleyiciler karşı mümkünse doğrulamanız gerekir. Standart program doğruluk, nihai olarak belirler ve derleyici mükemmel değildir, ancak Clang ve GCC, kodunuzu bir tanılama olmadan kabul MSVC yok, bizim derleyici bir hata, aradığınız olma olasılığı yüksektir. (Diğer bir olasılık Unix ve Windows davranış veya C++ standartları uygulama farklı düzeylerde farklılıkları dahil vb..) Tüm derleyiciler kodunuz reddederseniz, diğer taraftan, daha sonra kodunuzu yanlış olduğunu olasıdır. Farklı hata iletilerini görme sorunu kendiniz tanılamaya yardımcı olabilir.

   Kodunuzu karşı test etmek için çevrimiçi derleyiciler listesini bulabilirsiniz [çevrimiçi C++ Derleyicileri](https://isocpp.org/blog/2013/01/online-c-compilers) ISO C++ Web sitesi ya da bu seçkin [çevrimiçi C++ Derleyicileri listesi](https://arnemertz.github.io/online-compilers/) GitHub üzerinde. Belirli bazı örnekler [Wandbox](https://wandbox.org/), [derleyici Gezgini](https://godbolt.org/), ve [Coliru](http://coliru.stacked-crooked.com/).

   > [!NOTE]
   > Microsoft ile çevrimiçi derleyicisindeki Web siteleri bağlı değil. Birçok çevrimiçi derleyicisindeki Web sitesi kişisel projeleri çalıştırılır ve bu siteleri bazıları bunu okuyun, ancak diğerleri kullanabileceğiniz bir arama bulmanız gerekir kullanılamıyor olabilir.

Sorunları derleyici, bağlayıcı ve kitaplıklarında, kendisini özellikle yollarını göstermektedir eğilimindedir. Ne tür bir yineleme raporunuzda içermelidir. karşılaştığınız sorun türünü belirler. Uygun bir yineleme araştırmak için hiçbir şey sahibiz. Birkaç türde karşılaşabileceğiniz sorunları ve her tür sorunları bildirmek için kullanmalısınız oluşturmalar türlerini oluşturmak için yönergeler aşağıda verilmiştir.

#### <a name="frontend-parser-crash"></a>Kilitlenme ön uç (ayrıştırıcı)

Ön uç kilitlenmeler, derleyici ayrıştırma işlemi sırasında oluşur. Genellikle, derleyici yayar [önemli hata C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) ve başvuru, bir hata oluştu; genellikle bir dosya msc1.cpp bahsedecektir, ancak bu ayrıntı sayabilirsiniz kaynak kod dosya ve satır numarası.

Kilitlenme bu tür için lütfen belirtin bir [önceden işlenmiş yineleme](#preprocessed-repros).

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

Arka uç kilitlenmeleri kod derleyici oluşturma aşaması sırasında oluşur. Genellikle, derleyici yayar [önemli hata C1001](error-messages/compiler-errors-1/fatal-error-c1001.md)ve değil kaynak kodu dosyasının başvuru ve satır numarası sorunla ilişkili; genellikle dosya derleyici bahsedecektir\\utc\\src\\p2\\main.c, ancak bu ayrıntı yok sayabilirsiniz.

Kilitlenme bu tür için lütfen belirtin bir [bağlantı yineleme](#link-repros) bağlama sırasında kod oluşturma (LTCG) kullanıyorsanız, etkin **/GL** cl.exe komut satırı bağımsız değişkeni. Aksi takdirde, lütfen belirtin bir [yineleme önceden işlenmiş](#preprocessed-repros) yerine.

LTCG kullanılmadığı bir arka uç kilitlenme için derleyici çıktı örneği aşağıda verilmiştir. Derleme çıkışınızı gibi görünüyorsa sağlamalıdır bir [önceden işlenmiş yineleme](#preprocessed-repros).

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

Çizgi ile başlayan, **iç derleyici hatası** link.exe bahsetmeleri yerine cl.exe'yi LTCG etkinleştirildi ve sağlamanız bir [bağlantı yineleme](#link-repros). Varsa, not için bir önceki adımda Temizle LTCG derleyici hata iletisindeki etkin olup olmadığını ihtiyacınız olabilecek incelemek, yapıdan kopyaladığınız komut satırı bağımsız değişkenleri oturum **/GL** komut satırı bağımsız değişkeni.

#### <a name="linker-crash"></a>Bağlayıcı kilitlenme

Bağlayıcı kilitlenmeleri derleyici çalıştırdıktan sonra bağlama işlemi sırasında oluşur. Genellikle, bağlayıcı yayar [Bağlayıcı araçları hatası LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md).

> [!NOTE]
> Çıkış C1001 bahsetmeleri veya bağlama zamanı kod oluşturmayı içerir, başvurmak [arka uç (kod oluşturma) kilitlenme](#backend-code-generation-crash) bunun yerine daha fazla bilgi için.

Kilitlenme bu tür için lütfen belirtin bir [bağlantı yineleme](#link-repros).

Bu tür bir kilitlenme için derleyici çıktı örneği aşağıda verilmiştir.

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

Artımlı bağlamayı etkindir ve yalnızca başarılı başlangıç, bir bağlantı sonra kilitlenme oluştu (diğer bir deyişle, yalnızca ilk tam, artımlı bağlamaya temel bağlama sonra) Lütfen ' % s'nesne (.obj) bir kopyasını da sağlayın ve kitaplık (.lib) dosyaları ilk bağlantı tamamlandıktan sonra değiştirilen kaynak dosyalarına karşılık gelir.

#### <a name="bad-code-generation"></a>Hatalı kod oluşturma

Hatalı kod oluşturma nadir görülen bir durumdur, ancak derleyici yanlışlıkla uygulamanızın derleme zamanında bu sorunu algılama yerine çalışma zamanı kilitlenmesine neden olacak yanlış kod oluşturduğunda gerçekleşir. Hatalı kod oluşturma sonuçlarını yaşıyor sorunu düşünüyorsanız, raporunuzu aynı şekilde işlem bir [arka uç (kod oluşturma) kilitlenme](#backend-code-generation-crash).

Bu tür bir kilitlenme için lütfen belirtin bir [bağlantı yineleme](#link-repros) bağlama sırasında kod oluşturma (LTCG) kullanıyorsanız, etkin **/GL** cl.exe komut satırı bağımsız değişkeni. Lütfen bir [yineleme önceden işlenmiş](#preprocessed-repros) Aksi takdirde.

## <a name="how-to-generate-a-repro"></a>Bir yineleme oluşturma

Sorunun kaynağını izlemenize yardımcı olmak için bir [iyi yineleme](#what-makes-a-good-repro) yaşamsal önem taşır. Tüm oluşturmalar belirli türdeki özetlenen adımları uygulamadan önce mümkün olduğunca sorunu gösteren kod Daralt deneyin. Kaldırın veya bağımlılıkları, gerekli üst bilgileri ve kitaplıkları en aza indirmek ve derleyici seçenekleri ve mümkünse kullanılan önişlemci tanımlarını deneyin.

Raporu farklı türde sorunları için kullanacağınız oluşturmalar çeşitli türleri oluşturmak için yönergeler aşağıda verilmiştir.

### <a name="preprocessed-repros"></a>Önceden işlenmiş oluşturmalar

A *yineleme önceden işlenmiş* C önişlemcisinin çıktısından kullanılarak oluşturulan bir sorunu gösterir bir tek bir kaynak dosyası **/P** özgün yineleme kaynak dosyada derleyici seçeneği. Bu satır içleri ek kaynağı ve başlık dosyaları bağımlılıkları kaldırmak için üstbilgileri dahil ve makrolar, #ifdefs ve yerel ortamınızda bağımlı diğer önişlemci komutlarını da giderir.

> [!NOTE]
> Genellikle zaten sorunu düzelttik olup olmadığını görmek için en son, devam eden kararlılığımızın yerine istediğimizden, önceden işlenmiş oluşturmalar hataları standart kitaplığı kararlılığımızın bir sonucu olabilir sorunları için faydalı değildir. Bu durumda, yineleme önişle yoktur ve azaltırsanız olamaz, tek bir kaynak dosyası, sorunu kodunuzu veya benzer bir .zip dosyasına paketleyin veya bir IDE proje yineleme kullanmayı düşünün. Daha fazla bilgi için [diğer oluşturmalar](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Bir kaynak kodu dosyası ön işleme için

1. Açıklandığı gibi bir yineleme oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir.

1. Repro projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /P** *bağımsız değişkenleri* *filename.cpp*burada *bağımsız değişkenleri* olduğu Yukarıdaki yakalanan bağımsız değişkenlerinin listesi ve *filename.cpp* yineleme kaynak dosyanın adıdır. Bu komut yineleme için kullanılan komut satırı çoğaltır, ancak derleme önişlemci geçişi sonrasında durdurur ve önceden işlenmiş kaynak koduna çıkarır *filename*. ediyorum.

C + işleniyorsa +/ CX kaynak kodu dosyası veya C++ modülleri özelliğinin kullanıyorsanız, bazı ek adımlar gereklidir. Daha fazla bilgi için aşağıdaki bölümlere bakın.

Önceden işlenmiş dosyayı oluşturduktan sonra bunu emin olmak için iyi bir fikirdir önceden işlenmiş dosyayı kullanarak sorunu hala oluşturmalar.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Onaylamak için hata önceden işlenmiş dosyayı oluşturmalar hala

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl** *bağımsız değişkenleri* **/TP** *filename*.i derlemek için cl.exe bildirmek için önceden işlenmiş dosyayı bir C++ kaynak dosyası olarak nerede *bağımsız değişkenleri* yukarıda, ancak tüm yakalanan bağımsız değişkenler listesi **/D** ve **/I** (çünkü bağımsız değişkenleri kaldırıldı Bunlar zaten önceden işlenmiş dosyayı dahil edilmiş); ve nerede *filename*.i, önceden işlenmiş dosya adıdır.

1. Sorunu yeniden olduğunu onaylayın.

Son olarak, önceden işlenmiş yineleme ekleme *filename*.i raporunuza.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Önceden işlenmiş C + +/ CX WinRT/UWP kod oluşturmalar

C + kullanıyorsanız +/ CX yürütülebilir dosyanızı oluşturmak için oluşturma ve önceden işlenmiş istiyorduk doğrulamak için gereken bazı ek adımlar vardır.

#### <a name="to-preprocess-ccx-source-code"></a>İçin önceden işlenir C + +/ CX kaynak kodu

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

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /P** *bağımsız değişkenleri* *filename.cpp*burada *bağımsız değişkenleri* olduğu Yukarıdaki yakalanan bağımsız değişkenlerinin listesi ve *filename.cpp* modülünü kullanan kaynak dosyasının adıdır.

1. Modül arabirimi (.ifc çıkış) yerleşik yineleme projesini içeren dizine geçin.

1. Bir modül arabirimi oluşturmak için kullanılan komut satırı bağımsız değişkenlerini yakalar.

1. Geliştirici komut istemi konsol penceresinde komutu girin **cl /P** *bağımsız değişkenleri* *modulename.ixx*burada *bağımsız değişkenleri* olduğu Yukarıdaki yakalanan bağımsız değişkenlerinin listesi ve *modulename.ixx* modül arabirimi oluşturan dosyanın adıdır.

Önceden işlenmiş dosya oluşturduktan sonra önceden işlenmiş dosyayı kullanarak sorunu hala oluşturmalar emin olmak için iyi bir fikirdir.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Onaylamak için hata önceden işlenmiş dosyayı oluşturmalar hala

1. Geliştirici konsol penceresinde geri yineleme projenizi içeren dizine geçin.

1. Komutu girdikten **cl** *bağımsız değişkenleri* **/TP** *filename*.i C++ kaynak dosyası gibi önceden işlenmiş dosya derlemek için yukarıdaki gibi.

1. Sorunu hala tarafından önceden işlenmiş dosyayı yeniden onaylayın.

Son olarak, önceden işlenmiş yineleme dosya ekleme (*filename*.i ve *modulename*.i) raporunuza .ifc çıkış yanı sıra.

### <a name="link-repros"></a>Bağlantı oluşturmalar

A *yineleme bağlantısını* bağlayıcı tarafından oluşturulan içeriği tarafından belirtilen bir dizinin **bağlantı\_yineleme** ortam değişkeni. Bu, bağlama sırasında kod oluşturma (LTCG) içeren bir arka uç kilitlenme veya bir bağlayıcı kilitlenme gibi bağlantı zaman ortaya çıkan bir sorun topluca gösteren derleme yapıtları içerir. Bu derleme yapıları olan sorunu yeniden kombinasyonlarına bağlayıcı gerekli olanlar. Bağlantı istiyorduk bağlayıcı yerleşik yineleme oluşturma özelliğini etkinleştirmek için bu ortam değişkeni kullanarak, kolayca yeniden oluşturulabilir.

#### <a name="to-generate-a-link-repro"></a>Bir bağlantı yineleme oluşturmak için

1. Açıklandığı gibi bir yineleme oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümünüz ve yapılandırmanız mimarisi ile eşleşir.

1. Geliştirici komut istemi konsol penceresinde yineleme projenizi içeren dizine geçin.

1. Girin **mkdir linkrepro** bağlantı yineleme için bir dizin oluşturmak için.

1. Komutu girdikten **bağlantı ayarlayın\_yineleme linkrepro =** ayarlamak için **bağlantı\_yineleme** yeni oluşturduğunuz dizine ortam değişkeni. Genellikle daha karmaşık projeler için olduğu gibi farklı bir dizinden derleme çalışırsa ayarlayın **bağlantı\_yineleme** linkrepro dizinine tam yolu için bunun yerine.

1. Geliştirici komut istemi konsol penceresinde, Visual Studio'da aracındaki Projeyi derlemek için komutu girin **devenv**. Bu değeri sağlar **bağlantı\_yineleme** ortam değişkenidir Visual Studio'da görünür. Komut satırından Projeyi derlemek için yineleme derleme çoğaltmak için yukarıda yakalanan komut satırı bağımsız değişkenlerini kullanın.

1. Repro projenizi derleyin ve beklenen sorunu oluştu onaylayın.

1. Derleme gerçekleştirmek için kullanılan Visual Studio'yu kapatın.

1. Geliştirici komut istemi konsol penceresinde komutu girin **bağlantı ayarlayın\_yineleme =** temizlemek için **bağlantı\_yineleme** ortam değişkeni.

Son olarak, tüm linkrepro dizin bir .zip dosyasına veya benzer sıkıştırarak yineleme paketini ve raporunuza ekleyin.

### <a name="other-repros"></a>Diğer oluşturmalar

Tek bir kaynak dosyası ya da önceden işlenmiş yineleme sorun indiremezsiniz ve sorunun bir bağlantısını yineleme gerektirmez, biz bir IDE proje araştırabilirsiniz. Tüm kılavuzuna nasıl iyi bir yineleme oluşturmak hala geçerlidir; kodun en son araçlarımızı sorun oluşması minimal ve kendi içinde olması ve uygunsa, sorun diğer derleyicilerde görülmeyen.

Minimal bir IDE proje olarak, yineleme oluşturun, sonra tüm dizin yapısının bir .zip dosyasına veya benzer sıkıştırarak paketini ve raporunuza ekleyin.

## <a name="ways-to-send-your-report"></a>Raporunuzu gönderme yolları

Birkaç raporunuzu bize almak için iyi bir yolu vardır. Visual Studio'nun yerleşik kullanabileceğiniz [sorun rapor](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017), veya [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sayfaları. Geliştirici topluluğu sayfalarımızın doğrudan seçerek de elde edebilirsiniz **ürün geri bildirimi** bu sayfanın alt kısmındaki düğmesi. Seçimi ekran görüntüsü yakalamayı ve geliştirici topluluğu sayfalarında posta raporunuzun düzenleme IDE yerleşik Araçlar'ı kullanmak isteyip istemediğinizi veya doğrudan Web sitesini kullanmayı tercih ederseniz bağlıdır.

> [!NOTE]
> Raporunuzu nasıl gönderdiğiniz bağımsız olarak Microsoft, gizliliğinize saygı duyar. Microsoft tüm veri gizlilik yasalarına ve düzenlemelerine uyumluluğa taahhüt eder. Biz bize verileri nasıl kabul hakkında daha fazla bilgi için bkz: [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement).

### <a name="use-the-report-a-problem-tool"></a>Sorun raporu kullanın

**Sorun bildir** aracı Visual Studio'da Visual Studio kullanıcıların yalnızca birkaç tıklama ile ilgili sorunlar çeşitli rapor bir yoldur. Bu, karşılaştığınız ve sonra raporunuzu IDE'den çıkmadan gönderin sorun hakkında ayrıntılı bilgi belirtmek için kullanabileceğiniz basit bir form sağlar.

Sorununuzu aracılığıyla raporlama **sorun bildir** araçtır IDE'den kolay. Başlık Çubuğu'ndan seçerek erişebildiğinizi **geri bildirim gönder** yanındaki simge **hızlı başlatma** arama kutusu veya bulabilir, menü çubuğunda **yardımcı**  >  **Geri bildirim gönder** > **sorun bildir**.

Önce bir sorunu bildirmek seçtiğinizde, benzer sorunlarla ilgili Geliştirici topluluğu arayın. Sorununuzu daha önce bildirildiyse konu oylamak ve açıklamalar ile ek özellikleri ekleyin. Benzer bir sorun görmüyorsanız seçin **yeni sorun bildirme** düğme Visual Studio geri bildirim iletişim kutusunun alt kısmında ve sorununuzu bildirmek için adımları izleyin.

### <a name="use-the-visual-studio-developer-community-pages"></a>Visual Studio Geliştirici topluluğu sayfalarını kullanma

Visual Studio Geliştirici topluluğu sayfaları sorunları bildirme ve Visual Studio ve C++ Derleyici, araçları ve kitaplıkları için çözüm bulmak için başka bir uygun yoldur. Belirli bir geliştirici topluluğu sayfa için [Visual Studio](https://developercommunity.visualstudio.com/spaces/8/index.html), [Mac için Visual Studio](https://developercommunity.visualstudio.com/spaces/41/index.html), [.NET](https://developercommunity.visualstudio.com/spaces/61/index.html), [C++](https://developercommunity.visualstudio.com/spaces/62/index.html), [ Azure DevOps](https://developercommunity.visualstudio.com/spaces/21/index.html), ve [TFS](https://developercommunity.visualstudio.com/spaces/22/index.html). Her sayfanın üst kısmındaki aşağıdaki sekmelerden altındaki gönderileri veya benzer bir sorun bildirin konuları bulmak için kullanabileceğiniz bir arama kutusu var. Bir çözüm veya sorununuz için ilgili diğer yararlı bilgiler zaten bulunduğunu fark edebilirsiniz. Birisi aynı sorunla daha önce bildirmediyse, lütfen oylamak ve bu konuyla ilgili yorum yerine yeni bir sorun raporu oluşturun. Yorum yapmak için oy verin veya yeni bir sorun bildirmek için Visual Studio hesabınızda oturum açın ve profiliniz için geliştirici topluluğu uygulama erişimi vermek kabul etmeniz istenebilir.

C++ Derleyici, bağlayıcı ve diğer araçlar ve kitaplıkların kullanımı ile ilgili sorunlar için [C++](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfası. Sorununuz için arama yapın ve bunu önce bildirilen taşınmadığından, seçim **sorun bildir** sayfanın üstündeki arama kutusunun yanındaki düğmeyi. Repro kodunuzu ve komut satırı, ekran görüntüleri, ilgili tartışmalar için bağlantıları ve düşündüğünüz faydalı ve ilgili diğer bilgileri içerebilir.

> [!TIP]
> Diğer tür sorunları için Visual Studio'da C++ araç takımını (IDE işlevi veya genel kilitlenmeler gibi kullanıcı Arabirimi sorunları,), ilgili olmayan kullanım karşılaşabileceğiniz **sorun bildir** IDE'de araç. Ekran görüntüsü özelliklerini ve karşılaştığınız sorunu neden UI eylemlerini kaydedin yeteneğini nedeniyle en iyi seçenek budur. Bu tür hatalara da üzerinde aranabilir [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) site. Daha fazla bilgi için [Visual Studio ile ilgili bir sorun bildirme](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017).

### <a name="reports-and-privacy"></a>Raporlar ve gizlilik

Varsayılan olarak, **tüm bilgiler, raporlar ve yorumlar ve yanıtları herkese görünür**. Sorunları, çözümler ve diğer kullanıcıların bulduğunuz geçici çözümleri görmek tüm topluluğuna izin verdiğinden normalde, bir avantajı budur. Ancak, verileriniz veya kimliğini, gizlilik veya fikri mülkiyet hakları nedeniyle, genel yapma hakkında endişeleriniz varsa seçeneğiniz vardır.

Kimliğinizi göstermeden hakkında endişeleriniz varsa [yeni bir Microsoft hesabı oluşturma](https://signup.live.com/) ilgili tüm ayrıntıları açıklamaz. Raporunuzu oluşturmak için bu hesabı kullanın.

**Özel bir başlık ya da genel ilk rapor içeriğinin tutmak istediğiniz herhangi bir şey yerleştirmeyin.** Bunun yerine, ayrıntıları özel olarak ayrı bir açıklama için gönderir unutmayın. Raporunuzu ve doğru kişiye yönlendirildiğinden emin olmak için dahil **cppcompiler** sorun raporunuzu Konu listesinde. Sorun raporu oluşturulduktan sonra artık kimlerin görebileceğini yanıtlar ve eklerini belirtmek mümkündür.

#### <a name="to-create-a-problem-report-for-private-information"></a>Özel bilgiler için bir sorun raporu oluşturmak için

1. Oluşturduğunuz bir raporda seçin **açıklama ekleme** özel, sorunun tanımı oluşturmak için.

1. Yanıt Düzenleyicisi'nde, aşağıdaki dropdown denetimi kullanın **Gönder** ve **iptal** yanıtınız hedef kitlesini belirtmek için düğmeler. Yalnızca belirttiğiniz kişilerin bu özel yanıtlar ve tüm görüntüleri, bağlantıları veya kod içine dahil görebilirsiniz. Seçin **Moderatörler ve özgün posteri Viewable** Microsoft çalışanları ve kendiniz için görünürlük sınırlamak için.

1. Açıklama ve tüm diğer bilgileri, görüntüleri ve dosya ekleri, yineleme için gereken ekleyin. Seçin **Gönder** özel olarak bu bilgileri göndermek düğmesi.

   Ekli dosyalar ve 10 dosyaları en fazla 2 GB sınırlı olduğunu unutmayın. Daha büyük tüm yüklemeler için lütfen bir yükleme URL'si, özel açıklama isteyin.

Bu açıklamayı altında bus'dan belirttiğiniz aynı kısıtlı görünürlük vardır. Dropdown denetimi yanıtlar üzerinde sınırlı görünürlük durumu doğru şekilde göstermez olsa bile bu geçerlidir.

Gizliliğinizi korumak ve hassas bilgilerinizi genel görünümü dışında tutmak için lütfen Microsoft ile tüm etkileşim yanıtlara bu kısıtlı açıklama altında tutmak için dikkatli olun. Diğer açıklamaları yanıtlar hassas bilgilerin yanlışlıkla açığa neden olabilir.

## <a name="how-to-report-a-c-documentation-issue"></a>Bir C++ belgeleri sorun bildirme

GitHub sorunları belgelerimizde bildirilen sorunları izlemek için kullanırız. Şimdi GitHub sorunları doğrudan bu sayede bir içerik sayfasından Yazıcılar ve ürün ekipleri ile çok daha zengin bir şekilde etkileşim oluşturabilirsiniz. Bir belge, hatalı kod örneği, karmaşık bir açıklama, kritik bir atlama veya bile yalnızca bir yazım yanlışı ile ilgili bir sorun görürseniz, kolayca bize bildirin. Seçin ve sayfayı kaydırın **belgeler hakkında geri bildirimde bulunmak için oturum açın**. Zaten yoksa, ancak bunu yaptığınızda, tüm bizim belgeleri sorunları, bunların durumunu görmek ve bildirdiğiniz sorun için değişiklik yapıldığında bildirim alma bir GitHub hesabı oluşturmanız gerekir. Daha fazla bilgi için [A yeni geri bildirim sistemi geliyor docs.microsoft.com](/teamblog/a-new-feedback-system-is-coming-to-docs).

Belge geri bildirim düğmesini kullanarak bir belge sorunu Github'da oluşturduğunuzda, sorunun nerede olduğunu biliyoruz. Bu nedenle sorun sorunu, oluşturulan sayfaya hakkında bazı bilgiler ile otomatik olarak doldurulur. Lütfen bu bilgileri düzenlemeyin. Yalnızca bir önerilen düzeltme yanlış ve isterseniz nedir hakkında ayrıntılı bilgi ekleyin. [Belgelerimizi açık kaynaklıdır](https://github.com/MicrosoftDocs/cpp-docs/), aslında bir düzeltme yapıp kendiniz önermek isterseniz, bunu yapabilirsiniz. Belgelerimize nasıl katkıda bulunabileceğinizi hakkında daha fazla bilgi için bkz. bizim [katkıda Kılavuzu](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) GitHub üzerinde.

