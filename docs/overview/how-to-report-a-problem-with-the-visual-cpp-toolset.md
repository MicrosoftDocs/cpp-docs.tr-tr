---
title: Microsoft C++ araç takımı ile sorun bildirme
description: Microsoft C++ araç takımı için iyi bir sorun raporu ve yeniden üretme bilgileri oluşturma.
ms.date: 09/24/2019
ms.technology: cpp-ide
author: corob-msft
ms.author: corob
ms.openlocfilehash: 350e902501aca5cbe2b4022ec1f977719844644b
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685699"
---
# <a name="how-to-report-a-problem-with-the-microsoft-c-toolset-or-documentation"></a>Microsoft C++ araç takımı veya belgeleriyle ilgili bir sorunu bildirme

Microsoft C++ DERLEYICISI (MSVC), bağlayıcı veya diğer araç ve kitaplıklarda sorunlar bulursanız, bunları öğrenmek istiyoruz. Sorun belgelerimizde olduğunda, bunun da nasıl olduğunu öğrenmek istiyoruz.

## <a name="how-to-report-a-c-toolset-issue"></a>C++ Araç takımı sorununu bildirme

Bir sorun hakkında bize bildirmek için en iyi yol, bulduğunuz sorunun açıklamasını içeren bir rapor göndermektir. Programınızı nasıl derlemenize ilişkin tüm ayrıntıları içermelidir. Bu, sorunu kendi makinelerimizde yeniden oluşturmak için kullanabilmemiz için bir yeniden oluşturma ve bir yeniden *üretme*içermelidir. Bu bilgiler, sorunun kodunuzda mevcut olduğunu ve ortamınızda yerel olmadığını hızlı bir şekilde doğrulamamızı sağlar. Derleyicinin diğer sürümlerini etkileyip etkilemediğini ve nedenini tanımamıza yardımcı olur.

Aşağıdaki bölümlerde iyi rapor oluşturma hakkında bilgi edineceksiniz. Bulduğunuz sorun türü için yeniden üretme oluşturmayı ve raporunuzun ürün ekibine nasıl gönderileceğini anlatmaktadır. Raporlarınız bizim için ve sizin gibi diğer geliştiriciler için önemlidir. Microsoft C++'un geliştirmemize yardımcı olduğunuz için teşekkürler!

## <a name="how-to-prepare-your-report"></a>Raporunuzu hazırlama

Tam bilgi olmadan bulduğunuz sorunu yeniden oluşturmamızı zortacağından, yüksek kaliteli bir rapor oluşturulması önemlidir. Raporunuzun ne kadar iyi olduğu, sorunu yeniden oluşturup tanılamanıza daha etkili bir hale getirebiliriz.

Raporunuzun en azından şunları içermesi gerekir:

- Kullanmakta olduğunuz araç takımının tam sürüm bilgileri.

- Kodunuzu derlemek için kullanılan Full CL. exe komut satırı.

- Bulduğunuz sorunun ayrıntılı bir açıklaması.

- Yeniden üretme: sorunu gösteren, tam, Basitleştirilmiş, kendi kendine içerilen bir kaynak kodu örneği.

İhtiyaç duyduğumuz belirli bilgiler ve nerede bulabileceğiniz ve iyi bir yeniden oluşturma oluşturma hakkında daha fazla bilgi edinmek için okumaya devam edin.

### <a name="the-toolset-version"></a>Araç kümesi sürümü

Soruna neden olan araç takımının tam sürüm bilgilerine ve hedef mimarisine ihtiyacımız var. Bu nedenle, yeniden oluşturma için makinelerimizde aynı araç setine karşı test yapabiliriz. Sorunu yeniden oluşturamıyorsanız bu bilgiler, araç takımının diğer sürümlerinin aynı soruna sahip olduğunu araştırmak için bir başlangıç noktası da sunar.

#### <a name="to-report-the-full-version-of-your-compiler"></a>Derleyicinin tam sürümünü raporlamak için

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici komut istemi** açın. Örneğin, x64 için x64 hedefleri için Visual Studio 2017 kullanarak derleme yaparsanız, **VS 2017 için x64 yerel araçları komut istemi**seçin. Daha fazla bilgi için bkz. [Geliştirici komut istemi kısayolları](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts).

1. Geliştirici komut istemi konsol penceresinde **CL/v**komutunu girin.

Çıktının şuna benzer olması gerekir:

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

Tüm çıktıyı kopyalayıp raporunuza yapıştırın.

### <a name="the-command-line"></a>Komut satırı

Kodunuzu derlemek için kullanılan tam komut satırı olan CL. exe ve tüm bağımsız değişkenleri gereklidir. Bu nedenle, makinelerimizde tam olarak aynı şekilde derleyebiliriz. Bulduğunuz sorun yalnızca belirli bir bağımsız değişken veya bağımsız değişken birleşimi ile oluşturulurken mevcut olabileceğinden, bu önemlidir.

Bu bilgileri bulmanın en iyi yeri, sorun yaşandıktan hemen sonra derleme günlüğünde bulunur. Komut satırının, soruna katkıda bulunma ile tam olarak aynı bağımsız değişkenleri içerdiğinden emin olur.

#### <a name="to-report-the-contents-of-the-command-line"></a>Komut satırının içeriğini raporlamak için

