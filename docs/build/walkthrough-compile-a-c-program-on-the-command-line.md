---
title: 'İzlenecek Yol: Komut satırında C programı derleme'
ms.custom: conceptual
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
ms.openlocfilehash: d807fa75b32b515c2222fec9ea9d070266303e33
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335257"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>İzlenecek Yol: Komut satırında C programı derleme

Visual C++, temel konsol programlarından tam Windows Masaüstü uygulamalarına, mobil uygulamalara ve daha fazlasına kadar her şeyi oluşturmak için kullanabileceğiniz bir C derleyicisi içerir.

Bu izleme, metin düzenleyicisi kullanarak temel bir "Hello, World" tarzı C programının nasıl oluşturulup komut satırında nasıl derlenebildiğini gösterir. Komut satırında C++'da çalışmayı tercih ederseniz, [bkz.](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md) Komut satırını kullanmak yerine Visual Studio IDE'yi denemek istiyorsanız, [Walkthrough: Projects and Solutions (C++) ile çalışmak](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ Masaüstü Geliştirme için Visual Studio IDE'yi kullanmak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)bölümüne bakın.

## <a name="prerequisites"></a>Ön koşullar

Bu gözden geçiriyi tamamlamak için Visual Studio ve isteğe bağlı Visual C++ bileşenlerini veya Visual Studio için Yapı Araçları'nı yüklemiş olmalısınız.

Visual Studio, birçok dil ve platform için tam özellikli bir düzenleyiciyi, kaynak yöneticilerini, hata ayıklayıcılarını ve derleyicilerini destekleyen güçlü bir entegre geliştirme ortamıdır. Bu özellikler ve ücretsiz Visual Studio Community sürümü de dahil olmak üzere Visual Studio'yu nasıl indirip yükleyebilirsiniz hakkında bilgi için Visual [Studio'yu yükleyin.](/visualstudio/install/install-visual-studio)

Visual Studio'nun Visual Studio için Yapı Araçları sürümü yalnızca C ve C++ programları oluşturmak için gereken komut satırı araç kümesini, derleyicileri, araçları ve kitaplıkları yükler. Bu laboratuvarlar veya sınıf egzersizleri oluşturmak için mükemmel ve nispeten hızlı yükler. Yalnızca komut satırı araç kümesini yüklemek için [Visual Studio indirme sayfasından Visual Studio](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) için Araçlar Oluştur'u indirin ve yükleyiciyi çalıştırın. Visual Studio yükleyicisinde **C++ yapı araçları** iş yükünü seçin ve **Yükle'yi**seçin.

Komut satırında bir C veya C++ programı oluşturmadan önce, araçların yüklü olduğunu ve bunlara komut satırından erişebileceğinizi doğrulamanız gerekir. Visual C++'ın kullandığı araçları, üstbilgi ve kitaplıkları bulmak için komut satırı ortamı için karmaşık gereksinimleri vardır. Bazı hazırlıklar olmadan **Visual C++'ı düz komut istemi penceresinde kullanamazsınız.** Gerekli tüm ortam değişkenlerini ayarlayan normal bir komut istemi penceresi olan bir *geliştirici komut istemi* penceresine ihtiyacınız vardır. Neyse ki, Visual C++ komut satırı oluşturmaları için ortam ayarlı geliştirici komut istemlerini başlatmanız için kısayollar yükler. Ne yazık ki, geliştirici komutunun adları kısayolları ve bulundukları yer Visual C++'nin hemen hemen her sürümünde ve Windows'un farklı sürümlerinde farklıdır. İlk gözden geçirme göreviniz kullanmak için doğru kısayolu bulmaktır.

> [!NOTE]
> Geliştirici komut istemi kısayolu, derleyici ve araçlar ve gerekli üstbilgi ve kitaplıklar için doğru yolları otomatik olarak ayarlar. Bu değerlerden bazıları her yapı yapılandırması için farklıdır. Kısayollardan birini kullanmıyorsanız, bu ortam değerlerini kendiniz ayarlamanız gerekir. Daha fazla bilgi için [bkz.](setting-the-path-and-environment-variables-for-command-line-builds.md) Yapı ortamı karmaşık olduğundan, kendi ortamınızı oluşturmak yerine geliştirici komut istemi kısayolu kullanmanızı şiddetle öneririz.

