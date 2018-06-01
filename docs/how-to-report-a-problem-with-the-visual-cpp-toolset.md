---
title: Visual C++ araç takımını ile ilgili bir sorun bildirme | Microsoft Docs
ms.date: 5/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0044a0da7b1ac4ad052eb120ccfb1f7425d2c0e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34336337"
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset-or-documentation"></a>Visual C++ araç takımını veya belgelerinde bir sorun bildirme

Microsoft Visual C++ Derleyici, bağlayıcı, veya diğer araçlar ve kitaplıkları sorunlarla karşılaşırsanız, bunları hakkında bilmek isteriz. Sorun Belgelerimizdeki ise, hakkında çok bilmek isteriz.

## <a name="how-to-report-a-c-toolset-issue"></a>C++ araç takımını sorun bildirme

Bir sorun hakkında bilmeniz bize en iyi yolu bize programınızı oluşturmakta olduğunuz nasıl ve bir hakkında hatayla karşılaşıldı, Ayrıntılar sorun açıklamasını içeren bir rapor göndermektir *yeniden oluşturma*, yeniden oluşturmak için kullanabileceğiniz eksiksiz bir test çalışması sorunu kendi makinelerde. Bu bilgiler sorunu bizim kodda var ve ortamınız için derleyici'nin diğer sürümlerini etkiler olup olmadığını belirlemek ve nedenini tanılamak için yerel değil hızla doğrulamamıza olanak sağlar.

Aşağıdaki bölümlerde, iyi bir rapor kılan, yeniden oluşturma, buldunuz sorunu tür oluşturmak nasıl ve ürün ekibine raporunuzu göndermek nasıl okumanız. Raporlarınızı bize ve sizin gibi diğer geliştiriciler için önemlidir. Visual C++ geliştirmemize yardımcı olduğunuz için teşekkür ederiz!

## <a name="how-to-prepare-your-report"></a>Raporunuzu hazırlama

Tam bilgisi olmadan kendi makinelerde karşılaştığınız sorunu yeniden oluşturmak oldukça zor olduğundan, yüksek kaliteli rapor oluşturma önemlidir. Daha iyi raporunuzu, daha etkili bir şekilde biz olan mümkün yeniden oluşturun ve sorunu tanılamak.

En azından raporunuzu içermelidir

- Kullanmakta olduğunuz araç takımı tam sürüm bilgileri.

- Kodunuzu oluşturmak için kullanılan tam cl.exe komut satırı.

- Karşılaşılan sorunla ayrıntılı bir açıklaması.

- Bir yeniden oluşturma: sorunu gösteren tam, Basitleştirilmiş, kendi içinde bulunan kaynak kodu örneği.

İçin okumaya ihtiyacımız belirli bilgiler hakkında daha fazla bilgi ve burada bulabilirsiniz ve iyi bir yeniden oluşturma oluşturma.

### <a name="the-toolset-version"></a>Araç takımının sürüm