1. **CL. Command. 1. TLog** dosyasını bulun ve açın. Bu dosya, varsayılan olarak, \\ Visual Studio *Sürüm*\\projeler klasöründe bulunur\\*SolutionName*\\*ProjectName*\\*Configuration*\\*ProjectName*. TLog\\CL. Command. 1. TLog, ya da \\Source\\\\CL. Command. 1. TLog.\\\\\\\\ Başka bir yapı sistemi kullanıyorsanız veya projeniz için varsayılan konumu değiştirdiyseniz, farklı bir konumda olabilir.

   Bu dosyanın içinde, kaynak kodu dosyalarınızın adlarını, ardından her biri ayrı satırlarda derlemek için kullanılan komut satırı bağımsız değişkenlerini bulacaksınız.

1. Sorunun gerçekleştiği kaynak kodu dosyasının adını içeren çizgiyi bulun. Aşağıdaki satır, karşılık gelen CL. exe komut bağımsız değişkenlerini içerir.

Tüm komut satırını kopyalayıp raporunuza yapıştırın.

### <a name="a-description-of-the-problem"></a>Sorunun açıklaması

Bulduğunuz sorunun ayrıntılı bir açıklamasına ihtiyacımız var. Bu nedenle makinelerimizde aynı etkiyi görtiğimiz için bu şekilde emin olduğumuz. Ayrıca, ne yapmak istediğimizi ve ne olması gerektiğini bilmemiz için bazen yararlı olur.

İyi bir açıklama, araç kümesi tarafından verilen **tam hata iletilerini** veya gördüğünüz tam çalışma zamanı davranışını sağlar. Sorunu doğru bir şekilde oluşturduğumuz doğrulamak için bu bilgilere ihtiyacımız var. Yalnızca son hata iletisini değil, **Tüm** derleyici çıkışını dahil edin. Rapor ettiğiniz sorunu gösteren her şeyi görmemiz gerekiyor. Komut satırı derleyicisini kullanarak sorunu çoğaltabilir, bu Derleyici çıktısı tercih edilir. IDE ve diğer yapı sistemleri, gördüğünüz hata iletilerini filtreleyebilir veya yalnızca bir hata iletisinin ilk satırını yakalayabilir.

Sorun derleyicinin geçersiz kodu kabul etmesidir ve bir tanılama oluşturmaz, Bunu raporunuza dahil edin.

Çalışma zamanı davranış sorununu raporlamak için, programın yazdırdıklarının **tam bir kopyasını** ve görmeyi beklediğiniz öğeleri ekleyin. İdeal olarak, bunu çıkış ifadesinin kendisine katıştıracaksınız, örneğin, `printf("This should be 5: %d\n", actual_result);`. Programınız kilitlenirse veya askıda kalırsa, bu da bunu bahsetme.

Bulduğunuz herhangi bir Work-arounds gibi bulduğunuz sorunu tanılamanıza yardımcı olabilecek diğer ayrıntıları ekleyin. Raporunuzda başka bir yerde bulunan bilgileri yinelemenize çalışın.

### <a name="the-repro"></a>Yeniden üretme

Yeniden *oluşturma işlemi* , tam, kendi kendine içerilen bir kaynak kodu örneğidir. BT reproducibly, bulduğunuz sorunu, dolayısıyla adını gösterir. Makinelerimizde hatayı yeniden oluşturabilmeniz için yeniden üretme gerekir. Kod, derlenen ve çalıştırılan temel bir yürütülebilir dosya oluşturmak için kendine yeterli olmalıdır. Ya da, *bulduğunuz sorun için yoksa derleyip çalıştırılır* . Yeniden üretme bir kod parçacığı değildir. Tüm işlevleri ve sınıfları olmalıdır ve standart üstbilgiler için bile tüm gerekli #include yönergelerini içermelidir.

#### <a name="what-makes-a-good-repro"></a>İyi yeniden üretme ne yapar

İyi bir yeniden üretme:

- **En az.** Yeniden uzmanları mümkün olduğunca küçük olmalıdır, ancak yine de bulduğunuz sorunu tam olarak gösterir. Yeniden uzmanlarının karmaşık veya gerçekçi olması gerekmez. Yalnızca standart ya da belgelenen derleyici uygulamasına uyan kodu göstermesi gerekir. Eksik bir tanılama için yeniden oluşturma, uyumlu olmayan kodu göstermelidir. Yalnızca sorunu göstermek için yeterli kod içeren basit ve noktadan noktaya yeniden uzmanları en iyisidir. Kodu ortadan kaldırabilir veya basitleştirebilir ve uyumlu kaldıysanız ve aynı zamanda sorunu değiştirmeden bırakırsanız, bunu yapın. Bu kodun çalışması için sayaç örnekleri eklemeniz gerekmez.

- **Kendi kendine dahil.** Reprofesyonelleri, gereksiz bağımlılıklardan kaçınmalıdır. Sorunu üçüncü taraf kitaplıklar olmadan yeniden oluşturabilmeniz için bunu yapın. Sorunu basit çıkış deyimlerinin yanı sıra herhangi bir kitaplık kodu olmadan yeniden üretemede (örneğin, `puts("this shouldn't compile");`, `std::cout << value;`ve `printf("%d\n", value);`), bunu yapın. Örnek, herhangi bir Kullanıcı başlığına başvuru olmadan tek bir kaynak kod dosyası ile dar ise idealdir. Sorun için olası bir katkıda bulunanı göz önünde bulundurmanız gereken kod miktarını azaltmak, bizim için çok yararlı olabilir.