Bu talimatlar Visual Studio'nun hangi sürümünü kullandığınıza bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019'da geliştirici komut istemi açma

Visual Studio 2019'u Windows 10'a yüklediyseniz, Başlat menüsünü açın ve ardından aşağı kaydırın ve **Visual Studio 2019** klasörünü (Visual Studio 2019 uygulaması değil) açın. Komut istemi penceresini açmak **için VS 2019 için Geliştirici Komut Komut Ustem Komutu Komut Komut** Ustem'i seçin.

Windows'un farklı bir sürümünü kullanıyorsanız, geliştirici komut istemi kısayolu içeren Visual Studio araçları klasörü için Başlat menüsüne veya Başlat sayfanıza bakın. Windows arama işlevini kullanarak "geliştirici komut istemi" arayabilir ve Visual Studio'nun yüklü sürümünüzle eşleşen bir tane seçebilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017'de geliştirici komut istemi açma

Visual Studio 2017'yi Windows 10'a yüklediyseniz, Başlat menüsünü açın ve ardından aşağı kaydırın ve **Visual Studio 2017** klasörünü (Visual Studio 2017 uygulaması değil) açın. Komut istemi penceresini açmak **için VS 2017 için Geliştirici Komut Komut Ustem Komutu Komut Komut** Ustem'i seçin.

Windows'un farklı bir sürümünü çalıştırıyorsanız, geliştirici komut istemi kısayolu içeren Visual Studio araçları klasörü için Başlat menüsüne veya Başlat sayfanıza bakın. Windows arama işlevini kullanarak "geliştirici komut istemi" arayabilir ve Visual Studio'nun yüklü sürümünüzle eşleşen bir tane seçebilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015'te geliştirici komut istemi açma

Microsoft Visual C++ Build Tools 2015'i Windows 10'a yüklediyseniz, **Başlat** menüsünü açın ve ardından aşağı kaydırın ve **Visual C++ Build Tools** klasörünü açın. Komut istemi penceresini açmak için **Visual C++ 2015 x86 Native Tools Komut Komut İstemi'ni** seçin.

Windows'un farklı bir sürümünü çalıştırıyorsanız, geliştirici komut istemi kısayolu içeren Visual Studio araçları klasörü için Başlat menüsüne veya Başlat sayfanıza bakın. Windows arama işlevini kullanarak "geliştirici komut istemi" arayabilir ve Visual Studio'nun yüklü sürümünüzle eşleşen bir tane seçebilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

::: moniker-end

Ardından, Visual C++ geliştirici komut isteminin doğru şekilde ayarlıştırış olduğunu doğrulayın. Komut istemi penceresinde, `cl` çıktının aşağıdaki gibi göründüğünü girin ve doğrulayın:

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

Visual C++ sürümüne ve yüklenen güncelleştirmelere bağlı olarak geçerli dizin veya sürüm numaralarında farklılıklar olabilir. Yukarıdaki çıktı gördüklerinizin benzersiyse, komut satırında C veya C++ programları oluşturmaya hazırsınız demektir.

> [!NOTE]
> "'cl' gibi bir hata alırsanız bir iç veya dış komut, operable program veya toplu dosya olarak kabul edilmez," hata C1034 veya hata LNK1104 cl **komutu** çalıştırdığınızda, o zaman ya bir geliştirici komut istemi kullanmıyorsanız, ya da bir şey Visual C++ yükleme ile yanlış. Devam etmeden önce bu sorunu gidermeniz gerekir.

