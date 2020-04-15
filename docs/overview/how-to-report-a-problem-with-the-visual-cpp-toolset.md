---
title: Microsoft C++ araç kümesiyle ilgili bir sorunu bildirme
description: Microsoft C++ araç kümesi için iyi bir sorun raporu ve repro bilgi oluşturma.
ms.date: 09/24/2019
ms.technology: cpp-ide
author: corob-msft
ms.author: corob
ms.openlocfilehash: 350e902501aca5cbe2b4022ec1f977719844644b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "71685699"
---
# <a name="how-to-report-a-problem-with-the-microsoft-c-toolset-or-documentation"></a>Microsoft C++ araç kümesi veya dokümantasyonuyla ilgili bir sorunu bildirme

Microsoft C++ derleyicisinde (MSVC), bağlayıcıda veya diğer araçlarda ve kitaplıklarda sorunlar bulursanız, bunları öğrenmek isteriz. Konu belgelerimizde yer aldığında, bunu da bilmek isteriz.

## <a name="how-to-report-a-c-toolset-issue"></a>C++ araç kümesi sorunu nasıl bildirilir?

Bir sorun hakkında bize bildirmenin en iyi yolu, bize keşfettiğiniz sorunun açıklamasını içeren bir rapor göndermektir. Programınızı nasıl oluşturduğunuzla ilgili tüm ayrıntılara sahip olmalıdır. Ve bir *repro*içermelidir , biz kendi makineleri üzerinde sorunu çoğaltmak için kullanabileceğiniz tam bir test çalışması. Bu bilgiler, sorunun kodumuzda var olduğunu ve ortamınız için yerel olmadığını hızlı bir şekilde doğrulamamızı sağlar. Derleyicinin diğer sürümlerini etkileyip etkilemediğini belirlememize ve nedenini tanılamamıza yardımcı olur.

Aşağıdaki bölümlerde, iyi bir rapor yapan hakkında okuyacaksınız. Bulduğunuz sorun türü için nasıl bir repro oluşturacağınızı ve raporunuzu ürün ekibine nasıl göndereceğinizi açıklarız. Raporlarınız bizim ve sizin gibi diğer geliştiriciler için önemlidir. Microsoft C++'ı geliştirmemize yardımcı olduğunuz için teşekkür ederiz!

## <a name="how-to-prepare-your-report"></a>Raporunuzu nasıl hazırlayınız?

Yüksek kaliteli bir rapor oluşturmak önemlidir, çünkü bulduğunuz sorunu tam bilgi olmadan yeniden oluşturmak bizim için zordur. Raporunuz ne kadar iyise, sorunu o kadar etkili bir şekilde yeniden oluşturabilir ve tanıkoyabiliriz.

En azından, raporunuz şunları içermelidir:

- Kullandığınız araç kümesinin tam sürüm bilgileri.

- Kodunuzu oluşturmak için kullanılan tam cl.exe komut satırı.

- Bulduğunuz sorunun ayrıntılı bir açıklaması.

- Bir repro: sorunu gösteren tam, basitleştirilmiş, bağımsız bir kaynak kodu örneği.

İhtiyacımız olan belirli bilgiler ve nerede bulabileceğiniz ve iyi bir repro'yu nasıl oluşturabileceğiniz hakkında daha fazla bilgi edinmek için okumaya devam edin.

### <a name="the-toolset-version"></a>Araç seti sürümü

Tam sürüm bilgilerine ve soruna neden olan araç kümesinin hedef mimarisine ihtiyacımız var. Bu yüzden repro'nuzu makinelerimizde aynı alet setine karşı test edebiliriz. Sorunu yeniden oluşturabiliyorsak, bu bilgiler bize araç kümesinin diğer sürümlerinin aynı soruna sahip olduğunu araştırmak için bir başlangıç noktası da verir.