- **En son derleyici sürümüne karşı.** Reprofesyonelleri, mümkün olduğunda en son güncelleştirmenin en son sürümünü kullanmalıdır. Ya da bir sonraki güncelleştirmenin veya sonraki ana yayının en son yayın öncesi sürümünü kullanın. Araç takımının eski sürümlerinde bulabileceğiniz sorunlar genellikle daha yeni sürümlerde düzeltilmiştir. Düzeltmeler yalnızca olağanüstü koşullarda eski sürümlere karşı geri alınır.

- İlgiliyse, **diğer derleyicilere karşı denetlenir** . Taşınabilir C++ kod içeren reprofesyonelleri, mümkünse diğer derleyicilere karşı davranışı doğrulamalıdır. C++ Standart olarak program doğruluğu belirlenir ve hiçbir derleyici kusursuz değildir. Ancak, Clang ve GCC, kodunuzu bir tanılama olmadan kabul eder ve MSVC değilse, büyük olasılıkla derleyicimizde bir hata bulmışsınızdır. (Diğer olasılıklar UNIX ve Windows davranışlarındaki farkları veya farklı C++ standartlar uygulama seviyelerini içerir.) Tüm derleyiciler kodunuzu reddettiğinizde, kodunuzun hatalı olması olasıdır. Farklı hata iletilerini görmek sorunu kendi başınıza tanılamanıza yardımcı olabilir.

   Kodunuzu test etmek için çevrimiçi derleyicilerin listesini, ISO C++ Web sitesindeki [çevrimiçi C++ derleyicilerde](https://isocpp.org/blog/2013/01/online-c-compilers) veya GitHub 'daki [çevrimiçi C++ derleyicilerin bu listede](https://arnemertz.github.io/online-compilers/) yer alan bu listede bulabilirsiniz. Bazı belirli örnekler [Wandbox](https://wandbox.org/), [derleyici Gezgini](https://godbolt.org/)ve [Coliru](https://coliru.stacked-crooked.com/)içerir.

   > [!NOTE]
   > Çevrimiçi derleyici Web siteleri Microsoft ile bağlantılı değildir. Birçok çevrimiçi derleyici Web sitesi kişisel projeler olarak çalıştırılır. Bu sitelerden bazıları bunu okurken kullanılamayabilir, ancak bir aramanın kullanabileceğiniz diğerlerini bulması gerekir.

Derleyicide, bağlayıcıda ve kitaplıklarda bulunan sorunlar kendilerini belirli yollarla göstermeye eğilimlidir. Bulduğunuz sorun türü, raporunuza ne tür bir yeniden üretme ekleneceğini belirleyecektir. Uygun bir yeniden üretme olmadan araştırılacağı bir şey yok. Görebileceğiniz bazı sorun türleri aşağıda verilmiştir. Her tür sorunu raporlamak için kullanmanız gereken yeniden üretme türünü nasıl üretiyoruz hakkında yönergeler ekledik.

#### <a name="frontend-parser-crash"></a>Ön uç (Ayrıştırıcı) kilitlenmesi

Ön uç kilitlenmeler derleyicinin ayrıştırma aşamasında oluşur. Genellikle, derleyici [önemli hata C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md)yayar ve hatanın gerçekleştiği kaynak kod dosyasına ve satır numarasına başvurur. Genellikle msc1. cpp adlı bir dosyanın bahsetmektedir, ancak bu ayrıntıyı yoksayabilirsiniz.

Bu tür bir kilitlenme için [önceden işlenmiş](#preprocessed-repros)bir yeniden üretme sağlayın.

Bu tür bir kilitlenme için örnek Derleyici çıktısı aşağıda verilmiştir:

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

Derleyicinin kod oluşturma aşamasında arka uç kilitlenmeler oluşur. Genellikle, derleyici [önemli hata C1001](../error-messages/compiler-errors-1/fatal-error-c1001.md)yayar ve sorun ile ilişkili kaynak kodu dosyasına ve satır numarasına başvurmayabilir. Genellikle dosya derleyicisi\\UTC\\src\\P2\\Main. c ' dir, ancak bu ayrıntıyı yoksayabilirsiniz.

Bu tür bir kilitlenme için, CL. exe ' ye yönelik **/GL** komut satırı bağımsız değişkeni tarafından etkinleştirilen bağlantı zamanı kod ÜRETIMI (LTCG) kullanıyorsanız bir [bağlantı yeniden üretme](#link-repros) sağlayın. Aksi takdirde, bunun yerine [önceden işlenmiş](#preprocessed-repros) yeniden oluşturma sağlayın.

Aşağıda, LTCG 'nin kullanılmayan bir arka uç kilitlenme için örnek Derleyici çıktısı verilmiştir. Derleyici çıktılarınız aşağıdaki gibi görünüyorsa, [önceden işlenmiş](#preprocessed-repros)bir yeniden oluşturma sağlamalısınız.

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

**IÇ DERLEYICI hatası** ile başlayan çizgi, CL. exe yerine LINK. exe ' ye bahsetdi, LTCG etkindir. Bu durumda bir [bağlantı yeniden üretme](#link-repros) sağlayın. LTCG 'nin derleyici hata iletisinden etkinleştirilip etkinleştirilmediğini temizlemeden, komut satırı bağımsız değişkenlerini inceleyin. Bunları yapı günlüğinizden, **/GL** komut satırı bağımsız değişkeni için önceki bir adımda kopyaladınız.

#### <a name="linker-crash"></a>Bağlayıcı kilitlenmesi

Bağlayıcı çöküyor, derleyici çalıştırıldıktan sonra bağlama aşamasında oluşur. Genellikle bağlayıcı, [bağlayıcı araçları hata LNK1000](../error-messages/tool-errors/linker-tools-error-lnk1000.md)' i yayacaktır.

> [!NOTE]
> Çıkış C1001 bahsetmektedir veya bağlama zamanı kodu oluşturma içeriyorsa, bunun yerine [arka uç (kod oluşturma) kilitlenmesiyle](#backend-code-generation-crash) bağlantı altına bakın.

Bu tür bir kilitlenme için, bir [bağlantı yeniden üretme](#link-repros)sağlayın.

Bu tür bir kilitlenme için derleyici çıkışı örneği aşağıda verilmiştir:

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

Artımlı bağlama etkinse ve kilitlenme yalnızca başarılı bir başlangıç bağlantısından sonra gerçekleştiyse, diğer bir deyişle, daha sonra artımlı bir bağlantının temel aldığı ilk tam bağlantıdan sonra, kaynağa karşılık gelen nesne (. obj) ve kitaplık (. lib) dosyalarının bir kopyasını da sağlar ilk bağlantı tamamlandıktan sonra değiştirilen dosyalar.

#### <a name="bad-code-generation"></a>Hatalı kod oluşturma

Hatalı kod oluşturma nadir bir durumdur. Derleyici yanlışlıkla hatalı kodu oluşturduğunda, bu durum uygulamanızın çalışma zamanında kilitlenmesine neden olur. Bunun yerine, doğru kod üretecek veya derleme zamanında bir sorun algılamamalıdır. Bulduğunuz sorunun hatalı kod oluşturulmasına neden olduğunu düşünüyorsanız, raporunuzu [arka uç (kod oluşturma) kilitlenmesiyle](#backend-code-generation-crash)aynı şekilde değerlendirin.

Bu tür bir kilitlenme için, CL. exe için **/GL** komut satırı bağımsız değişkenini kullanıyorsanız bir [bağlantı yeniden üretme](#link-repros) sağlayın. Değilse, [önceden işlenmiş yeniden üretme](#preprocessed-repros) sağlayın.

## <a name="how-to-generate-a-repro"></a>Yeniden üretme oluşturma

Sorunun kaynağını izlememize yardımcı olması için iyi bir yeniden [üretme](#what-makes-a-good-repro) hayati önem taşır. Belirli türlerde reprofesyonelleri için aşağıda özetlenen adımlardan herhangi birini yapmadan önce, sorunu mümkün olduğunca çok belirten kodu ayrıştırmayı deneyin. Bağımlılıkları, gerekli üstbilgileri ve kitaplıkları ortadan kaldırmaya veya en aza indirmenize çalışın. Mümkünse, kullanılan derleyici seçeneklerini ve Önişlemci tanımlarını sınırlayın.

Aşağıda, farklı türlerde sorunları raporlamak için kullanacağınız çeşitli türlerde reprofesyonelleri oluşturmaya yönelik yönergeler verilmiştir.

### <a name="preprocessed-repros"></a>Ön işlenmiş yeniden uzmanları

*Önceden işlenmiş* yeniden oluşturma bir sorunu gösteren tek bir kaynak dosyasıdır. C Önişlemci çıktısından oluşturulur. Bir tane oluşturmak için özgün yeniden üretme kaynak dosyasında **/p** derleyici seçeneğini kullanın. Bu seçenek, ek kaynak ve üstbilgi dosyalarındaki bağımlılıkları kaldırmak için dahil edilen üst bilgileri geçersiz kılar. Bu seçenek ayrıca, yerel ortamınıza bağlı olabilecek makroları, #ifdef koşulları ve diğer Önişlemci komutlarını da çözümler.

> [!NOTE]
> Önceden işlenmiş yeniden kullanım profesyonelleri, genellikle sorunu düzelttiğimiz bir sorun olup olmadığını görmek için en son sürmekte olan uygulamanızı yerine getirme işlemini yapmak istediğimiz için standart kitaplık uygulamamızda hataların sonucu olabilecek sorunlar için yararlı değildir. Bu durumda, yeniden oluşturma işlemini önceden işlemez ve sorunu tek bir kaynak dosyayla azaltamıyorsanız kodunuzu bir. zip dosyasına veya benzer şekilde paketleyin ya da IDE projesi yeniden oluşturma kullanmayı deneyin. Daha fazla bilgi için bkz. [diğer reprofesyonelleri](#other-repros).

#### <a name="to-preprocess-a-source-code-file"></a>Kaynak kodu dosyasını önceden işlemek için

1. [Komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line)bölümünde açıklandığı şekilde, yeniden oluşturma yapınızı oluşturmak için kullanılan komut satırı bağımsız değişkenlerini yakalayın.

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici komut istemi** açın.

1. Yeniden üretme projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde **CL/p** *arguments* *filename. cpp*komutunu girin. *Bağımsız değişkenler*için, yukarıda yakaladığınız bağımsız değişkenlerin listesini kullanın. *filename. cpp* yeniden üretme kaynak dosyanızın adıdır. Bu komut yeniden üretme için kullandığınız komut satırını çoğaltır, ancak Önişlemci geçişinden sonra derlemeyi sonlandırır. Daha sonra, önceden işlenmiş kaynak kodunu *filename. ı*dosyasına yazar.

Bir C++/CX kaynak kodu dosyasını ön işleme alıyorsa veya C++ modüller özelliğini kullanıyorsanız, bazı ek adımlar gerekir. Daha fazla bilgi için aşağıdaki bölümlere bakın.

Önceden işlenmiş dosyayı oluşturduktan sonra, önceden işlenmiş dosyayı derlerken sorunun hala olumlu hale geldiğinden emin olmak iyi bir fikirdir.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Önceden işlenmiş dosyayı doğrulamak için yine de hatanın yeniden olumlu olması

1. Geliştirici komut istemi konsol penceresinde, CL. exe *' nin önceden* işlenmiş C++ dosyayı kaynak dosya olarak derlemesine bildirmek için, CL *filename. i* **komutunu girin** . *Bağımsız* değişkenler yukarıda yakalanan bağımsız değişkenlerle aynıdır, ancak tüm **/d** ve **/ı** bağımsız değişkenleri kaldırılır. Bunun nedeni, önceden işlenmiş dosyaya zaten dahil edilmiştir. *dosya adı. i* , önceden işlenmiş dosyanızın adıdır.

1. Sorunun yeniden üretildiğini doğrulayın.

Son olarak, önceden işlenmiş yeniden oluşturma *dosya adı*. i raporunuza ekleyin.

### <a name="preprocessed-ccx-winrtuwp-code-repros"></a>Önceden işlenmiş C++/CX WINRT/UWP kodu yeniden uzmanları

Yürütülebilir dosyanızı oluşturmak için C++/CX kullanıyorsanız, önceden işlenmiş yeniden oluşturma işlemi oluşturmak ve doğrulamak için gereken bazı ek adımlar vardır.

#### <a name="to-preprocess-ccx-source-code"></a>/CX kaynak kodunu C++önceden işlemek için

1. [Kaynak kodu dosyasını önceden Işlemek için](#to-preprocess-a-source-code-file)bölümünde açıklandığı gibi önceden işlenmiş bir kaynak dosya oluşturun.

1. Oluşturulan _dosya adı_. ı dosyasını **#using** yönergeler için arayın.

1. Başvurulan tüm dosyaların bir listesini oluşturun. Tüm Windows\*. winmd dosyalarını, platform. winmd dosyalarını ve mscorlib. dll ' yi kapatın.

Önceden işlenmiş dosyanın sorunu hala yeniden ürettiğini doğrulamaya hazırlanmak için

1. Önceden işlenmiş dosya için yeni bir dizin oluşturun ve yeni dizine kopyalayın.

1. **#Using** listenizden. winmd dosyalarını yeni dizine kopyalayın.

1. Yeni dizinde boş bir vccorlib. h dosyası oluşturun.

1. Mscorlib. dll ' nin tüm **#using** yönergelerini kaldırmak için önceden işlenmiş dosyayı düzenleyin.

1. Tüm mutlak yolları kopyalanan. winmd dosyaları için yalnızca çıplak dosya adlarıyla değiştirmek üzere önceden işlenmiş dosyayı düzenleyin.

Önceden işlenmiş dosyanın, yukarıdaki gibi hala sorunu yeniden ürettiğini onaylayın.

### <a name="preprocessed-c-modules-repros"></a>Önceden işlenmiş C++ modüller yeniden uzmanları

C++ Derleyicinin modüller özelliğini kullanıyorsanız, önceden işlenmiş yeniden oluşturma işlemi oluşturmak ve doğrulamak için gereken bazı farklı adımlar vardır.

#### <a name="to-preprocess-a-source-code-file-that-uses-a-module"></a>Modül kullanan bir kaynak kodu dosyasını önceden işlemek için

1. [Komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line)bölümünde açıklandığı şekilde, yeniden oluşturma yapınızı oluşturmak için kullanılan komut satırı bağımsız değişkenlerini yakalayın.

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici komut istemi** açın.

1. Yeniden üretme projenizi içeren dizine geçin.

1. Geliştirici komut istemi konsol penceresinde **CL/p** *arguments* *filename. cpp*komutunu girin. *Bağımsız değişkenler* yukarıda yakalanan bağımsız değişkenlerdir ve *filename. cpp* , modülü tüketen kaynak dosyanın adıdır.

1. Modül arabirimini (. ifc çıkışı) oluşturan yeniden üretme projesini içeren dizine geçin.

1. Modül arabiriminizi derlemek için kullanılan komut satırı bağımsız değişkenlerini yakalayın.

1. Geliştirici komut istemi konsol penceresinde **CL/p** *arguments* *ModuleName. IXX*komutunu girin. *Bağımsız değişkenler* yukarıda yakalanan bağımsız değişkenlerdir ve *ModuleName. IXX* modül arabirimini oluşturan dosyanın adıdır.

Önceden işlenmiş dosyaları oluşturduktan sonra, önceden işlenmiş dosyayı kullanırken sorunun hala olumlu hale geldiğinden emin olmak iyi bir fikirdir.

#### <a name="to-confirm-the-preprocessed-file-still-repros-the-error"></a>Önceden işlenmiş dosyayı doğrulamak için yine de hatanın yeniden olumlu olması

1. Geliştirici konsolu penceresinde yeniden üretme projenizi içeren dizine dönün.

1. Önceden işlenmiş dosyayı bir C++ kaynak dosyası gibi derlemek için, **Yukarıdaki dosya** *adı*. **i komutunu yukarıdaki** şekilde yazın.

1. Sorunun önceden işlenmiş dosya tarafından hala yeniden üretildiğini doğrulayın.

Son olarak, önceden işlenmiş yeniden oluşturma dosyalarını (*filename*. i ve *ModuleName*. i) rapora. ifc çıkışı ile birlikte iliştirin.

### <a name="link-repros"></a>Yeniden uzmanları bağla

*Bağlantı yeniden üretme* , **bağlantı\_yeniden üretme** ortam değişkeni veya [/LINKREPRO](../build/reference/linkrepro.md) bağlayıcı seçeneğine bir bağımsız değişken olarak belirtilen bir dizinin bağlayıcı tarafından oluşturulan içeriğidir. Bağlantı zamanında oluşan bir sorunu topluca gösteren derleme yapıtları içerir. Örneğin, bağlantı zamanı kod oluşturma (LTCG) veya bağlayıcı kilitlenmesiyle ilgili bir arka uç kilitlenmesi bulunur. Bu derleme yapıtları, sorun yeniden üretibilmeleri için bağlayıcı girişi olarak gerekli olanlardır. Bir bağlantı yeniden üretme, bu ortam değişkeni kullanılarak kolayca oluşturulabilir. Bağlayıcının yerleşik yeniden üretme oluşturma özelliğini sunar.

#### <a name="to-generate-a-link-repro-using-the-link_repro-environment-variable"></a>Link_repro ortam değişkenini kullanarak bağlantı yeniden üretme oluşturmak için

1. [Komut satırının içeriğini raporlamak için](#to-report-the-contents-of-the-command-line)bölümünde açıklandığı şekilde, yeniden oluşturma yapınızı oluşturmak için kullanılan komut satırı bağımsız değişkenlerini yakalayın.

1. Projenizi oluşturmak için kullanılan Visual Studio sürümü ve yapılandırma mimarisiyle eşleşen **Geliştirici komut istemi** açın.

1. Geliştirici komut istemi konsol penceresinde, yeniden üretme projenizi içeren dizine geçin.

1. Bağlantı yeniden üretme için *linkrepro* adlı bir dizin oluşturmak üzere **mkdir linkrepro** girin. Başka bir bağlantı yeniden üretme yakalamak için farklı bir ad kullanabilirsiniz.

1. **Bağlantı\_yeniden üretme** ortam değişkenini oluşturduğunuz dizine ayarlamak için **\_yeniden üretme = linkrepro komut kümesi bağlantısını** girin. Derlemeniz farklı bir dizinden çalışıyorsa, çoğu zaman daha karmaşık projeler için de olduğu gibi, **bağlantı\_** yeniden oluşturma işlemi yerine bağlantı yeniden oluşturma dizininizin tam yolunu ayarlayın.

1. Visual Studio 'da yeniden üretme projesi oluşturmak için, geliştirici komut istemi konsol penceresinde, **devenv**komutunu girin. **Bağlantı\_yeniden üretme** ortamı değişkeninin değerinin Visual Studio 'ya görünür olmasını sağlar. Projeyi komut satırında derlemek için, yeniden üretme derlemesini çoğaltmak üzere yukarıda yakalanan komut satırı bağımsız değişkenlerini kullanın.

1. Yeniden üretme projenizi derleyin ve beklenen sorunun oluştuğunu onaylayın.

1. Derlemeyi yapmak için kullandıysanız, Visual Studio 'Yu kapatın.

1. Geliştirici komut istemi konsol penceresinde, **bağlantı\_yeniden üretme** ortam değişkenini temizlemek için **\_yeniden üretme = komut kümesi bağlantısını** girin.

Son olarak, tüm linkrepro dizinini bir. zip dosyasına veya benzer şekilde sıkıştırarak yeniden oluşturma 'yı paketleyin ve raporunuza ekleyin.

**/LINKREPRO** bağlayıcı seçeneği, **bağlantı\_yeniden üretme** ortam değişkeniyle aynı etkiye sahiptir. Oluşturulan bağlantıyı yeniden oluşturma için filtreleyecek adı belirtmek için [/LINKREPROTARGET](../build/reference/linkreprotarget.md) seçeneğini kullanabilirsiniz. **/LINKREPROTARGET**kullanmak için, **/Out** bağlayıcı seçeneğini de belirtmeniz gerekir.

#### <a name="to-generate-a-link-repro-using-the-linkrepro-option"></a>/LINKREPRO seçeneğini kullanarak bağlantı yeniden üretme oluşturmak için

1. Bağlantıyı yeniden oluşturmayı tutacak bir dizin oluşturun. _Dizin yolu_olarak oluşturduğunuz tam dizin yoluna başvuracağız. Boşluk içeriyorsa yolun etrafında çift tırnak işareti kullanın.

1. Bağlayıcı komut satırına **/LINKREPRO:** _Directory-Path_ komutunu ekleyin. Visual Studio 'da, projeniz için **Özellik sayfaları** iletişim kutusunu açın. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin. Daha sonra, **ek seçenekler** kutusuna **/LINKREPRO:** _Directory-Path_ seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

1. Yeniden üretme projenizi derleyin ve beklenen sorunun oluştuğunu onaylayın.

Son olarak, tüm _Dizin-yol bağlantısı yeniden_ üretme dizinini bir. zip dosyasına veya benzer şekilde sıkıştırarak yeniden oluşturma 'yı paketleyin ve raporunuza ekleyin.

### <a name="other-repros"></a>Diğer reprofesyonelleri

Sorunu tek bir kaynak dosya veya önceden işlenmiş yeniden oluşturma ile azaltamaz ve sorun bir bağlantı yeniden üretme gerektirmiyorsa, bir IDE projesi araştırıyoruz. İyi bir yeniden oluşturma oluşturmaya ilişkin tüm yönergeler hala geçerlidir: kod, en az ve kendi kendine dahil olmak üzere. Sorun en son araçlarımızda gerçekleşmeli ve ilgiliyse, diğer derleyicilerde görülmemelidir.

Yeniden oluşturma 'yı en düşük IDE projesi olarak oluşturun, ardından tüm dizin yapısını bir. zip dosyasına sıkıştırarak veya benzer şekilde, raporunuza bağlayın.

## <a name="ways-to-send-your-report"></a>Raporunuzu gönderme yolları

Raporunuzu bize almak için kullanabileceğiniz birkaç iyi yol vardır. Visual Studio 'nun yerleşik [rapor bir sorun aracını](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)veya [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sayfalarını kullanabilirsiniz. Ayrıca, bu sayfanın alt kısmında bir **ürün geri bildirim** düğmesi de bulunur. Bu seçenek, ekran görüntülerini yakalamak ve raporunuzu düzenlemek için IDE 'de yerleşik araçları kullanmak isteyip istemediğinize bağlıdır. Kullanmayı tercih ediyorsanız, doğrudan geliştirici topluluğu Web sitesini kullanabilirsiniz.

> [!NOTE]
> Raporunuzu gönderdikten bağımsız olarak, Microsoft gizliliğinize saygı duyar. Microsoft tüm veri gizliliği yasaları ve yönetmelikleriyle uyumluluğu taahhüt etmektedir. Bize göndereceğiniz verileri nasıl değerlendirdiğimiz hakkında bilgi için [Microsoft gizlilik bildirimi](https://privacy.microsoft.com/privacystatement)' ne bakın.

### <a name="use-the-report-a-problem-tool"></a>Sorun bildir aracını kullanma

Visual Studio 'da **sorun bildir** Aracı, Visual Studio kullanıcılarının yalnızca birkaç tıklamayla sorunları raporladığı bir yoldur. Bulduğunuz sorun hakkında ayrıntılı bilgi göndermek için basit bir form açılır. Daha sonra, IDE 'yi kapatmadan raporunuzu gönderebilirsiniz.

**Sorun bildir** aracı aracılığıyla sorununuzu BILDIRME, IDE 'den kolay ve kullanışlı bir işlemdir. **Hızlı başlatma** arama kutusunun yanındaki **geri bildirim gönder** simgesini seçerek, bu kişiye başlık çubuğundan erişebilirsiniz. Ya da **bir sorun bildirmek** > **Yardım** > **geri bildirim göndermek** için menü çubuğunda bulabilirsiniz.

Bir sorunu bildirmelisiniz, önce geliştirici topluluğunda benzer sorunlar için arama yapın. Sorununuzun daha önce raporlanmış olması durumunda, raporu oylayın ve ek bilgilerle yorum ekleyin. Benzer bir sorun görmüyorsanız, Visual Studio geri bildirim iletişim kutusunun altındaki **yeni sorun bildir** düğmesini seçin ve sorununuzu raporlamak için adımları izleyin.

### <a name="use-the-visual-studio-developer-community-pages"></a>Visual Studio Geliştirici topluluk sayfalarını kullanma

Visual Studio Geliştirici topluluk sayfaları, sorunları bildirmek ve Visual Studio ve C++ derleyici, Araçlar ve kitaplıklar için çözüm bulmak için kullanışlı bir yoldur. [Visual Studio](https://developercommunity.visualstudio.com/spaces/8/index.html), [Mac için Visual Studio](https://developercommunity.visualstudio.com/spaces/41/index.html), [.net](https://developercommunity.visualstudio.com/spaces/61/index.html), [C++](https://developercommunity.visualstudio.com/spaces/62/index.html), [Azure DevOps Services](https://developercommunity.visualstudio.com/spaces/21/index.html)ve [TFS](https://developercommunity.visualstudio.com/spaces/22/index.html)için belirli geliştirici topluluk sayfaları vardır.

Topluluk sekmelerinin altında, her sayfanın üst kısmına yakın bir arama kutusudur. Bunu, sizinkilerle benzer sorunları rapor eden gönderimler bulmak için kullanabilirsiniz. Sorunla ilgili bir çözüm veya diğer yararlı bilgiler zaten var. Birisi daha önce aynı sorunu rapormışsa, yeni bir sorun raporu oluşturmak yerine bu raporda yukarı oy ve açıklama ekleyin. Yeni bir sorunu yorum, oylamak veya raporlamak için, Visual Studio hesabınızda oturum açmanız istenebilir. İlk kez oturum açtığınızda, geliştirici topluluk uygulamasına profilinize erişim vermeyi kabul etmeniz gerekir.

C++ Derleyici, bağlayıcı ve diğer araç ve kitaplıklarla ilgili sorunlar için [C++](https://developercommunity.visualstudio.com/spaces/62/index.html) sayfasını kullanın. Sorun için arama yaptıysanız ve daha önce bildirilmediyse, arama kutusunun yanındaki **sorun bildir** düğmesini seçin. Yeniden üretme kodunuzu ve Komut satırlarınızı, ekran görüntülerini, ilgili tartışmalara bağlantıları ve uygun ve yararlı olduğunu düşündüğünüz diğer bilgileri ekleyebilirsiniz.

> [!TIP]
> Visual Studio 'da C++ araç kümesiyle ilgisi olmayan diğer tür sorunlar (ÖRNEĞIN, UI sorunları, kopuk IDE işlevselliği veya genel kilitlenmeler) için IDE 'de **sorun bildir** aracını kullanın. Bu, ekran görüntüsü özellikleri ve bulduğunuz soruna yol açabilecek Kullanıcı Arabirimi eylemlerini kaydetme özelliği nedeniyle en iyi seçenektir. Bu tür hatalar [Geliştirici topluluğu](https://developercommunity.visualstudio.com/) sitesinde de aranabilir. Daha fazla bilgi için bkz. [Visual Studio ile sorun bildirme](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017).

### <a name="reports-and-privacy"></a>Raporlar ve Gizlilik

**Raporlardaki tüm bilgiler ve tüm yorumlar ve yanıtlar, varsayılan olarak herkese açık bir şekilde görünür**. Normal olarak, diğer kullanıcıların bulduğu sorunları, çözümleri ve geçici çözümleri görmek için topluluğun tamamına izin verdiği için bu bir avantajdır. Bununla birlikte, verilerinizi veya kimliğinizi genel hale getirme konusunda endişe ediyorsanız, gizlilik veya fikri mülkiyet nedenleriyle seçenekleriniz vardır.

Kimliğinizi açığa çıkardıysanız, sizin hakkındaki ayrıntıları açıklayamaz [Yeni bir Microsoft hesabı oluşturun](https://signup.live.com/) . Raporunuzu oluşturmak için bu hesabı kullanın.

**Ortak olan ilk raporun başlığında veya içeriğinde özel tutmak istediğiniz herhangi bir şeyi yerleştirmeyin.** Bunun yerine, ayrıntıları özel olarak ayrı bir yoruma göndereceksiniz. Raporunuzun doğru kişilere yönlendirildiğinden emin olmak için, sorun raporunuzun konu listesine **cppcompiler** ekleyin. Sorun raporu oluşturulduktan sonra, yanıtları ve ekleri kimlerin görebileceğini belirlemek artık mümkündür.

#### <a name="to-create-a-problem-report-for-private-information"></a>Özel bilgiler için bir sorun raporu oluşturmak için

1. Oluşturduğunuz raporda, sorunun özel açıklamasını oluşturmak için **Açıklama Ekle** ' yi seçin.

1. Yanıt Düzenleyicisi 'nde Yanıtla ilgili hedef kitlelerinizi belirtmek için **Gönder** ve **iptal** düğmeleri altındaki açılan menü denetimini kullanın. Yalnızca belirttiğiniz kişiler, bu özel yanıtları ve bunlara dahil ettiğiniz herhangi bir görüntüyü, bağlantıyı veya kodu görüntüleyebilir. Microsoft çalışanları ve kendi kendinize yönelik görünürlüğü sınırlamak için **, moderatör ve orijinal poster** seçeneklerini belirleyin.

1. Yeniden oluşturma için gereken açıklama ve diğer bilgileri, görüntüleri ve dosya eklerini ekleyin. Bu bilgileri özel olarak göndermek için **Gönder** düğmesini seçin.

   İliştirilen dosyalar ve en fazla 10 dosya için 2GB sınırı vardır. Daha büyük karşıya yüklemeler için özel açıklamaınıza karşıya yükleme URL 'SI isteyin.

Bu yorum altındaki tüm yanıtlar, belirttiğiniz aynı kısıtlanmış görünürlüğe sahiptir. Yanıtlardaki açılan denetim, kısıtlanmış görünürlük durumunu doğru bir şekilde göstermese bile geçerlidir.

Gizliliğinizi korumak ve hassas bilgilerinizi genel görünümden korumak için dikkatli olun. Kısıtlanmış yorum altında yanıt vermek için tüm etkileşimi Microsoft ile koruyun. Diğer açıklamalara yanıt vermek, hassas bilgileri yanlışlıkla açıklayabilmeniz için yol açabilir.

## <a name="how-to-report-a-c-documentation-issue"></a>Bir C++ belge sorununu bildirme

Belgelerimizde bildirilen sorunları izlemek için GitHub sorunlarını kullanıyoruz. Artık, yazarlar ve ürün ekipleriyle çok daha zengin bir şekilde etkileşimde bulunmak için doğrudan bir içerik sayfasından GitHub sorunları oluşturabilirsiniz. Bir belgeyle ilgili bir sorun, hatalı kod örneği, kafa karıştırıcı bir açıklama, kritik bir atlama veya hatta yalnızca bir typo görürseniz, kolayca haberdar olabilirsiniz. Sayfanın alt kısmına ilerleyin ve **belge geri bildirimi sağlamak Için oturum aç '** ı seçin. Henüz yoksa bir GitHub hesabı oluşturmanız gerekir. Bir GitHub hesabınız olduğunda, tüm belge sorunlarınızı ve bunların durumlarını görebilirsiniz. Ayrıca, bildirdiğiniz sorun için değişiklik yapıldığında bildirimler alırsınız. Daha fazla bilgi için bkz. [docs.Microsoft.com to A yeni bir geri bildirim sistemi](/teamblog/a-new-feedback-system-is-coming-to-docs).

Belge geri bildirim düğmesini kullandığınızda GitHub 'da bir belge sorunu oluşturursunuz. Sorun, sorunu oluşturduğunuz sayfa hakkında bazı bilgilerle otomatik olarak doldurulur. Sorunun nerede bulunduğunu öğrendiğimiz bu, bu bilgileri düzenlemeyin. Yalnızca neyin yanlış olduğuna ilişkin ayrıntıları ve isterseniz önerilen bir çözümü ekleyin. [Belgelerimiz C++ açık kaynaktır](https://github.com/MicrosoftDocs/cpp-docs/), bu nedenle kendiniz bir çözüm göndermek isterseniz, ' yi kullanabilirsiniz. Belgelerimize nasıl katkıda bulunabileceğiniz hakkında daha fazla bilgi için GitHub 'daki [katkıda bulunan kılavuzumuza](https://github.com/MicrosoftDocs/cpp-docs/blob/master/CONTRIBUTING.md) bakın.