Geliştirici komut istemi kısayolu bulamıyorsanız veya girdiğinizde `cl`bir hata iletisi alırsanız, Visual C++ yüklemenizde bir sorun olabilir. Visual Studio 2017 veya sonraki bir tarihte kullanıyorsanız, Visual Studio yükleyicisinde C++ iş **yüküyle Masaüstü geliştirmeyi** yeniden yüklemeyi deneyin. Ayrıntılar için [Visual Studio'da C++ yükle desteğine](vscpp-step-0-installation.md)bakın. Veya [Visual Studio indirme sayfasından](https://visualstudio.microsoft.com/downloads/) Yapı Araçları'nı yeniden yükleyin. Bu işe yarayana kadar bir sonraki bölüme geçme. Visual Studio'nun yüklenmesi ve sorun giderme hakkında daha fazla bilgi için [Visual Studio'yı yükle'ye](/visualstudio/install/install-visual-studio)bakın.

> [!NOTE]
> Bilgisayardaki Windows sürümüne ve sistem güvenliği yapılandırmasına bağlı olarak, geliştirici komut istemi kısayolu için kısayol menüsünü açmak için sağ tıklatmanız ve ardından bu gözden geçirmeyi izleyerek oluşturduğunuz programı başarıyla oluşturmak ve çalıştırmak için **Yönetici olarak Çalıştır'ı** seçmeniz gerekebilir.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C kaynak dosyası oluşturma ve komut satırında derleme

1. Geliştirici komut istemi penceresinde, `cd c:\` geçerli çalışma dizini C: sürücü köküne değiştirmek için girin. Ardından, `md c:\simple` bir dizin oluşturmak için `cd c:\simple` girin ve sonra bu dizine değiştirmek için girin. Bu dizin, kaynak dosyanızı ve derlenen programı tutar.

1. Geliştirici `notepad simple.c` komut istemine girin. Açılan Not Defteri uyarı iletişim kutusunda, çalışma dizininizde yeni bir simple.c dosyası oluşturmak için **Evet'i** seçin.

1. Not Defteri'nde aşağıdaki kod satırlarını girin:

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. Not Defteri menü çubuğunda, çalışma dizininizde simple.c kaydetmek için **Dosya** > **Kaydet'i** seçin.

1. Geliştirici komut istemi penceresine geri dön. `dir` C:\simple directory içeriğini listelemek için komut istemigirin. Kaynak dosya basit.c dizin listesinde, hangi gibi bir şey görünüyor görmeniz gerekir:

    ```Output
    C:\simple>dir
     Volume in drive C has no label.
     Volume Serial Number is CC62-6545

     Directory of C:\simple

    10/02/2017  03:46 PM    <DIR>          .
    10/02/2017  03:46 PM    <DIR>          ..
    10/02/2017  03:36 PM               143 simple.c
                   1 File(s)            143 bytes
                   2 Dir(s)  514,900,566,016 bytes free

    ```

   Tarihler ve diğer ayrıntılar bilgisayarınızda farklılık gösterir. Kaynak kod dosyanızı görmüyorsanız, simple.c, oluşturduğunuz c:\simple dizinine ve Not Defteri'nde kaynak dosyanızı bu dizine kaydettiğinizden emin olun. Ayrıca kaynak kodunu .txt uzantısı ile değil.c dosya adı uzantısı ile kaydettiğinden emin olun.

1. Programınızı derlemek için `cl simple.c` geliştirici komut istemini girin.

   Derleyicinin görüntülebildiği çıktı bilgileri satırlarında çalıştırılabilir program adı simple.exe'yi görebilirsiniz:

    ```Output
    c:\simple>cl simple.c
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
    Copyright (C) Microsoft Corporation.  All rights reserved.

    simple.c
    Microsoft (R) Incremental Linker Version 14.10.25017.0
    Copyright (C) Microsoft Corporation.  All rights reserved.

    /out:simple.exe
    simple.obj
    ```

   > [!NOTE]
   > "'cl' gibi bir hata alırsanız, "dahili veya harici komut, çalışabilir program veya toplu iş dosyası" hatası C1034 veya lNK1104 hatası olarak tanımlanamazsa, geliştirici komut isteminiz doğru şekilde ayarlanmaz. Bu sorunun nasıl giderilenhakkında bilgi için **geliştirici komut istemi** aç bölümüne geri dön.

   > [!NOTE]
   > Farklı bir derleyici veya bağlayıcı hatası veya uyarı alırsanız, hataları düzeltmek için kaynak kodunuzu gözden geçirin, ardından kaydedin ve derleyiciyi yeniden çalıştırın. Belirli hatalar hakkında bilgi almak için, hata numarasını aramak için bu sayfanın üst kısmındaki arama kutusunu kullanın.

1. Programınızı çalıştırmak için `simple` komut istemine girin.

   Program bu metni görüntüler ve sonra çıkar:

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   Tebrikler, komut satırını kullanarak bir C programını derleyip çalıştırdın.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Merhaba, Dünya" örneği hakkında bir C programı alabilirsiniz kadar basittir. Gerçek dünya programları üstbilgi dosyaları ve daha fazla kaynak dosyaları var, kitaplıklarda bağlantı ve yararlı işler yapmak.

Gösterilen örnek kodu yazmak yerine kendi C kodunuzu oluşturmak için bu izbindeki adımları kullanabilirsiniz. Ayrıca başka bir yerde bulabileceğiniz birçok C kodu örnek programları oluşturabilirsiniz. Ek kaynak kodu dosyaları olan bir program derlemek için, bunların tümlerini komut satırına girin:

`cl file1.c file2.c file3.c`

Derleyici file1.exe adlı bir program çıkar. Adı program1.exe olarak değiştirmek için [bir /out](reference/out-output-file-name.md) bağlayıcı seçeneği ekleyin:

`cl file1.c file2.c file3.c /link /out:program1.exe`

Daha fazla programlama hatasını otomatik olarak yakalamak için [/W3](reference/compiler-option-warning-level.md) veya [/W4](reference/compiler-option-warning-level.md) uyarı düzeyi seçeneğini kullanarak derlemenizi öneririz:

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

Derleyici cl.exe, kodunuzu oluşturmak, optimize etmek, hata ayıklamak ve çözümlemek için uygulayabileceğiniz daha birçok seçenek vardır. Hızlı bir liste `cl /?` için geliştirici komut istemine girin. Ayrıca ayrı ayrı derleyebilir ve bağlantı kurabilir ve daha karmaşık yapı senaryolarında bağlayıcı seçenekleri uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanımı hakkında daha fazla bilgi için [C/C++ Yapı Başvurusu'na](reference/c-cpp-building-reference.md)bakın.

Komut satırında daha karmaşık projeleri yapılandırmak ve oluşturmak için NMAKE ve makefiles veya MSBuild ve proje dosyalarını kullanabilirsiniz. Bu araçları kullanma hakkında daha fazla bilgi için [NMAKE Reference](reference/nmake-reference.md) ve [MSBuild adresine](msbuild-visual-cpp.md)bakın.

C ve C++ dilleri benzerdir, ancak aynı değildir. Microsoft C/C++ derleyicisi (MSVC), kodunuzu derlediğinde hangi dili kullanacağınızı belirlemek için basit bir kural kullanır. Varsayılan olarak, MSVC derleyicisi .c ile biten tüm dosyaları C kaynak kodu olarak, .cpp ile biten tüm dosyaları ise C++ kaynak kodu olarak ele alır. Derleyiciyi tüm dosyaları dosya adı uzantısına bağlı olmayan C olarak ele almaya zorlamak için [/Tc](reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneğini kullanın.

MSVC, ISO C99 standardı ile uyumludur, ancak tam olarak uyumlu değildir. Çoğu durumda, taşınabilir C kodu derlenecek ve beklendiği gibi çalışacaktır. Visual C++ ISO C11'deki değişikliklerin çoğunu desteklemez. Bazı kitaplık işlevleri ve POSIX işlev adları MSVC tarafından amortismana alınır. Işlevler desteklenir, ancak tercih edilen adlar değişti. Daha fazla bilgi için [CRT](../c-runtime-library/security-features-in-the-crt.md) ve [Derleyici Uyarısı'ndaki Güvenlik Özellikleri (düzey 3) C4996'ya](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Standart C++ Programı Oluşturma](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C Dil Referansı](../c-language/c-language-reference.md)<br/>
[Projeler ve yapı sistemleri](projects-and-build-systems-cpp.md)<br/>
[Uyumluluk](../c-runtime-library/compatibility.md)