Tam sürüm bilgileri ve sorunu neden olur ve böylece, yeniden oluşturma aynı araç takımı karşı bizim makinelerde sınayabilirsiniz araç takımı hedef mimarisini ihtiyacımız var. Sorunu yeniden, bu bilgileri bize Ayrıca hangi bir araç takımı Sergi aynı sorun sürümlerinin araştırmak için bir başlangıç noktası sunar.

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>Kullanmakta olduğunuz derleyici'nın tam sürümünü bildirmek için

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisi ile eşleşir. Örneğin, Visual Studio 2017 üzerinde x64 için x64 kullanarak yapılandırdıysanız hedefleri seçin **x64 VS 2017 için yerel Araçları Komut İstemi**. Daha fazla bilgi için bkz: [Geliştirici komut istemi kısayolları](build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

1. Geliştirici komut istemi konsol penceresinde aşağıdaki komutu girin **cl /Bv**.

Çıktı aşağıdakine benzer görünmelidir:

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

Kopyalayabilir ve tüm çıktı raporunuzu yapıştırabilirsiniz.

### <a name="the-command-line"></a>Komut satırı

Tam biz bunu tam olarak aynı şekilde bizim makinelerde oluşturabilmeleri, kodunuzu oluşturmak için kullanılan komut satırı (cl.exe ve tüm bağımsız değişkenler) ihtiyacımız var. Karşılaşılan sorunla yalnızca belirli bir bağımsız değişken veya bağımsız değişkenler bileşimi ile oluştururken olabileceğinden, bu önemlidir.

Bu bilgileri bulmak için en iyi derleme günlüğünde sorunlu hemen sonra yerdir. Bu komut satırı sorunu katkıda bulunan tam olarak aynı bağımsız değişkenler içeriyor sağlar.

#### <a name="to-report-the-contents-of-the-command-line"></a>Komut satırının içeriğini bildirmek için

1. Bulun **CL.command.1.tlog** dosya ve açın. Varsayılan olarak, bu dosya, Belgeler klasöründe bulunan \\Visual Studio *sürüm*\\projeleri\\*SolutionName* \\ *ProjectName*\\*yapılandırma*\\*ProjectName*.tlog\\CL.command.1.tlog, ya da kullanıcı klasörü altında \\Kaynak\\depoları\\*SolutionName*\\*ProjectName*\\*yapılandırma* \\ *ProjectName*.tlog\\CL.command.1.tlog. Başka bir yapı sistem kullanırsanız veya varsayılan konumu projeniz için değiştirdiyseniz, farklı bir konumda olabilir.

   Bu dosya içinde bunların her birini ayrı satırlara derlemek için kullanılan komut satırı bağımsız değişkenleri ve ardından kaynak kodu dosyaları adlarını bulabilirsiniz.

1. Sorunun nerede oluştuğunu kaynak kodu dosyasının adını içeren satırı bulun; Satır altındaki karşılık gelen cl.exe komut bağımsız değişkenlerini içerir.

Kopyalayın ve tüm komut satırı, rapora yapıştırın.

### <a name="a-description-of-the-problem"></a>Sorun açıklaması

Biz biz bizim makineler aynı etkisini görmek doğrulayabilir karşılaşılan sorunla ayrıntılı bir açıklaması ihtiyacımız; kendi da bazen yararlı bize gerçekleştirmek çalıştığınız ve olmasını beklediğinizi bilmeleri için.

Lütfen **tam hata iletileri** verilen araç takımı veya gördüğünüz tam çalışma zamanı davranışı. Biz düzgün sorunu çoğaltılamaz olduğunu doğrulamak için bu bilgilere ihtiyacımız var. Lütfen dahil **tüm** çıkışı, derleyici yalnızca son hata iletisi. Bildirdiğiniz sorunun açan her şeyi görmek gerekir. Komut satırı derleyicisini kullanarak sorunu çoğaltabilirsiniz olduğunda, o Derleyici çıktısı tercih edilir; IDE ve diğer yapı sistemleri hata iletileri görmek veya yalnızca bir hata iletisi, ilk satırının yakalama filtre uygulayabilir.

Lütfen sorunu derleyici geçersiz kodu kabul eder ve bir tanılama oluşturmaz ise, bu rapor unutmayın.

Bir çalışma zamanı davranışı sorunu bildirmek için içeren bir **tam kopyalama** program yazdırır ve görmeyi beklediğiniz. İdeal olarak, bu çıkış deyiminde kendisi, örneğin, gömülü olduğu `printf("This should be 5: %d\n", actual_result);`. Programınızı kilitleniyor veya askıda kalır, bu da söz.

Bize yardımcı olabilecek herhangi bir ayrıntıyı, tüm iş bulduğunuz ya gibi karşılaştığınız sorunu tanılamak ekleyin. Başka bir yerde raporunuzda bulunan bilgileri yinelenen kaçının.

### <a name="the-repro"></a>Yeniden oluşturma

Bir yeniden oluşturma tekrarlanarak karşılaşılan sorunla gösteren tam ve müstakil kaynak kodu örneği olduğunu (Bu nedenle adı). Böylece hata bizim makinelerde üretebileceği bir yeniden oluşturma ihtiyacımız var. Kodu derler ve çalışan ya da derlemek ve çalıştırmak basit bir yürütülebilir dosyayı oluşturmak için kendi başına kullanılmıyorsa, buldunuz sorun için yeterli olmalıdır. Bir yeniden oluşturma bir kod parçacığı değil; tam işlevleri ve sınıfları olması ve tüm gerekli içeren # standart üstbilgi için bile yönergeleri include.

#### <a name="what-makes-a-good-repro"></a>İyi bir yeniden oluşturma kılan

İyi bir yeniden oluşturma aşağıdaki gibidir:

- **En az.** Repros, olabildiğince küçük henüz hala tam olarak karşılaştığınız sorunu gösterir. Repros karmaşık veya gerçekçi olması gerekmez; yalnızca standart veya belgelenmiş derleyici uygulaması ya da tanılama eksik olması durumunda uyumlu kodu, uyumluluğunu değil kodu göstermek ihtiyaç duyar. Sorun göstermek için yeterli kodu içeren basit,-noktaya repros en iyisidir. Lütfen ortadan kaldırmak veya kod basitleştirebilir ve uyumluluğunu kalır ve ayrıca değişmeden sorunu bırakın, bunu yapın. Karşı çalışan kod örnekleri arasında gerekmez.

- **Kendi içinde yer alan.** Repros gereksiz bağımlılıkları kaçınmalısınız. Lütfen, üçüncü taraf kitaplıklar olmadan sorunu yeniden oluşturup, bunu yapar. Basit çıktı deyimleri yanı sıra tüm kitaplık kodu olmadan sorunu yeniden varsa (örneğin, `puts("this shouldn't compile");`, `std::cout << value;`, ve `printf("%d\n", value);` teşkil), lütfen bunu yapın. Tüm kullanıcı üstbilgileri başvuru olmadan bir tek kaynak kodu dosyasına örnek sıkıştırılmış durumunda idealdir. Biz sorun olası Katılımcısı olarak göz önünde bulundurmanız gereken kod miktarını azaltmak için bize enormously yardımcı olur.

- **En son derleyici sürümü karşı.** Repros en son güncelleştirmeyi Araç Takımı'nın en son sürümünü veya sonraki güncelleştirme veya sonraki büyük yayın, mümkün olduğunda en son ön sürümünü kullanmanız gerekir. Araç takımı eski sürümleri karşılaşabileceğiniz sorunları, daha yeni sürümlerinde çok sık düzeltildi. Düzeltmeler backported olağanüstü durumlarda yalnızca eski sürümlere edinilebilir.

- **Diğer derleyiciler karşı kullanıma** varsa. Taşınabilir C++ kodu ile ilgili repros davranışı diğer derleyiciler karşı mümkünse doğrulamanız gerekir. Standart program doğruluk, sonuçta belirler ve hiçbir derleyici mükemmeldir ancak Clang ve GCC kodunuzu bir tanılama olmadan kabul edin ve MSVC desteklemez, bizim derleyici hatada görüntülemekte olduğunuz olasıdır. (Diğer olasılıklar UNIX ve Windows davranışı ya da C++ standartlar uygulamasını farklı düzeylerde farklılıkları içerir ve benzeri.) Tüm derleyicileri kodunuzu reddederseniz, öte yandan, daha sonra kodunuzu hatalı olduğunu olasıdır. Farklı hata iletilerini görme sorunu kendi başınıza tanılamaya yardımcı olabilir.

   Kodunuzu karşı test etmek için çevrimiçi derleyicileri listesini bulabilirsiniz [çevrimiçi C++ Derleyicileri](https://isocpp.org/blog/2013/01/online-c-compilers) ISO C++ Web sitesi ya da bu seçkin [çevrimiçi C++ Derleyicileri listesi](https://arnemertz.github.io/online-compilers/) github'da. Belirli bazı örnekler [Wandbox](https://wandbox.org/), [derleyici Explorer](https://godbolt.org/), ve [Coliru](http://coliru.stacked-crooked.com/).

   > [!NOTE]
   > Microsoft ile çevrimiçi derleyici Web siteleri bağlı değildir. Birçok çevrimiçi derleyici Web sitesi kişisel projeler olarak çalıştırılır ve sitelerin bazıları bu okuyun, ancak bir arama başkalarının kullanabileceğiniz bulmalıdır kullanılamayabilir.

Derleyici sorunlarını bağlayıcı ve kitaplıklarında kendilerini özellikle yolları göster eğilimindedir. Tür karşılaştığınız sorunlar ne tür bir yeniden oluşturma, raporunuza dahil belirler. Uygun bir yeniden oluşturma araştırmak için hiçbir şey sunuyoruz. Burada, karşılaşabileceğiniz sorunları ve her tür sorunları bildirmek için kullanması gereken repros türleri oluşturmak için yönergeler türleri bazılarını bulunmaktadır.

#### <a name="frontend-parser-crash"></a>Ön uç (ayrıştırıcı) kilitlenme

Ön uç çökme (Crash) derleyici ayrıştırma işlemi sırasında oluşur. Genellikle, derleyici yayma [önemli hata C1001](error-messages/compiler-errors-1/fatal-error-c1001.md) ve hangi hata oluştu; genellikle bir dosya msc1.cpp Bahsediyor, ancak bu ayrıntı yoksayabilirsiniz kaynak kodu dosya ve satır numarası başvuru.

Bu çökme türü için lütfen bir [ön işlemesi yapılan yeniden oluşturma](#preprocessed-repros).

Bu tür bir kilitlenme için örnek Derleyici çıktısı şöyledir:

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

#### <a name="backend-code-generation-crash"></a>Arka uç (kod oluşturma) kilitlenme

Arka uç çökme (Crash) kod derleyici oluşturma aşaması sırasında oluşur. Genellikle, derleyici yayma [önemli hata C1001](error-messages/compiler-errors-1/fatal-error-c1001.md)ve değil kaynak kodu dosyasının başvuru ve satır numarası sorunla ilişkili; genellikle dosya derleyici Bahsediyor\\utc\\src\\p2\\main.c, ancak bu ayrıntı yoksayabilirsiniz.

Bu çökme türü için lütfen bir [bağlantı yeniden oluşturma](#link-repros) bağlama zamanı kodu oluşturma (LTCG) kullanıyorsanız, etkin **/GL** cl.exe komut satırı bağımsız değişkeni. Aksi durumda, Lütfen bir [yeniden oluşturma ön işlemesi yapılan](#preprocessed-repros) yerine.

Burada, örnek Derleyici çıktısı için bir arka uç kilitlenme LTCG kullanılmaz verilmiştir. Derleyici çıktı bunun gibi görünürse sağlamalıdır bir [ön işlemesi yapılan yeniden oluşturma](#preprocessed-repros).

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

Çizgi ile başlayan, **iç derleyici hatası** link.exe değinmektedir yerine cl.exe, LTCG etkindir ve sağlamanız bir [bağlantı yeniden oluşturma](#link-repros). Varsa, not için bir önceki adımda Temizle LTCG derleyici hata iletisinden etkin olup olmadığını ihtiyacınız olabilecek incelemek, derleme kopyaladığınız komut satırı bağımsız değişkenleri oturum **/GL** komut satırı bağımsız değişkeni.

#### <a name="linker-crash"></a>Bağlayıcı kilitlenme

Bağlayıcı çökme (Crash) derleyici çalıştıktan sonra bağlama işlemi sırasında oluşur. Genellikle, bağlayıcı yayma [Bağlayıcı araçları hatası LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md).

> [!NOTE]
> Çıkış C1001 söz edilen ya da bağlama zamanı kodu oluşturma içerir oluştuysa, [arka uç (kod oluşturma) kilitlenme](#backend-code-generation-crash) yerine daha fazla bilgi için.

Bu çökme türü için lütfen bir [bağlantı yeniden oluşturma](#link-repros).

Aşağıda, bu tür bir kilitlenme için örnek derleyici çıktı verilmiştir.

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

Artımlı bağlantılandırma etkindir ve yalnızca bir başarılı ilk bağlantı sonra kilitlenme oluştu (diğer bir deyişle, yalnızca ilk tam üzerinde sonraki artımlı bağlantılandırma temel bağlama sonra) Lütfen nesne (.obj) bir kopyasını da sağlar ve kitaplık (.lib) dosyaları ilk bağlantı tamamlandıktan sonra değiştirilen kaynak dosyalarına karşılık gelir.

#### <a name="bad-code-generation"></a>Hatalı kod oluşturma

Hatalı kod oluşturma nadir ancak derleyici yanlışlıkla uygulamanız bu sorunu derleme zamanında algılama yerine çalışma zamanı kilitlenmesine neden olacak yanlış kodu oluşturduğunda gerçekleşir. Hatalı kod oluşturma sonuçlarını yaşıyor sorun düşünüyorsanız, raporunuzu aynı şekilde işlem bir [arka uç (kod oluşturma) kilitlenme](#backend-code-generation-crash).

Bu çökme türü için lütfen bir [bağlantı yeniden oluşturma](#link-repros) bağlama zamanı kodu oluşturma (LTCG) kullanıyorsanız, etkin **/GL** cl.exe komut satırı bağımsız değişkeni. Lütfen bir [yeniden oluşturma ön işlemesi yapılan](#preprocessed-repros) değilse.

## <a name="how-to-generate-a-repro"></a>Bir yeniden oluşturma oluşturmak nasıl

Sorunun kaynağını izlemenize yardımcı olmak için bir [iyi yeniden oluşturma](#what-makes-a-good-repro) önemlidir. Belirli türde repros için aşağıda açıklanan adımları uygulamadan önce mümkün olduğunca sorun gösteren kod sıkıştırmak deneyin. Ortadan kaldırmak veya bağımlılıkları, gerekli üst bilgilerinin ve kitaplıklarının en aza indirmek ve derleyici seçenekleri ve mümkünse kullanılan önişlemci tanımları sınırlamak deneyin.

Rapor farklı türde sorunları için kullanacağınız repros çeşitli türleri oluşturmak için yönergeler aşağıda verilmiştir.

### <a name="preprocessed-repros"></a>Önceden işlenmiş repros

A *yeniden oluşturma ön işlemesi yapılan* C önişlemci çıktısını kullanılarak oluşturulan bir sorunu gösterir tek kaynak dosyası **/P** özgün yeniden oluşturma kaynak dosyasını derleyici seçeneği. Bu Inlines ek kaynağı ve başlık dosyaları bağımlılıkları kaldırmak için üstbilgileri dahil ve makroları, #ifdefs ve yerel ortamınıza bağlı olan diğer önişlemci komutları da giderir.

> [!NOTE]
> Önceden işlenmiş repros bizim standart kitaplık uygulaması'nda hataları nedeni olabilir sorunları için yararlı değildir biz genellikle sorun zaten düzelttik olup olmadığını görmek için en son, devam eden bir uygulama yerine isteyeceksiniz. Bu durumda, yeniden oluşturma önişle yok ve azaltırsanız olamaz, tek bir kaynak dosyası, sorunu kodunuzu bir .zip dosyasına veya benzer paketini veya bir IDE projeyi yeniden oluşturma kullanmayı düşünün. Daha fazla bilgi için bkz: [diğer repros](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Kaynak kodu dosyasının önişle için

1. Bölümünde açıklandığı gibi yeniden oluşturma oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini bildirmek için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisi ile eşleşir.

1. Yeniden oluşturma projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde aşağıdaki komutu girin **cl /P** *bağımsız değişkenleri* *filename.cpp*, burada *bağımsız değişkenleri* olduğu Yukarıdaki yakalanan bağımsız değişkenlerinin listesi ve *filename.cpp* , yeniden oluşturma kaynak dosyasının adıdır. Bu komutu yeniden oluşturma için kullanılan komut satırı yinelenir ancak önişlemci geçişi sonrasında derleme durdurur ve önceden işlenmiş kaynak koduna çıkarır *filename*. ediyorum.

C + işleniyorsa +/ CX kaynak kodu dosyasının veya C++ modülleri özelliğini kullanıyor, bazı ek adımlar gereklidir. Daha fazla bilgi için aşağıdaki bölümlere bakın.

Önceden işlenmiş dosyasını oluşturduktan sonra onu emin olmak için iyi bir fikirdir önceden işlenmiş dosyasını kullanarak sorunu hala repros.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Onaylamak için hata önceden işlenmiş dosyasıyla repros hala

1. Geliştirici komut istemi konsol penceresinde aşağıdaki komutu girin **cl** *bağımsız değişkenleri* **/TP** *filename*.i derlemek için cl.exe bildirmek için C++ kaynak dosyası olarak önceden işlenmiş dosya burada *bağımsız değişkenleri* yukarıda ancak herhangi biriyle yakalanan bağımsız değişkenleri listesi **/D** ve **/I** bağımsız değişkenler (çünkü kaldırıldı Bunlar zaten önceden işlenmiş dosyasında dahil edilmiş); ve nerede *filename*.i önceden işlenmiş dosyanızı adıdır.

1. Sorunu yeniden olduğunu onaylayın.

Son olarak, önceden işlenmiş yeniden oluşturma attach *filename*raporunuza .i.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>C + ön işlemesi yapılan +/ CX WinRT/UWP kod repros

C + kullanıyorsanız, +/ CX yürütülebilir dosyanın, yapı oluşturmak ve önceden işlenmiş yeniden oluşturma doğrulamak için gereken bazı ek adımlar vardır.

#### <a name="to-preprocess-ccx-source-code"></a>İçin önişle C + +/ CX kaynak kodu

1. Bölümünde açıklandığı gibi önceden işlenmiş kaynak dosyası oluşturma [kaynak kodu dosyasının önişle için](#to-preprocess-a-source-code-file).

1. Oluşturulan arama _filename_.i dosyası için **#using** yönergeleri.

1. Başvurulan tüm dosyaların listesini hazırlayın. Tüm Windows bırakın\*.winmd dosyaları, platform.winmd dosyaları ve mscorlib.dll.

Önceden işlenmiş dosya hala sorun oluşmazsa doğrulamak hazırlamak için

1. Önceden işlenmiş dosya için yeni bir dizin oluşturun ve yeni dizine kopyalayın.

1. .Winmd dosyalarından kopyalamak, **#using** dosyasını yeni dizine listesi.

1. Yeni bir dizinde bir boş vccorlib.h dosyası oluşturun.

1. Kaldırmak için önceden işlenmiş dosyasını düzenleyin **#using** mscorlib.dll yönergeleri.

1. Mutlak yollar yalnızca tam dosya adları kopyalanan .winmd dosyaları değiştirmek için önceden işlenmiş dosyasını düzenleyin.

Önceden işlenmiş dosya hala yukarıdaki sorun oluşmazsa onaylayın.

### <a name="preprocessed-c-modules-repros"></a>Önceden işlenmiş C++ modülleri repros

C++ derleyicisi modülleri özelliğini kullanıyorsanız, oluşturabilir ve önceden işlenmiş yeniden oluşturma doğrulamak için gereken bazı farklı adımlar vardır.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Bir modül kullanan bir kaynak kodu dosyasının önişle

1. Bölümünde açıklandığı gibi yeniden oluşturma oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini bildirmek için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisi ile eşleşir.

1. Yeniden oluşturma projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde aşağıdaki komutu girin **cl /P** *bağımsız değişkenleri* *filename.cpp*, burada *bağımsız değişkenleri* olduğu Yukarıdaki yakalanan bağımsız değişkenlerinin listesi ve *filename.cpp* modülünü kullanan kaynak dosyasının adıdır.

1. Modül arabirimi (.ifc çıktı) yerleşik yeniden oluşturma projeyi içeren dizine geçin.

1. Modül arabirimi oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalayın.

1. Geliştirici komut istemi konsol penceresinde aşağıdaki komutu girin **cl /P** *bağımsız değişkenleri* *modulename.ixx*, burada *bağımsız değişkenleri* olduğu Yukarıdaki yakalanan bağımsız değişkenlerinin listesi ve *modulename.ixx* modülü arabirimi oluşturur dosyasının adıdır.

Önceden işlenmiş dosyaları oluşturduktan sonra önceden işlenmiş dosyasını kullanarak sorunu hala repros emin olmak için iyi bir fikirdir.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Onaylamak için hata önceden işlenmiş dosyasıyla repros hala

1. Geliştirici konsol penceresinde geri yeniden oluşturma projenizi içeren dizine geçin.

1. Aşağıdaki komutu girin **cl** *bağımsız değişkenleri* **/TP** *filename*.i yukarıdakiyle bir C++ kaynak dosyası değilmiş gibi önceden işlenmiş dosya derlemek için.

1. Sorun hala önceden işlenmiş dosyasıyla yeniden onaylayın.

Son olarak, önceden işlenmiş yeniden oluşturma dosyaları Ekle (*filename*.i ve *modulename*.i) raporunuzu .ifc çıkışı yanı sıra.

### <a name="link-repros"></a>Bağlantı repros

A *yeniden oluşturma bağlantı* tarafından belirtilen bir dizin, bağlayıcı tarafından oluşturulan içeriği **bağlantı\_yeniden oluşturma** ortam değişkeni. Topluca bağlama zamanı kodu oluşturma (LTCG) içeren bir arka uç kilitlenme ya da bir bağlayıcı kilitlenme gibi bağlantı zaman ortaya çıkan bir sorun göstermek derleme yapıları içerir. Bunlar yapıları yapı olan sorunu yeniden böylece giriş bağlayıcı gerekli olanlar. Bağlantı yeniden oluşturma bağlayıcı yerleşik yeniden oluşturma oluşturma özelliğini etkinleştirmek için bu ortam değişkenini kullanarak kolayca oluşturulabilir.

#### <a name="to-generate-a-link-repro"></a>Bağlantı yeniden oluşturma oluşturmak için

1. Bölümünde açıklandığı gibi yeniden oluşturma oluşturmak için kullanılan komut satırı bağımsız değişkenleri yakalama [komut satırının içeriğini bildirmek için](#to-report-the-contents-of-the-command-line).

1. Açık **Geliştirici komut istemi** projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisi ile eşleşir.

1. Geliştirici komut istemi konsol penceresinde yeniden oluşturma projenizi içeren dizine geçin.

1. Girin **mkdir linkrepro** bağlantı yeniden oluşturma için bir dizin oluşturmak için.

1. Aşağıdaki komutu girin **kümesi bağlantı\_yeniden oluşturma linkrepro =** ayarlamak için **bağlantı\_yeniden oluşturma** oluşturduğunuz dizine ortam değişkeni.

1. Geliştirici komut istemi konsol penceresinde, Visual Studio'da yeniden oluşturma projesi oluşturmak için aşağıdaki komutu girin **devenv**. Bu değeri sağlar **bağlantı\_yeniden oluşturma** ortam değişkenidir Visual Studio'ya görünür. Komut satırında Projeyi derlemek için yeniden oluşturma yapı çoğaltmak için yukarıdaki yakalanan komut satırı bağımsız değişkenlerini kullanın.

1. Yeniden oluşturma projeyi oluşturun ve beklenen sorun oluştu onaylayın.

1. Yapı gerçekleştirmek için kullandıysanız Visual Studio'yu kapatın.

1. Geliştirici komut istemi konsol penceresinde aşağıdaki komutu girin **kümesi bağlantı\_yeniden oluşturma =** temizlemek için **bağlantı\_yeniden oluşturma** ortam değişkeni.

Son olarak, tüm linkrepro bir .zip dosyasına dizin veya benzer sıkıştırarak yeniden oluşturma paketini ve raporunuza ekleyin.

### <a name="other-repros"></a>Diğer repros

Tek kaynak dosyası ya da önceden işlenmiş yeniden oluşturma sorunu indiremezsiniz ve sorun bağlantı yeniden oluşturma gerektirmez, biz IDE projesinde araştırabilirsiniz. İyi bir yeniden oluşturma oluşturma konusunda tüm yönerge hala geçerlidir; kod sorunu en son araçlarımız gerçekleşmesi gereken en düşük ve kendi başına olmalıdır ve uygunsa, sorun diğer derleyiciler görülmelidir değil.

Yeniden oluşturma en az bir IDE projesi olarak oluşturun, sonra bir .zip dosyasına veya benzer tüm dizin yapısının sıkıştırarak paketini ve raporunuza ekleyin.

## <a name="ways-to-send-your-report"></a>Raporunuzu gönderme yolları

Çeşitli raporunuzu bize almak için iyi şekillerde vardır. Visual Studio'nun yerleşik kullanabilirsiniz [bir sorun aracı rapor](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017), veya [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sayfaları. Seçerek doğrudan sunduğumuz Geliştirici topluluğu sayfalara alabilirsiniz **ürün geri bildirim** bu sayfanın sonundaki düğmesi. Seçimi ekran görüntüleri yakalama ve geliştirici topluluğu sayfalarında nakil raporunuzun düzenleme için IDE içinde yerleşik araçları kullanmak mı istediğinizi ya da doğrudan Web sitesi kullanmayı tercih ederseniz bağlıdır.

> [!NOTE]
> Raporunuzu nasıl gönderme bağımsız olarak, Microsoft, gizliliğinize saygı duyar. Microsoft, tüm veri gizlilik yasalarına ve düzenlemelerine ile uyumluluk için taahhüt eder. Biz bize gönderin verileri nasıl işler hakkında daha fazla bilgi için bkz: [Microsoft Visual Studio ürün ailesi gizlilik bildirimi](https://www.visualstudio.com/dn948229).

### <a name="use-the-report-a-problem-tool"></a>Rapor bir sorun aracını kullanın

**Bir sorun bildirmek** Visual Studio aracında Visual Studio kullanıcıların çeşitli sorunlar yalnızca birkaç tıklama ile rapor bir yoldur. Karşılaştı ve ardından IDE ayrılmadan raporunuzu gönderme sorun hakkında ayrıntılı bilgi belirtmek için kullanabileceğiniz basit bir form sağlar.

Sorununuzu aracılığıyla raporlama **bir sorun bildirmek** araçtır kolay ve rahat IDE gelen. Başlık Çubuğu'ndan seçerek erişebildiğinizi **geri bildirim gönder** yanındaki simge **hızlı başlatma** arama kutusu veya bulabilir, menü çubuğunda **yardımcı**  >  **Geri bildirim gönder** > **bir sorun bildirmek**.

Önce bir sorunu bildirmek seçtiğinizde, yazılım geliştirme topluluğuna benzer sorunlar için arama yapın. Sorununuzu önce bildirildiyse upvote konu ve ek özellikleri ile yorumlar ekleyin. Benzer bir sorun görmüyorsanız seçin **raporu yeni sorun** Visual Studio geri bildirim iletişim kutusunun alt kısmındaki düğmesine tıklayın ve sorunu bildirmek için adımları izleyin.

### <a name="use-the-visual-studio-developer-community-pages"></a>Visual Studio Geliştirici topluluğu sayfalarını kullanma

Visual Studio Geliştirici topluluğu sayfaları sorunları bildirme ve Visual Studio, C++ Derleyici, Araçlar ve kitaplıkları için çözüm bulmak için başka bir uygun yoludur. [Visual Studio soruları](https://developercommunity.visualstudio.com/spaces/8/index.html) IDE veya yükleme sorunları bildirmek nereye sayfasıdır. C++ Derleyici, bağlayıcı ve diğer araçları ve kitaplıklarını kullanma ile ilgili sorunlar için [C++ soruları](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfası.

Yazılım geliştirme topluluğuna başlığı, her sayfanın üstüne yakın gönderileri veya sorunları dilediğiniz benzer rapor konuları bulmak için kullanabileceğiniz bir arama kutusu ' dir. Bir çözüm ya da sorununuz için ilgili yararlı bilgiler zaten varolan bir konuda kullanılabilir olduğunu fark edebilirsiniz. Birisi önce aynı sorun bildirdi, lütfen upvote ve bu konu hakkında yorum yerine yeni bir sorun raporu oluşturun.

Sorununuzu önce bildirilmedi kaldığınızda **bir sorun bildirmek** Geliştirici topluluğu sayfasında arama kutusunun yanında düğmesi. Visual Studio hesabınızda oturum açın ve profilinize Geliştirici topluluğu uygulama erişimi vermek kabul etmeniz istenebilir. Oturum açtığında, sorunun nerede rapor doğrudan sayfasına gidin. Yeniden oluşturma kodunuzu ve komut satırı, ekran görüntüleri, ilgili tartışmalar bağlantılar ve ilgili ve yararlı olduğunu düşündüğünüz diğer bilgiler içerebilir.

> [!TIP]
> Visual Studio'da, araç takımı için (örneğin, kullanıcı Arabirimi sorunları, bozuk bir IDE işlevsellik veya genel çökme (Crash)), ilişkili olmayan karşılaşabileceğiniz sorunları diğer türleri için **bir sorun aracı rapor** özellikle iyi bir seçim son olabilir kendi ekran yetenekleri ve soruna yol kayıt UI eylemlerini kendi yeteneği karşılaştı. Bu tür hatalara da üzerinde bildirilebilir [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) site.

### <a name="reports-and-privacy"></a>Raporlar ve gizlilik

Varsayılan olarak, **raporlar ve açıklamaları ve yanıtları tüm bilgileri herkese görünür**. Sorunları, çözümleri ve diğer kullanıcıların bulduğunuz geçici çözümleri görmek tamamını topluluk izin verdiği için normalde, bir avantajı budur. Ancak, verileri veya kimlik gizlilik veya fikri mülkiyet nedenleri için ortak sağlama konusunda endişe, seçeneğiniz vardır.

Kimliğinizi ortaya hakkında endişeleriniz varsa [yeni bir Microsoft hesabı oluşturmak](https://signup.live.com/) ilgili herhangi bir ayrıntıyı açıklamaz. Raporunuzu oluşturmak için bu hesabı kullanın. 

**Özel başlık veya ortak ilk rapor içeriği tutmak istediğiniz herhangi bir şey koymayın.** Bunun yerine, ayrıntıları özel olarak ayrı bir açıklama için gönderir unutmayın. Raporunuzu doğru kişilere yönlendirilir emin olmak için eklemeniz **cppcompiler** sorun raporu Konu listesinde. Sorun raporu oluşturulduktan sonra artık kimlerin yanıtlar ve ekleri görebileceğini belirtmek mümkündür.

#### <a name="to-create-a-problem-report-for-private-information"></a>Özel bilgi sorun raporu oluşturmak için

1. Oluşturulan rapora seçin **açıklama eklemek** özel, sorunun açıklamasını oluşturmak için.

1. Aşağıdaki açılan denetimi yanıt Düzenleyicisi'nde kullanma **gönderme** ve **iptal** yanıtınızı kitlesi belirtmek için düğmeler. Yalnızca belirttiğiniz kişilerin, bu özel yanıtları ve tüm görüntüleri, bağlantılar veya kod içine dahil görebilirsiniz. Seçin **Viewable araburucu ve özgün posteri** görünürlük Microsoft çalışanlarına ve kendiniz için sınırlamak için.

1. Açıklama ve herhangi diğer bilgileri, görüntüler ve dosya ekleri, yeniden oluşturma için gerekli ekleyin. Seçin **gönderme** özel olarak bu bilgileri göndermek için düğme.

   Ekli dosyalar ve en fazla 10 dosya 2 GB sınırını olduğuna dikkat edin. Tüm büyük yüklemeler için lütfen özel yorumunuzu karşıya yükleme URL'de isteyin.

Bu açıklama altında yanıtları belirttiğiniz aynı kısıtlı görünürlük vardır. Yanıtları açılır denetimin kısıtlı görünürlük durumu doğru göstermez olsa bile bu geçerlidir.

Gizliliğinizi korumak ve hassas bilgilerinizi genel görünümü dışında tutmak için lütfen Microsoft ile tüm etkileşim yanıtları bu kısıtlı açıklama altında tutmak için dikkatli olun. Diğer açıklamaları yanıtlar hassas bilgilerin yanlışlıkla açığa neden olabilir.

## <a name="how-to-report-a-c-documentation-issue"></a>C++ belgeleri sorun bildirme

GitHub sorunları Belgelerimizdeki bildirilen sorunlarını izlemek için kullanırız. Yazarlar ve ürün ekipleriyle çok daha zengin bir yol sağlayan bir içerik sayfasını doğrudan sorunlarını etkileşimli GitHub artık oluşturabilirsiniz. Bir belge, hatalı kod örneği, karmaşık bir açıklama, kritik atlandığını veya bile yalnızca bir yazım hatası ile ilgili bir sorun görürseniz, kolayca bize bildirin. Kaydırma seçin ve sayfanın altına **belgelerine geribildirim vermek oturum**. GitHub hesabı zaten yoksa, ancak bunu yaptığınızda, tüm bizim belgelerine sorunları, bunların durumunu görmek ve, bildirilen sorunu için yapılan bir değişiklik olduğunda bildirim almak oluşturmanız gerekir. Daha fazla bilgi için bkz: [A yeni geri bildirim sistemi yakında docs.microsoft.com için](/teamblog/a-new-feedback-system-is-coming-to-docs).

Belge geri bildirim düğmesini kullanarak Github'da belgelerine konu oluşturduğunuzda, sorunun nerede olduğunu biliyoruz şekilde sorunu, sorunu oluşturulan sayfa hakkında bazı bilgiler ile otomatik olarak doldurulur. Lütfen bu bilgileri düzenleyin yok. Yalnızca yanlış ve, isterseniz, önerilen bir düzeltmeyi yenilikler hakkında ayrıntılı bilgi ekleyin. [Belgelerimizi açık bir kaynaktır](https://github.com/MicrosoftDocs/cpp-docs/), aslında bir düzeltme yapıp kendiniz önermek istiyorsanız, bunu yapabilirsiniz. Bizim belgelerine nasıl katkıda hakkında daha fazla bilgi için bkz: bizim [Contributing Kılavuzu](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) github'da.

