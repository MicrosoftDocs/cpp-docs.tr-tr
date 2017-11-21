---
title: "Visual C++ araç ile ilgili bir sorun bildirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: ec24a49c-411d-47ce-aa4b-8398b6d3e8f6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4a669b2935e4c21421d0c760e6de0c5c7340bed4
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Visual C++ araç ile ilgili bir sorun bildirme

Visual C++ Derleyici, bağlayıcı veya diğer araçlar sorunlarla karşılaşırsanız, bunları hakkında bilmek isteriz.

Bir sorun hakkında bilmeniz bize en iyi yolu, bize sorunla karşılaşıldı programınız ve kendi makinelerde problemi kullanırız biraz kod nasıl oluşturmakta olduğunuz hakkında ayrıntılar açıklamasını içeren bir rapor göndermektir. Bu bilgiler, hızlı bir şekilde sorun var ve ortamınız için yerel değil doğrulayın, derleyici ve nedenini tanılamak için diğer sürümleri etkileyip etkilemediğini belirlemek olanak sağlar.

Bu belgede, okumanız

- [Raporunuzu hazırlamak nasıl](#prepare), ve ne iyi bir rapor sağlar.

- [Raporunuzu gönderme yolları](#send), ve bunları farklı kılan.

- [Bir yeniden oluşturma oluşturmak nasıl](#generate)ve repros farklı türde.

Raporlarınızı bize ve sizin gibi diğer geliştiriciler için önemlidir. Visual C++ geliştirmemize yardımcı olduğunuz için teşekkür ederiz!

## <a name="prepare"></a>Raporunuzu hazırlama

Yüksek kaliteli rapor oluşturma önemlidir çünkü kendi oldukça zor tam bilgisi olmadan kendi makinelerde karşılaştığınız sorunu yeniden oluşturma. Daha iyi raporunuzu, daha etkili bir şekilde biz olan mümkün yeniden oluşturun ve sorunu tanılamak.

En azından raporunuzu içermelidir

- Kullanmakta olduğunuz araç takımı tam sürüm bilgileri.

- Kodunuzu oluşturmak için kullanılan tam cl.exe komut satırı.

- Karşılaşılan sorunla ayrıntılı bir açıklaması.

- 'Yeniden oluşturma' — kaynak kodu sorun gösterilmektedir.

İçin okumaya öğrenin daha hakkındaki belirli bilgileri biz gereksinimini ve burada bulabilirsiniz.

### <a name="the-toolset-version"></a>Araç takımının sürüm

Böylece biz, yeniden oluşturma aynı araç takımı karşı bizim makinelerde test kullandığınız araç takımı tam sürüm bilgilerini ihtiyacımız var. Sorunu yeniden, bu bilgileri bize Ayrıca hangi bir araç takımı Sergi aynı sorun sürümlerinin araştırmak için bir başlangıç noktası sunar.

#### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>Kullanmakta olduğunuz derleyici'nın tam sürümünü bildirmek için

1. Klavyenizde Windows tuşuna basın ve yazmaya başlayın `Developer Command Prompt`.

1. Seçin **Geliştirici komut istemi** Visual Studio sürümü ile eşleşen sürümünü kullanmakta olduğunuz eşleşmeleri listesinde göründüğünde.

1. İçinde **Geliştirici komut istemi** konsolunda, aşağıdaki komutu girin `cl /Bv /CLR`.

Çıktı aşağıdakine benzer görünmelidir:

```Output
C:\Compiler>cl /Bv /CLR
Microsoft (R) C/C++ Optimizing Compiler Version 18.00.40209
for Microsoft (R) .NET Framework version 4.00.30319.34014
Copyright (C) Microsoft Corporation.  All rights reserved.

Compiler Passes:
 C:\WinCComp\binaries.x86chk\bin\i386\cl.exe:        Version 18.00.40209.0
 C:\WinCComp\binaries.x86chk\bin\i386\c1.dll:        Version 18.00.40209.0
 C:\WinCComp\binaries.x86chk\bin\i386\c1xx.dll:      Version 18.00.40209.0
 C:\WinCComp\binaries.x86chk\bin\i386\c2.dll:        Version 18.00.40209.0
 C:\WinCComp\binaries.x86chk\bin\i386\link.exe:      Version 12.00.40209.0
 C:\WinCComp\binaries.x86chk\bin\i386\mspdb120.dll:  Version 12.00.40209.0
 C:\WinCComp\binaries.x86chk\bin\i386\1033\clui.dll: Version 18.00.40209.0
 Common Language Runtime:                            Version  4.00.30319.34014

cl : Command line error D8003 : missing source filename
```

Kopyalayabilir ve tüm çıktı raporunuzu yapıştırabilirsiniz.

### <a name="the-command-line"></a>Komut satırı

Tam biz bunu tam olarak aynı şekilde bizim makinelerde oluşturabilmeleri kodunuzu oluşturmak için kullanılan komut satırı (cl.exe ve bağımsız değişkenler) ihtiyacımız var. Karşılaşılan sorunla yalnızca belirli bir bağımsız değişken veya bağımsız değişkenler bileşimi ile oluştururken olabileceğinden, bu önemlidir.

Bu bilgileri bulmak için en iyi derleme günlüğünde sorunlu hemen sonra yerdir. Bu komut satırı sorunu katkıda bulunan tam olarak aynı bağımsız değişkenler içeriyor sağlar.

#### <a name="to-report-the-contents-of-the-command-line"></a>Komut satırının içeriğini bildirmek için

1. Bulun **CL.command.1.tlog** dosya ve açın. Varsayılan olarak, bu dosyası şu konumdadır \\...\Visual Studio Version\Projects\SolutionName\ProjectName\Config\ProjectName.tlog\CL.command.1.tlog.

   Bu dosya içinde bunların her birini ayrı satırlara derlemek için kullanılan komut satırı bağımsız değişkenleri ve ardından kaynak kodu dosyaları adlarını bulabilirsiniz.

1. Sorunun nerede oluştuğunu kaynak kodu dosyasının adını içeren satırı bulun; Satır altındaki karşılık gelen cl.exe komutun ve bağımsız değişkenlerini içerir.

Kopyalayın ve tüm komut satırı, rapora yapıştırın.

### <a name="a-description-of-the-problem"></a>Sorun açıklaması

Biz biz bizim makineler aynı etkisini görmek doğrulayabilir karşılaşılan sorunla ayrıntılı bir açıklaması ihtiyacımız; kendi da bazen yararlı bize gerçekleştirmek çalıştığınız ve olmasını beklediğinizi bilmeleri için.

Yeniden oluşturma kodunuzu ve bize yardımcı olabilecek herhangi bir ayrıntıyı sorunu tanılamak anlamanıza yardımcı olmak için gerçekleştirmek çalıştığınız kısa bir açıklaması karşılaştığınız, tüm iş ya gibi, lütfen araç takımı tarafından verilen kesin hata iletileri belirtin. bulunan. Başka bir yerde raporunuzda bulunan bilgileri yinelenen kaçının.

### <a name="the-repro"></a>Yeniden oluşturma

İhtiyacımız bir *yeniden oluşturma*, böylece hata bizim makinelerde üretebileceği sorun gösteren kendi içinde bulunan kaynak kod örneği, karşılaştığınız. Tür karşılaştığınız sorunlar ne tür bir yeniden oluşturma, raporunuza dahil belirler. Uygun bir yeniden oluşturma araştırmak için hiçbir şey sunuyoruz.

Rapor metninizi kısa, kendi içinde bulunan repros doğrudan dahil edilebilir, ancak büyük kaynak kodu repros rapora eklenmesi gerekir. Bir tek kaynak kodu dosyasına azaltılamaz repros rapora bir .zip dosyasına tüm dosyaları içeren dizini sıkıştırma tarafından paketlenmiş veya benzer ve bağlı olmalıdır. Rapor metindeki asla kaynak kodunda her zaman ek senaryoya özgü ayrıntılar bulunması gerekir.

Bize sağlayabilir yeniden oluşturma en iyi türde bir *en az yeniden oluşturma*. Bu sorun göstermek için yeterli kodu içeren bir tek, kendi içinde bulunan kaynak kodu (olmadan kullanıcı üstbilgileri başvurular) dosyasıdır. Yalnızca bu formdaki bir yeniden oluşturma sağlayabilir, kaynak kodu dosyasının raporunuza ekleyin; ihtiyacımız kendi tüm.

Bağımlılıklar olmadan en az bir yeniden oluşturma sorunu sıkıştırmak olamaz, raporunuza içermelidir yeniden oluşturma türü belirlemek için aşağıdaki bölümlere bakın.

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

#### <a name="backend_crash"></a>Arka uç (kod oluşturma) kilitlenme

Arka uç çökme (Crash) kod derleyici oluşturma aşaması sırasında oluşur. Genellikle, derleyici yayma [önemli hata C1001](error-messages/compiler-errors-1/fatal-error-c1001.md)ve başvuru kaynak kodu dosya ve satır numarası sorunla ilişkili; genellikle bir dosya compiler\utc\src\p2\main.c Bahsediyor, ancak bu ayrıntı yoksayabilirsiniz.

Bu çökme türü için lütfen bir [bağlantı yeniden oluşturma](#link-repros) bağlama zamanı kodu oluşturma (LTCG) kullanıyorsanız veya [ön işlemesi yapılan yeniden oluşturma](#preprocessed-repros) değilse. LTGC etkindir `/GL` cl.exe komut satırı bağımsız değişkeni.

Bu tür bir kilitlenme LTCG olduğu için örnek derleyici çıktı **değil** kullanılır. Derleyici çıktı bunun gibi görünürse sağlamalıdır bir [ön işlemesi yapılan yeniden oluşturma](#preprocessed-repros).

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

Çizgi ile başlayan, **iç derleyici hatası** link.exe değinmektedir yerine cl.exe, LTCG etkindir ve sağlamanız bir [bağlantı yeniden oluşturma](#link-repros). Varsa, not için bir önceki adımda Temizle LTCG derleyici hata iletisinden etkin olup olmadığını ihtiyacınız olabilecek incelemek, derleme kopyaladığınız komut satırı bağımsız değişkenleri oturum `/GL` komut satırı bağımsız değişkeni.

#### <a name="linker-crash"></a>Bağlayıcı kilitlenme

Bağlayıcı çökme (Crash) derleyici çalıştıktan sonra bağlama işlemi sırasında oluşur. Genellikle, bağlayıcı yayma [Bağlayıcı araçları hatası LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md).

> [!NOTE]
> Çıkış C1001 söz edilen ya da bağlama zamanı kodu oluşturma içerir oluştuysa, [arka uç (kod oluşturma) kilitlenme](#backend_crash) yerine daha fazla bilgi için.

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

Artımlı bağlantılandırma etkindir ve yalnızca ilk bağladıktan sonra kilitlenme oluştu — diğer bir deyişle, yalnızca ilk tam üzerinde sonraki artımlı bağlantılandırma temel bağlama sonra — lütfen ayrıca nesne (.obj) ve kitaplık bir kopyasını karşılık gelir (.lib) dosyaları belirtin ilk bağlama tamamlandıktan sonra değiştirilen kaynak dosyaları için.

#### <a name="bad-code-generation"></a>Hatalı kod oluşturma

Hatalı kod oluşturma nadir ancak derleyici yanlışlıkla uygulamanız bu sorunu derleme zamanında algılama yerine çalışma zamanı kilitlenmesine neden olacak yanlış kodu oluşturduğunda gerçekleşir. Hatalı kod oluşturma sonuçlarını yaşıyor sorun düşünüyorsanız, raporunuzu aynı şekilde işlem bir [arka uç (kod oluşturma) kilitlenme](#backend_crash).

Bu çökme türü için lütfen bir [bağlantı yeniden oluşturma](#link-repros) bağlama zamanı kodu oluşturma (LTCG) kullanıyorsanız veya [ön işlemesi yapılan yeniden oluşturma](#preprocessed-repros) değilse. LTGC etkindir `/GL` cl.exe komut satırı bağımsız değişkeni.

## <a name="send"></a>Raporunuzu gönderme yolları

Raporunuzu bize almak için birkaç yolu vardır. Visual Studio'nun yerleşik kullanabilirsiniz [bir sorun aracı rapor](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017), ya da e-posta gönderin. Raporunuz için en iyi seçenek sorunla karşılaşıldı nasıl raporunuzu araştırmak mühendisleri ile etkileşim kurmak istediğinizi ve olup ilerleme durumunu izlemek veya raporunuzu topluluğuyla paylaşmak istediğiniz tür bağlıdır.

> [!NOTE]
> Raporunuzu nasıl gönderme bağımsız olarak, Microsoft, gizliliğinize saygı duyar. Biz bize gönderin verileri nasıl işler hakkında daha fazla bilgi için bkz: [Microsoft Visual Studio ürün ailesi gizlilik bildirimi](https://www.visualstudio.com/dn948229).

### <a name="send-an-email"></a>Bir e-posta Gönder

E-posta raporunuzu Visual C++ Takımı'na doğrudan göndermek için başka bir yoldur; bizimle ulaşabilir [ compilercrash@microsoft.com ](mailto:compilercrash@microsoft.com).

E-posta ile raporu göndermeyi seçerseniz, aşağıdaki şablonu, e-posta iletisinin gövdesi olarak kullanabilirsiniz. Bu bilgileri e-posta gövdesindeki dahil değil, kaynak kodu veya diğer dosyaları eklemek unutmayın.

```Example
To: compilercrash@microsoft.com
Subject: Visual C++ Error Report
-----

Compiler version:

CL.EXE command line:

Problem description:

Source code and repro steps:

```

### <a name="use-the-report-a-problem-tool"></a>Rapor bir sorun aracını kullanın

Visual Studio sorun aracında rapor Visual Studio kullanıcıların çeşitli sorunlar yalnızca birkaç tıklama ile rapor bir yoldur. Karşılaştı ve ardından IDE ayrılmadan raporunuzu gönderme sorun hakkında ayrıntılı bilgi belirtmek için kullanabileceğiniz basit bir form sağlar.

Bu belgede ele alınan araç takımı sorun türlerini için alışılmadık sorun araçtır raporu sayesinde, sorun bildirimi; Bununla birlikte, kendi bir seçenek değilse seçebilirsiniz, paketleri tercihlerinizi.

> [!TIP]
> Araç takımı için (örneğin, kullanıcı Arabirimi sorunları, bozuk bir IDE işlevsellik veya genel kilitlenme) ilgili olmayan Visual Studio'da karşılaşabileceğiniz sorunlar diğer tür için bir sorun aracı rapor ekran yeteneklerini nedeniyle özellikle iyi bir seçimdir olabilir ve sorunu neden kayıt UI eylemlerini kendi yeteneği karşılaştı. Hiçbir zaman bu diğer tür hatalara e-posta göndererek bildirmelisiniz compilercrash@microsoft.com.

## <a name="generate"></a>Bir yeniden oluşturma oluştur

Bir yeniden oluşturma, raporlama sorun gösteren bir tam ve müstakil bir kod örneğidir. Bir yeniden oluşturma olan **değil** bir kod parçacığı — oluşturur ve çalıştırır (veya Raporlama sorun tarafından üretilen hataları dışında olur) tam bir örnek olması gerekir. Tüm gerekli içermesi gereken # standart üstbilgi için bile yönergeleri include.

Ayrıca, iyi bir yeniden oluşturma değil

- **En az.** Repros tam olarak karşılaştığınız sorunu hala gösteren sırasında olabildiğince küçük olmalıdır. Repros karmaşık veya gerçekçi olması gerekmez — basit,-noktaya repros daha iyi. Karşı çalışır, ancak yalnızca tanım ise olabilir kod örnekleri arasında gerekmez; soruna neden olan kod örneği gereklidir.

- **Kendi içinde yer alan.** Repros gereksiz bağımlılıkları kaçınmalısınız. Lütfen, üçüncü taraf kitaplıklar olmadan sorunu yeniden oluşturup, bunu yapar. Tüm kitaplık kodu sorunsuz yeniden (`std::out`, `printf()` Tamam olan), lütfen bunu yapın. Biz sorun olası Katılımcısı olarak göz önünde bulundurmanız gereken kod miktarını azaltmak için bize enormously yardımcı olur.

- **En son derleyici sürümü karşı.** Repros mümkün olduğunca Araç Takımı'nın en son sürümünü kullanmanız gerekir. Araç takımı eski sürümleri hala karşılaşabileceğiniz sorunları, daha yeni sürümlerinde çok sık düzeltildi.

- **Diğer derleyiciler karşı kullanıma**, uygunsa. Taşınabilir C++ kodu ile ilgili repros davranışı diğer derleyiciler karşı mümkünse doğrulamanız gerekir.

   Bu adım, kodunuzu zaman MSVC Clang ve GCC disagrees olarak doğru veya yanlış olarak ne zaman MSVC, Clang ve GCC kabul olup kodunuzu hata üretir belirlemeye yardımcı olur.

Rapor farklı türde sorunları için kullanacağınız repros çeşitli türleri oluşturmak için yönergeler aşağıda verilmiştir.

### <a name="preprocessed-repros"></a>Önceden işlenmiş repros

Önceden işlenmiş yeniden oluşturma, bir sorunu gösterir ve özgün kaynak dosyasını işleyerek C önişlemci çıktısını oluşturuldu tek kaynak bir dosyadır. Bu işlem Inlines ek kaynağı ve başlık dosyaları bağımlılıkları kaldırmak için üstbilgileri dahil ve makroları, #ifdefs ve yerel ortamınıza bağlı olan diğer önişlemci komutları da giderir.

> [!NOTE]
> Önceden işlenmiş repros az biz genellikle sorun zaten düzelttik olup olmadığını görmek için en son, devam eden bir uygulama yerine isteyeceksiniz çünkü bizim standart kitaplık uygulaması'nda hataları nedeni olabilir sorunlar için uygun olduğunu unutmayın. Bu durumda, verme yeniden oluşturma önişle ve tek bir kaynak dosyası için sorun indiremezsiniz, kodunuzu bir .zip dosyasına veya benzer paketini veya bir IDE projeyi yeniden oluşturma kullanmayı düşünün (bkz [diğer Repros](#other-repros) aşağıda).

#### <a name="to-preprocess-a-source-code-file"></a>Kaynak kodu dosyasının önişle için

1. Klavyenizde Windows tuşuna basın ve yazmaya başlayın `Developer Command Prompt`.

1. Seçin **Geliştirici komut istemi** Visual Studio sürümü ile eşleşen sürümünü kullanmakta olduğunuz eşleşmeleri listesinde göründüğünde.

1. İçinde **Geliştirici komut istemi** konsol penceresinde, aşağıdaki komutu girin `cl /P argumentsfilename.cpp`.

Önceden işlenmiş (şimdi filename.i) dosyanız olduktan sonra onu emin olmak için iyi bir fikirdir önceden işlenmiş dosyasını kullanarak sorunu hala repros. Kullanabileceğiniz `/TP` önişlemci adımı atlamak için cl.exe söyleyin ve her zamanki gibi derleme yeniden denemek için komut satırı bağımsız değişkeni.

#### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>Onaylamak için hata önceden işlenmiş dosyasıyla repros hala

1. Klavyenizde Windows tuşuna basın ve yazmaya başlayın `Developer Command Prompt`.

1. Seçin **Geliştirici komut istemi** Visual Studio sürümü ile eşleşen sürümünü kullanmakta olduğunuz eşleşmeleri listesinde göründüğünde.

1. İçinde **Geliştirici komut istemi** konsol penceresinde, aşağıdaki komutu girin `cl arguments /TP filename.i`.

1. Sorunu yeniden olduğunu onaylayın.

Son olarak, bu yeniden oluşturma raporunuza ekleyin.

### <a name="link-repros"></a>Bağlantı repros

Bağlantı yeniden oluşturma topluca bağlama zamanı kodu oluşturma (LTCG) veya bir bağlayıcı kilitlenme içeren bir arka uç kilitlenme gibi bağlantı zaman ortaya çıkan bir sorun göstermek derleme yapıları içeren tek bir dizindir; dahil edilen yapı böylece sorunu yeniden giriş bağlayıcı gerekenler ürünleridir. Bağlantı repros kolayca bağlayıcı tarafından sağlanan özellikleri kullanılarak oluşturulabilir.

#### <a name="to-generate-a-link-repro"></a>Bağlantı yeniden oluşturma oluşturmak için

1. Bir komut istemi açın ve aşağıdaki komutu girin `mkdir directory` bağlantı yeniden oluşturma için bir dizin oluşturmak için.

1. Link_repro ortam değişkeni, yeni oluşturduğunuz dizine ayarlayın; Aşağıdaki komutu girin `set link_repro=directory`.

1. Yapı gerçekleştirmek istiyorsanız gelen Visual Studio içinde komut isteminden komutunu girerek başlatın `devenv`. Bu link_repro ortam değişkeninin değerini Visual Studio'ya görünür olmasını sağlar.

1. Uygulamanızı yapılandırmak ve beklenen sorun oluştu onaylayın.

1. 3. adımda başlatılan Visual Studio şimdi kapatın.

1. Link_repro ortam değişkeni temizleyin; komutunu girin`set link_repro=`

Son olarak, tüm bir .zip dosyasına dizin veya benzer sıkıştırarak yeniden oluşturma paketini ve raporunuza ekleyin.

### <a name="other-repros"></a>Diğer repros

Tek kaynak dosyası ya da önceden işlenmiş yeniden oluşturma sorunu indiremezsiniz ve sorun bağlantı yeniden oluşturma gerektirmez, biz araştırabilirsiniz ve IDE projesi. Proje içinde kod hala en az olmalıdır ve bu belgedeki tüm yönerge hala geçerlidir.

Yeniden oluşturma en az bir IDE projesi olarak oluşturun, sonra bir .zip dosyasına veya benzer tüm dizin yapısının sıkıştırarak paketini ve raporunuza ekleyin.