#### <a name="to-report-the-full-version-of-your-compiler"></a>Derleyicinizin tam sürümünü bildirmek için

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici Komut Komut Komut Ustem'ini** açın. Örneğin, x64 hedefleri için x64 üzerinde Visual Studio 2017 kullanarak inşa ederseniz, **VS 2017 için x64 Yerli Araçlar Komut İstemi'ni**seçin. Daha fazla bilgi için geliştirici [komut istemi kısayolları'na](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)bakın.

1. Geliştirici komut istemi konsol penceresinde, **komut u / Bv**girin.

Çıktı aşağıdakilere benzer olmalıdır:

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

Çıktının tamamını kopyalayıp raporunuza yapıştırın.

### <a name="the-command-line"></a>Komut satırı

Tam komut satırına, CL.exe'e ve tüm argümanlarına ihtiyacımız var, kodunuzu oluşturmak için kullanılır. Bu yüzden makinelerimize aynı şekilde inşa edebiliriz. Bu önemlidir, çünkü bulduğunuz sorun yalnızca belirli bir bağımsız değişken veya bağımsız değişken bileşimiyle oluştururken bulunabilir.

Bu bilgileri bulmak için en iyi yer, sorunu yaşadıktan hemen sonra yapı günlüğündedir. Komut satırının soruna katkıda bulunabilecek tam olarak aynı bağımsız değişkenleri içermesini sağlar.

#### <a name="to-report-the-contents-of-the-command-line"></a>Komut satırının içeriğini bildirmek için

1. **CL.command.1.tlog** dosyasını bulun ve açın. Varsayılan olarak, bu dosya \\Visual Studio *sürümüNde*\\Belgeler\\klasörünüzde bulunur*ProjectsSolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*.tlog\\CL.command.1.tlog veya Kaynak \\\\Repos\\\\*SolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*.tlog CL.command.1.tlog altında Kullanıcı klasöründe. Başka bir yapı sistemi kullanıyorsanız veya projeniz in varsayılan konumunu değiştirdiyseniz farklı bir konumda olabilir.

   Bu dosyanın içinde, kaynak kod dosyalarınızın adlarını ve ardından her biri ayrı satırlarda bunları derlemek için kullanılan komut satırı bağımsız değişkenlerini bulacaksınız.

1. Sorunun oluştuğu kaynak kod dosyasının adını içeren satırı bulun. Aşağıdaki satırda karşılık gelen cl.exe komut bağımsız değişkenleri yer almaktadır.

Tüm komut satırını kopyalayıp raporunuza yapıştırın.

### <a name="a-description-of-the-problem"></a>Sorunun açıklaması

Bulduğunuz sorunun ayrıntılı bir açıklamasına ihtiyacımız var. Böylece makinelerimizde de aynı etkiyi gördüğümüzden o kadar iyi bir şey biliyoruz. Ayrıca bazen neyi başarmaya çalıştığınızı ve ne olmasını beklediğiniz bilmek bizim için de yararlıdır.

İyi bir açıklama, araç kümesi tarafından verilen **tam hata iletilerini** veya gördüğünüz tam çalışma zamanı davranışını sağlar. Sorunu doğru bir şekilde yeniden ürettiğimizi doğrulamak için bu bilgilere ihtiyacımız var. Derleyici çıktısının **tümünün** dahil edin, sadece son hata iletisini değil. Rapor ettiğiniz konuya yol açan her şeyi görmemiz gerekiyor. Komut satırı derleyicisini kullanarak sorunu çoğaltabilirseniz, derleyici çıktısı tercih edilir. IDE ve diğer yapı sistemleri gördüğünüz hata iletilerini filtreleyebilir veya yalnızca hata iletisinin ilk satırını yakalayabilir.

Sorun derleyicinin geçersiz kodu kabul etmesi ve tanıoluşturmamasıysa, bunu raporunuza ekleyin.

Çalışma zamanı davranışı sorununu bildirmek için, programın yazdırdığı ve görmeyi beklediğiniz şeyin tam bir **kopyasını** ekleyin. İdeal olarak, çıktı deyiminin kendisine, örneğin, `printf("This should be 5: %d\n", actual_result);`katıştıracaksınız. Programınız çöküyorsa veya askıdaysa, bundan da bahsedin.

Bulduğunuz geçici çözüm gibi bulduğunuz sorunu tanılamamıza yardımcı olabilecek diğer ayrıntıları ekleyin. Raporunuzun başka bir yerinde bulunan bilgileri yinelememeye çalışın.

### <a name="the-repro"></a>Repro

*Repro,* tam, bağımsız bir kaynak kodu örneğidir. Bulduğunuz problemi, dolayısıyla adı tekrar tekrar gösterir. Makinelerimizdeki hatayı yeniden üretebilmek için bir repro'ya ihtiyacımız var. Kod, derleyen ve çalışan temel bir yürütülebilir oluşturmak için tek başına yeterli olmalıdır. Ya da, bulduğunuz sorun için değilse, *derleyip* çalıştırın. Repro bir kod parçacığı değildir. Tam işlevlere ve sınıflara sahip olmalı ve standart üstbilgi için bile gerekli tüm #include yönergeleri içermelidir.

#### <a name="what-makes-a-good-repro"></a>Ne iyi bir repro yapar

İyi bir repro:

- **Minimal.** Repros mümkün olduğunca küçük olmalı ama yine de tam olarak bulduğunuz sorunu göstermek. Repros karmaşık veya gerçekçi olması gerekmez. Yalnızca Standart'a veya belgelenmiş derleyici uygulamasına uygun kodu göstermeleri gerekir. Eksik bir tanı için, repro'nuz uygun olmayan kodu göstermelidir. Sorunu göstermek için yeterli kod içeren basit, to-the-nokta repros en iyisidir. Kodu ortadan kaldırabilir veya basitleştirebilir ve uyumlu kalabilir ve sorunu değiştirmeden bırakabilirsiniz, bunu yapın. Çalışan karşı kod örneklerini eklemeniz gerekmez.

- **Bağımsız.** Repros gereksiz bağımlılıklardan kaçınmalıdır. Sorunu üçüncü taraf kitaplıkları olmadan yeniden oluşturabiliyorsanız, bunu yapın. Basit çıktı deyimleri dışında herhangi bir kitaplık kodu olmadan `puts("this shouldn't compile");` `std::cout << value;`sorunu `printf("%d\n", value);`çoğaltabilirseniz (örneğin, , ve , sonra bunu. Örnek, herhangi bir kullanıcı üstbilgisine başvuru yapılmadan tek bir kaynak kod dosyasına yoğunlaştırılmış olabilirse idealdir. Soruna olası bir katkıda bulunan olarak göz önünde bulundurmamız gereken kod miktarını azaltmak bizim için son derece yararlıdır.

- **En son derleyici sürümüne karşı.** Repros mümkün olduğunca araç kümesinin en son sürümüiçin en son güncelleştirmeyi kullanmalıdır. Veya, bir sonraki güncelleştirmenin veya bir sonraki büyük sürümün en son yayın öncesi sürümünü kullanın. Araç setinin eski sürümlerinde bulabileceğiniz sorunlar genellikle yeni sürümlerde giderilmiştir. Düzeltmeler yalnızca istisnai durumlarda eski sürümlere geri taşınır.

- İlgiliyse **diğer derleyiciler tarafından kontrol edilir.** Taşınabilir C++ kodu içeren repros mümkünse diğer derleyiciler karşı davranışı doğrulamak gerekir. C++ standardı sonuçta program doğruluğunu belirler ve hiçbir derleyici mükemmel değildir. Ancak, Clang ve GCC kodunuzu tanılama olmadan kabul ettiklerinde ve MSVC kabul etmediğinde, derleyicimizde büyük olasılıkla bir hata bulmuşsunuzlabilirsiniz. (Diğer olasılıklar arasında Unix ve Windows davranışındaki farklılıklar veya farklı C++ standartlarının uygulanması vb.) Tüm derleyiciler kodunuzu reddettiğinde, kodunuzun yanlış olması olasıdır. Farklı hata iletileri görmek sorunu kendiniz tanılamanıza yardımcı olabilir.

   Kodunuzu ISO C++ web sitesinde [çevrimiçi C++ derleyicilerine](https://isocpp.org/blog/2013/01/online-c-compilers) karşı test etmek için çevrimiçi derleyicilerin listesini veya GitHub'daki bu seçilmiş [Çevrimiçi C++ Derleyicileri Listesini](https://arnemertz.github.io/online-compilers/) bulabilirsiniz. Bazı özel örnekler [Wandbox,](https://wandbox.org/) [Derleyici Explorer](https://godbolt.org/)ve [Coliru](https://coliru.stacked-crooked.com/)içerir.

   > [!NOTE]
   > Çevrimiçi derleyici web siteleri Microsoft'a bağlı değildir. Birçok çevrimiçi derleyici web sitesi kişisel projeler olarak çalıştırılır. Bu sitelerden bazıları bunu okuduğunuzda kullanılamayabilir, ancak bir arama da kullanabileceğiniz başkalarını bulmalıdır.

Derleyici, bağlayıcı ve kitaplıktaki sorunlar, kendilerini belirli şekillerde gösterme eğilimindedir. Bulduğunuz sorun, raporunuza ne tür bir repro eklemeniz gerektiğini belirler. Uygun bir repro olmadan, araştıracak bir şeyimiz yok. Burada görebileceğiniz sorunlar dan birkaçı vardır. Her tür bir sorunu bildirmek için kullanmanız gereken repro türünü nasıl oluşturacağınız hakkında talimatlar ekleriz.

#### <a name="frontend-parser-crash"></a>Frontend (parser) çarpışması

Ön uç çökmeleri derleyicinin ayrıştırma aşamasında oluşur. Genellikle derleyici [C1001 Ölümcül Hata](../error-messages/compiler-errors-1/fatal-error-c1001.md)yayır ve hatanın oluştuğu kaynak kod dosyası na ve satır numarasına başvurur. Genellikle msc1.cpp adlı bir dosyadan bahseder, ancak bu ayrıntıyı yoksayabilirsiniz.

Bu tür bir çarpışma için, [önceden işlenmiş bir repro](#preprocessed-repros)sağlar.

Bu tür bir kilitlenme için örnek derleyici çıktısı aşağıda verilmiştir:

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

#### <a name="backend-code-generation-crash"></a>Arka uç (kod oluşturma) çökmesi

Arka uç çökmeleri derleyicinin kod oluşturma aşamasında oluşur. Genellikle, derleyici [Fatal Error C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md)yayır ve sorunla ilişkili kaynak kodu dosyası ve satır numarasına başvurulabilir. Genellikle dosya derleyicisi\\utc\\\\src\\p2 main.c bahseder, ancak bu ayrıntıyı göz ardı edebilirsiniz.

Bu tür bir kilitlenme için, **/GL** komut satırı bağımsız değişkeni tarafından cl.exe olarak etkinleştirilen Bağlantı-Zaman Kodu Oluşturma (LTCG) kullanıyorsanız bir [Bağlantı repro'su](#link-repros) sağlayın. Değilse, bunun yerine [önceden işlenmiş bir repro](#preprocessed-repros) sağlayın.

LTCG'nin kullanılmadığı bir arka uç çökmesi için örnek derleyici çıktısı burada. Derleyici çıktınız aşağıdaki gibi görünüyorsa, [önceden işlenmiş bir repro](#preprocessed-repros)sağlamalısınız.

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

**Internal COMPILER ERROR** ile başlayan satır cl.exe yerine link.exe'den bahsediyorsa, LTCG etkinleştirilmişti. Bu durumda bir [Bağlantı repro](#link-repros) sağlayın. LTCG derleyici hata iletisinden etkinleştirilip etkinleştirilmediği belli olmadığında, komut satırı bağımsız değişkenlerini inceleyin. **/GL** komut satırı bağımsız değişkeni için önceki bir adımda bunları yapı günlüğünden kopyaladınız.

#### <a name="linker-crash"></a>Bağlayıcı çökmesi

Bağlayıcı çökmeleri bağlama aşamasında, derleyici çalıştırdıktan sonra oluşur. Genellikle, bağlayıcı [Linker Araçları Hata LNK1000](../error-messages/tool-errors/linker-tools-error-lnk1000.md)yatacak.

> [!NOTE]
> Çıktıda C1001'den bahsediliyorsa veya Bağlantı Zamanı Kodu Oluşturma içeriyorsa, bunun yerine [Backend (kod oluşturma) çökmesine](#backend-code-generation-crash) bakın.

Bu tür bir çökme için, bir [Link repro](#link-repros)sağlar.

Bu tür bir çökme için derleyici çıktısı örneği aşağıda verilmiştir:

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

Artımlı bağlantı etkinse ve kilitlenme yalnızca başarılı bir ilk bağlantıdan sonra oluştuysa, yani daha sonraki bir artımlı bağlantının temel aldığı ilk tam bağlantıdan sonra, ayrıca ilk bağlantı tamamlandıktan sonra değiştirilen kaynak dosyalara karşılık gelen nesne (.obj) ve kitaplık (.lib) dosyalarının bir kopyasını sağlar.

#### <a name="bad-code-generation"></a>Kötü kod oluşturma

Kötü kod üretimi nadirdir. Derleyici yanlışlıkla uygulamanızın çalışma zamanında çökmesine neden olan yanlış kod oluşturduğunda oluşur. Bunun yerine, doğru kod oluşturmalı veya derleme zamanında bir sorun algılamalıdır. Kötü kod oluşturma da sonuç bulduğunuz soruna inanıyorsanız, raporunuzu [Arka Uç (kod oluşturma) kilitlemi](#backend-code-generation-crash)olarak ele verin.

Bu tür bir kilitlenme için, cl.exe için **/GL** komut satırı bağımsız değişkenini kullanıyorsanız bir [Link repro](#link-repros) sağlayın. Değilse [önceden işlenmiş bir repro](#preprocessed-repros) sağlayın.

## <a name="how-to-generate-a-repro"></a>Nasıl bir repro oluşturmak için

Sorunun kaynağını bulmamıza yardımcı olmak için iyi bir [repro](#what-makes-a-good-repro) hayati önem taşıyor. Belirli repros türleri için aşağıda özetlenen adımlardan herhangi birini yapmadan önce, sorunu mümkün olduğunca gösteren kodu yoğunlaştırmaya çalışın. Bağımlılıkları, gerekli üstbilgi ve kitaplıkları ortadan kaldırmaya veya en aza indirmeye çalışın. Mümkünse derleyici seçeneklerini ve kullanılan önişlemci tanımlarını sınırlayın.

Aşağıda, farklı türde sorunları bildirmek için kullanacağınız çeşitli repros türlerini oluşturma yönergeleri verilmiştir.

### <a name="preprocessed-repros"></a>Önceden işlenmiş repros

*Önceden işlenmiş repro,* bir sorunu gösteren tek bir kaynak dosyasıdır. C önişlemcisinin çıktısından oluşturulur. Bir tane oluşturmak için, orijinal repro kaynak dosyasındaki **/P** derleyici seçeneğini kullanın. Bu seçenek, ek kaynak ve üstbilgi dosyalarına olan bağımlılıkları kaldırmak için dahil edilen üstbilgi satırlar. Bu seçenek, yerel ortamınıza bağlı olabilecek makroları, #ifdef koşullu komutları ve diğer ön işlemci komutlarını da giderir.

> [!NOTE]
> Önceden işlenmiş repros standart kitaplık uygulamamızdaki hataların sonucu olabilecek sorunlar için yararlı değildir, çünkü sorunu zaten düzeltip düzeltmediğimizi görmek için genellikle en son, devam eden uygulamamızı değiştirmek isteriz. Bu durumda, repro'yu önceden işlemeyin ve sorunu tek bir kaynak dosyaya indiremezseniz, kodunuzu bir .zip dosyasına veya benzerbir dosyaya paketleyebilir veya bir IDE proje repro'su kullanmayı düşünün. Daha fazla bilgi için [bkz.](#other-repros)

#### <a name="to-preprocess-a-source-code-file"></a>Kaynak kodu dosyasını önceden işlemek için

1. Komut satırının içeriğini bildirmek için açıklandığı gibi, repro oluşturmak için kullanılan komut satırı bağımsız [değişkenleri yakalayın.](#to-report-the-contents-of-the-command-line)

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici Komut Komut Komut Ustem'ini** açın.

1. Repro projenizi içeren dizine değiştirin.

1. Geliştirici komut istemi konsol penceresinde, komut **cl / P** bağımsız *değişkenler* *filename.cpp*girin. *Bağımsız değişkenler*için, yukarıda yakalanan bağımsız değişkenlerin listesini kullanın. *filename.cpp,* repro kaynak dosyanızın adıdır. Bu komut, repro için kullandığınız komut satırını çoğaltır, ancak önişlemci geçişinden sonra derlemeyi durdurur. Sonra *filename.i*için önceden işlenmiş kaynak kodu yazar.

C++/CX kaynak kodu dosyasını önceden işliyorsanız veya C++ Modülleri özelliğini kullanıyorsanız, bazı ek adımlar gerekir. Daha fazla bilgi için aşağıdaki bölümlere bakın.

Önceden işlenmiş dosyayı oluşturduktan sonra, önceden işlenmiş dosyayı derlediğinizde sorunun hala yeniden oluşturulduğundan emin olmak iyi bir fikirdir.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Önceden işlenmiş dosyayı onaylamak için hala hatayı yeniden

1. Geliştirici komut istemi konsol penceresinde, cl.exe'ye önceden işlenmiş dosyayı C++ kaynak dosyası olarak derlemesini söylemek için **cl** *bağımsız değişkenleri* **/TP** *filename.i* komutunu girin. *Bağımsız değişkenler* yukarıda yakalanan aynı bağımsız değişkenler, ancak herhangi bir **/ D** ve / **I** bağımsız değişkenleri kaldırıldı. Çünkü önceden işlenmiş dosyaya zaten dahil edilmişler. *filename.i* önceden işlenmiş dosyanızın adıdır.

1. Sorunun yeniden üretildiğini doğrulayın.

Son olarak, önceden işlenmiş repro *dosya adını*.i'yi raporunuza ekleyin.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Önceden işlenmiş C++/CX WinRT/UWP kod repros

Çalıştırılabilir oluşturabilirsiniz oluşturmak için C++/CX kullanıyorsanız, önceden işlenmiş bir repro oluşturmak ve doğrulamak için bazı ek adımlar gerekir.

#### <a name="to-preprocess-ccx-source-code"></a>C++/CX kaynak kodunu önceden işlemek için

1. Kaynak [kodu dosyasını önceden işlemek için](#to-preprocess-a-source-code-file)açıklandığı şekilde önceden işlenmiş bir kaynak dosyası oluşturun.

1. **#using** yönergeleri için oluşturulan _dosya adı_.i dosyasını arayın.

1. Başvurulan tüm dosyaların bir listesini yapın. Herhangi bir\*Windows .winmd dosyaları, platform.winmd dosyaları ve mscorlib.dll dışında bırakın.

Önceden işlenmiş dosyanın sorunu yeniden ürettiğini doğrulamak için hazırlamak için,

1. Önceden işlenmiş dosya için yeni bir dizin oluşturun ve yeni dizine kopyalayın.

1. **.winmd** dosyalarını #using listenizden yeni dizine kopyalayın.

1. Yeni dizinde boş bir vccorlib.h dosyası oluşturun.

1. mscorlib.dll için **#using** yönergelerini kaldırmak için önceden işlenmiş dosyayı edin.

1. Kopyalanan .winmd dosyaları için herhangi bir mutlak yolu salt dosya adlarıyla değiştirmek için önceden işlenmiş dosyayı edin.

Önceden işlenmiş dosyanın yukarıdaki gibi sorunu yeniden ürettiğini doğrulayın.

### <a name="preprocessed-c-modules-repros"></a>Önceden işlenmiş C++ Modülleri repros

C++ derleyicisinin Modüller özelliğini kullanıyorsanız, önceden işlenmiş bir repro oluşturmak ve doğrulamak için bazı farklı adımlar gerekir.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Modül kullanan bir kaynak kodu dosyasını önceden işlemek için

1. Komut satırının içeriğini bildirmek için açıklandığı gibi, repro oluşturmak için kullanılan komut satırı bağımsız [değişkenleri yakalayın.](#to-report-the-contents-of-the-command-line)

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici Komut Komut Komut Ustem'ini** açın.

1. Repro projenizi içeren dizine değiştirin.

1. Geliştirici komut istemi konsol penceresinde, komut **cl / P** bağımsız *değişkenler* *filename.cpp*girin. *Bağımsız değişkenler* yukarıda yakalanan bağımsız değişkenlerdir ve *filename.cpp* modülü tüketen kaynak dosyanın adıdır.

1. Modül arabirimini (.ifc çıkışı) oluşturan repro projesini içeren dizin değiştirin.

1. Modül arabirimi oluşturmak için kullanılan komut satırı bağımsız değişkenlerini yakalayın.

1. Geliştirici komut istemi konsol penceresinde, komut **cl / P** bağımsız *değişkenler* *modulename.ixx*girin. *Bağımsız değişkenler* yukarıda yakalanan bağımsız değişkenlerdir ve *modulename.ixx* modül arabirimini oluşturan dosyanın adıdır.

Önceden işlenmiş dosyaları oluşturduktan sonra, önceden işlenmiş dosyayı kullandığınızda sorunun hala yeniden oluşturulduğundan emin olmak iyi bir fikirdir.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Önceden işlenmiş dosyayı onaylamak için hala hatayı yeniden

1. Geliştirici konsol penceresinde, repro projenizi içeren dizine geri dön.

1. Önceden işlenmiş dosyayı C++ kaynak dosyası gibi derlemek için yukarıdaki gibi komut **cl** *bağımsız değişkenleri* **/TP** *dosya adı*.i girin.

1. Sorunun hala önceden işlenmiş dosya tarafından çoğaltıldığını doğrulayın.

Son olarak, önceden işlenmiş repro dosyalarını *(filename*.i ve *modulename*.i) .ifc çıktısıyla birlikte raporunuza ekleyin.

### <a name="link-repros"></a>Bağlantı repros

*Bağlantı repro* bağlantı repro bağlantı repro veya **bağlantı\_repro** ortamı değişkeni tarafından belirtilen bir dizinin bağlayıcı oluşturulan içeriği, ya da [/ LINKREPRO](../build/reference/linkrepro.md) bağlayıcı seçeneği için bir bağımsız değişken olarak. Bu toplubağlantı zamanda meydana gelen bir sorunu gösteren yapı yapıları içerir. Örnekler arasında Bağlantı-Zaman Kodu Oluşturma (LTCG) içeren bir arka uç çökmesi veya bir bağlayıcı çökmesi verilebilir. Bu yapı yapıları, sorunun yeniden üretileebilmesi için bağlayıcı girdi olarak gerekli olan lardır. Bu ortam değişkeni kullanılarak kolayca bir bağlantı repro'su oluşturulabilir. Bu, bağlayıcının yerleşik repro oluşturma yeteneğini sağlar.

#### <a name="to-generate-a-link-repro-using-the-link_repro-environment-variable"></a>link_repro ortamı değişkenini kullanarak bir bağlantı repro oluşturmak için

1. Komut satırının içeriğini bildirmek için açıklandığı gibi, repro oluşturmak için kullanılan komut satırı bağımsız [değişkenleri yakalayın.](#to-report-the-contents-of-the-command-line)

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici Komut Komut Komut Ustem'ini** açın.

1. Geliştirici komut istemi konsol penceresinde, repro projenizi içeren dizine değiştirin.

1. Link repro için *linkrepro* adlı bir dizin oluşturmak için **mkdir linkrepro** girin. Başka bir bağlantı repro yakalamak için farklı bir ad kullanabilirsiniz.

1. Oluşturduğunuz dizine **\_bağlantı repro** ortamı değişkenini ayarlamak için komut **kümesi bağlantısını\_repro=linkrepro** girin. Yapınız, genellikle daha karmaşık projelerde olduğu gibi farklı bir dizinden çalıştırılırsa, bağlantı **\_repro'yu** bağlantı repro dizininize tam yola ayarlayın.

1. Visual Studio'da repro projesini oluşturmak için geliştirici komut istemi konsol penceresinde **devenv**komutunu girin. **\_Bağlantı repro** ortam değişkeninin değerinin Visual Studio tarafından görülebilmesini sağlar. Projeyi komut satırında oluşturmak için, repro yapısını çoğaltmak için yukarıda yakalanan komut satırı bağımsız değişkenlerini kullanın.

1. Repro projenizi oluşturun ve beklenen sorunun oluştuğunu doğrulayın.

1. Yapıyı yapmak için kullandıysanız Visual Studio'yu kapatın.

1. Geliştirici komut istemi konsol penceresinde, **\_bağlantı repro** ortam değişkenini temizlemek için komut **kümesi link\_repro=** girin.

Son olarak, bir .zip dosyası veya benzer içine tüm linkrepro dizin sıkıştırarak repro paketi ve raporunuza ekleyin.

**/LINKREPRO** bağlayıcı **seçeneği,\_link repro** ortam değişkeni ile aynı etkiye sahiptir. Oluşturulan bağlantı repro'su için filtrelenebilmek için adı belirtmek için [/LINKREPROTARGET](../build/reference/linkreprotarget.md) seçeneğini kullanabilirsiniz. **/LINKREPROTARGET'i**kullanmak için **/OUT** bağlayıcı seçeneğini de belirtmeniz gerekir.

#### <a name="to-generate-a-link-repro-using-the-linkrepro-option"></a>/LINKREPRO seçeneğini kullanarak bir bağlantı repro oluşturmak için

1. Bağlantıyı yeniden tutmak için bir dizin oluşturun. Oluşturduğunuz dizin yolunun tamamını _dizin yolu_olarak adlandıracağız. Boşluklar içeriyorsa, yolun etrafında çift tırnak kullanın.

1. **/LINKREPRO:**_dizin yolu_ komutunu bağlayıcı komut satırına ekleyin. Visual Studio'da, projeniz için **Özellik Sayfaları** iletişim kutusunu açın. Yapılandırma **Özellikleri** > **Bağlayıcı** > **Komut Satırı** özellik sayfasını seçin. Ardından, **Ek Seçenekler** kutusuna **/LINKREPRO:**_dizin yolu_ seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

1. Repro projenizi oluşturun ve beklenen sorunun oluştuğunu doğrulayın.

Son olarak, repro'yu bir .zip dosyasıveya benzeri bir dosyaya tüm _dizin yolu_ bağlantısı repro dizinini sıkıştırarak paketleyip raporunuza ekleyin.

### <a name="other-repros"></a>Diğer repros

Sorunu tek bir kaynak dosyaya veya önceden işlenmiş repro'ya indiremezseniz ve sorun bir bağlantı repro'su gerektirmiyorsa, bir IDE projesini inceleyebiliriz. İyi bir repro oluşturmak için nasıl tüm rehberlik hala geçerlidir: kod en az ve kendi kendine yeten olmalıdır. Sorun en son araçlarımızda ortaya çıkmalı ve ilgiliyse diğer derleyicilerde görülmemelidir.

Repro'nuzu en az IDE projesi olarak oluşturun, ardından tüm dizin yapısını bir .zip dosyasına sıkıştırarak veya benzer bir şekilde paketleyip raporunuza takın.

## <a name="ways-to-send-your-report"></a>Raporunuzu gönderme yolları

Raporunu bize vermek için birkaç iyi yöntemin var. Visual Studio'nun yerleşik Sorun [Bildir Aracı'nı](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)veya [Visual Studio Developer Community](https://developercommunity.visualstudio.com/) sayfalarını kullanabilirsiniz. Bu sayfanın alt kısmında bir **Ürün geri bildirimi** düğmesi de bulunmaktadır. Seçim, ekran görüntülerini yakalamak ve raporunuzu düzenlemek için IDE'deki yerleşik araçları kullanmak isteyip istemediğinize bağlıdır. Tercih etmiyorsanız, Geliştirici Topluluğu web sitesini doğrudan kullanabilirsiniz.

> [!NOTE]
> Raporunuzu nasıl gönderdiğinizne bakılmaksızın, Microsoft gizliliğinize saygı duyar. Microsoft, tüm veri gizliliği yasaları ve yönetmeliklerine uymayı taahhüt eder. Bize gönderdiğiniz verileri nasıl ele aldığımız hakkında bilgi için [Microsoft Gizlilik Bildirimi'ne](https://privacy.microsoft.com/privacystatement)bakın.

### <a name="use-the-report-a-problem-tool"></a>Sorun Bildir aracını kullanma

Visual Studio'daki **Sorun Bildir** aracı, Visual Studio kullanıcılarının sorunları sadece birkaç tıklamayla bildirmesinin bir yoludur. Bulduğunuz sorun hakkında ayrıntılı bilgi göndermek için basit bir form açılır. Daha sonra IDE'den hiç ayrılmadan raporunuzu gönderebilirsiniz.

**Sorun Bildir** aracı aracılığıyla sorununuzu bildirmek IDE'den kolay ve kullanışlıdır. **Hızlı Başlat** arama kutusunun yanındaki **Geri Bildirim Gönder** simgesini seçerek başlık çubuğundan erişebilirsiniz. Veya, **Geri** > **Bildirim** > Gönder'deki menü çubuğunda**bulabilirsiniz.**

Bir sorunu bildirmeyi seçtiğinizde, önce Geliştirici Topluluğu'nda benzer sorunlar için arama yapın. Sorununuzun daha önce bildirilmiş olması durumunda, raporu yukarı oylayın ve ek ayrıntılariçeren yorumlar ekleyin. Benzer bir sorun görmüyorsanız, Visual Studio Geri Bildirim iletişim kutusunun altındaki **Yeni Sorun Bildir** düğmesini seçin ve sorununuzu bildirmek için aşağıdaki adımları izleyin.

### <a name="use-the-visual-studio-developer-community-pages"></a>Visual Studio Developer Community sayfalarını kullanma

Visual Studio Developer Community sayfaları, sorunları bildirmenin ve Visual Studio ve C++ derleyicisi, araçları ve kitaplıkları için çözümler bulmanın başka bir kullanışlı yoludur. [Visual Studio, Visual Studio](https://developercommunity.visualstudio.com/spaces/8/index.html)for [Mac](https://developercommunity.visualstudio.com/spaces/41/index.html), [.NET](https://developercommunity.visualstudio.com/spaces/61/index.html), [C++](https://developercommunity.visualstudio.com/spaces/62/index.html), [Azure DevOps Services](https://developercommunity.visualstudio.com/spaces/21/index.html)ve [TFS](https://developercommunity.visualstudio.com/spaces/22/index.html)için özel Geliştirici Topluluğu sayfaları vardır.

Topluluk sekmelerinin altında, her sayfanın üst kısmında bir arama kutusu bulunur. Sizinkine benzer sorunları bildiren gönderileri bulmak için kullanabilirsiniz. Sorununuzun bir çözüm veya diğer yararlı bilgiler zaten kullanılabilir bulabilirsiniz. Birisi aynı sorunu daha önce bildirmişse, yeni bir sorun raporu oluşturmak yerine bu rapora oy verin ve yorum yapın. Yeni bir sorunu yorumlamak, oylamak veya bildirmek için Visual Studio hesabınızda oturum açmanız istenebilir. İlk oturum açğınızda, Geliştirici Topluluğu uygulamasına profilinize erişim izni vermeyi kabul etseniz gerekir.

C++ derleyicisi, bağlayıcısı ve diğer araçlar ve kitaplıklarla ilgili sorunlar için [C++](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfasını kullanın. Sorununuzu ararsanız ve daha önce bildirilmemişse, arama kutusunun yanındaki **sorun bildir** düğmesini seçin. Repro kodunuzu ve komut satırınızı, ekran görüntülerinizi, ilgili tartışmalara bağlantılar ve alakalı ve yararlı olduğunu düşündüğünüz diğer bilgileri ekleyebilirsiniz.

> [!TIP]
> Visual Studio'da C++ araç kümesiyle alakasız diğer türde sorunlar (Örneğin, UI sorunları, bozuk IDE işlevselliği veya genel kilitlenmeler) IDE'de **Sorun Bildir** aracını kullanın. Bu, ekran görüntüsü yetenekleri ve bulduğunuz soruna yol açan UI eylemlerini kaydetme yeteneği nedeniyle en iyi seçimdir. Bu tür hatalar [Geliştirici Topluluğu](https://developercommunity.visualstudio.com/) sitesinde de görülebilir. Daha fazla bilgi için [Visual Studio ile ilgili bir sorunu nasıl bildirin.](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)

### <a name="reports-and-privacy"></a>Raporlar ve gizlilik

**Raporlardaki tüm bilgiler ve tüm yorumlar ve yanıtlar varsayılan olarak genel olarak görülebilir.** Normalde, tüm topluluğun diğer kullanıcıların bulduğu sorunları, çözümleri ve geçici çözümleri görmesini sağladığı için bu bir avantajdır. Ancak, gizlilik veya fikri mülkiyet nedenleriyle verilerinizi veya kimliğinizi herkese açık hale getirme konusunda endişeleriniz varsa, seçenekleriniz vardır.

Kimliğinizi ifşa etme konusunda endişeleriniz varsa, sizinle ilgili hiçbir ayrıntıyı açıklamayan [yeni bir Microsoft hesabı oluşturun.](https://signup.live.com/) Raporunuzu oluşturmak için bu hesabı kullanın.

**Gizli tutmak istediğiniz hiçbir şeyi herkese açık olan ilk raporun başlığına veya içeriğine koymayın.** Bunun yerine, ayrıntıları ayrı bir yorumda özel olarak göndereceğinizi varsan. Raporunuzun doğru kişilere yönlendirildiğinden emin olmak için, sorun raporunuzun konu listesine **cppderer'** i ekleyin. Sorun raporu oluşturulduktan sonra, yanıtlarınızı ve eklerinizi kimlerin görebileceğini artık belirtmek mümkündür.

#### <a name="to-create-a-problem-report-for-private-information"></a>Özel bilgiler için sorun raporu oluşturmak için

1. Oluşturduğunuz raporda, sorunun özel açıklamasını oluşturmak için **yorum ekle'yi** seçin.

1. Yanıt düzenleyicisinde, yanıtınızın hedef kitlesini belirtmek için **Gönder** ve **İptal** düğmelerinin altındaki açılır açma denetimini kullanın. Yalnızca belirttiğiniz kişiler bu özel yanıtları ve bunlara eklediğiniz resimleri, bağlantıları veya kodu görebilir. Microsoft çalışanları ve kendinizin görünürlüğünü sınırlamak için **moderatörler tarafından Görüntülenebilir'i ve orijinal posteri** seçin.

1. Açıklamave repro için gerekli diğer bilgileri, görüntüleri ve dosya eklerini ekleyin. Bu bilgileri özel olarak göndermek için **Gönder** düğmesini seçin.

   Ekli dosyalarda 2 GB sınırı ve en fazla 10 dosya vardır. Daha büyük yüklemeler için, özel yorumunuzda bir yükleme URL'si isteyin.

Bu yorumun altındaki yanıtlar, belirttiğiniz sınırlı görünürlüğe sahiptir. Yanıtlar üzerindeki açılır bırakma denetimi kısıtlı görünürlük durumunu doğru şekilde göstermese bile doğrudur.

Gizliliğinizi korumak ve hassas bilgilerinizi genel görünümden uzak tutmak için dikkatli olun. Sınırlı yorum altında yanıtlar için Microsoft ile tüm etkileşimi tutun. Diğer yorumlara verilen yanıtlar, hassas bilgileri yanlışlıkla ifşa etmenize neden olabilir.

## <a name="how-to-report-a-c-documentation-issue"></a>C++ belge sorunu nasıl bildirilir?

Belgelerimizde bildirilen sorunları izlemek için GitHub sorunlarını kullanırız. Artık GitHub sorunlarını doğrudan bir içerik sayfasından oluşturabilirsiniz, bu da yazarlar ve ürün ekipleriyle çok daha zengin bir şekilde etkileşimkurmanızı sağlar. Bir belge, kötü kod örneği, kafa karıştırıcı bir açıklama, kritik bir ihmal, hatta sadece bir yazım hatası ile ilgili bir sorun görürseniz, bize kolayca bildirebilirsiniz. Sayfanın altına gidin ve **belgelere geri bildirim de vermek için Oturum Aç'ı**seçin. Zaten hesabınız yoksa bir GitHub hesabı oluşturmanız gerekir. Bir GitHub hesabınız olduğunda, tüm dokümantasyon sorunlarımızı ve bunların durumunu görebilirsiniz. Ayrıca, bildirdiğinin soruniçin değişiklikler yapıldığında bildirimler de alırsınız. Daha fazla bilgi için [bkz: Yeni Bir Geri Bildirim Sistemi docs.microsoft.com Geliyor.](/teamblog/a-new-feedback-system-is-coming-to-docs)

Belge geri bildirimi düğmesini kullandığınızda GitHub'da bir belge sorunu oluşturursunuz. Sorun, sorunu oluşturduğunuz sayfa yla ilgili bazı bilgilerle otomatik olarak doldurulur. Sorunun nerede olduğunu bu şekilde biliyoruz, bu nedenle bu bilgileri de bu şekilde değiştirin. Sadece sorunun ne olduğu yla ilgili ayrıntıları ve isterseniz önerilen düzeltmeyi ekle. [C++ dokümanlarımız açık kaynak koddur,](https://github.com/MicrosoftDocs/cpp-docs/)bu nedenle kendiniz bir düzeltme göndermek isterseniz, gönderebilirsiniz. Belgelerimize nasıl katkıda bulunabileceğiniz hakkında daha fazla bilgi için GitHub'daki [Katkıda Bulunan kılavuzumuza](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) bakın.
