---
title: 'İzlenecek yol: Komut satırında C programı derleme'
description: Basit bir Merhaba Dünya Style C programının nasıl oluşturulacağını gösteren izlenecek yol.
ms.custom: conceptual
ms.date: 9/10/2020
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
ms.openlocfilehash: 57276f61ca8ff848db0313935bc1841de50f9874
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075614"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>İzlenecek yol: Komut satırında C programı derleme

Visual C++, temel konsol programlarından tam Windows masaüstü uygulamalarına, mobil uygulamalara ve daha fazlasına her şeyi oluşturmak için kullanabileceğiniz bir C derleyicisi içerir.

Bu izlenecek yol, bir metin düzenleyicisi kullanarak temel, "Merhaba, Dünya" stili C programı oluşturmayı ve ardından komut satırında derlemeyi gösterir. C++ ' da komut satırında çalışmayı tercih ediyorsanız, bkz. [Izlenecek yol: komut satırında yerel C++ programı derleme](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md). Komut satırını kullanmak yerine Visual Studio IDE 'yi denemek istiyorsanız, bkz. [Izlenecek yol: projeler ve çözümlerle çalışma (c++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ masaüstü geliştirme IÇIN Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi tamamlamak için, Visual Studio 'Yu ve isteğe bağlı Visual C++ bileşenlerini ya da Visual Studio için derleme araçlarını yüklemiş olmanız gerekir.

Visual Studio, birçok dil ve platformda tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyiciler destekleyen güçlü bir tümleşik geliştirme ortamıdır. Bu özellikler hakkında bilgi edinmek ve ücretsiz Visual Studio Community Edition dahil Visual Studio 'yu indirme ve yükleme hakkında bilgi için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio).

Visual Studio 'nun Visual Studio sürümüne yönelik derleme araçları, C ve C++ programları derlemek için ihtiyaç duyduğunuz yalnızca komut satırı araç takımını, derleyicileri, araçları ve kitaplıkları kurar. Derleme laboratuvarları veya sınıf alıştırmaları için idealdir ve görece hızlı bir şekilde yüklenir. Yalnızca komut satırı araç takımını yüklemek için Visual Studio için derleme araçları 'nı [Visual Studio İndirmeleri](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) sayfasından indirin ve yükleyiciyi çalıştırın. Visual Studio yükleyicisi ' nde, **C++ derleme araçları** iş yükünü seçin ve **yükleme**' yi seçin.

Komut satırında bir C veya C++ programı oluşturabilmeniz için önce araçların yüklendiğini ve bunlara komut satırından erişebildiğinizi doğrulamanız gerekir. Visual C++, komut satırı ortamının kullandığı araçları, üstbilgileri ve kitaplıkları bulması için karmaşık gereksinimlere sahiptir. Bazı hazırlıklar olmadan **düz bir komut istemi penceresinde Visual C++ kullanamazsınız** . Tüm gerekli ortam değişkenleri ayarlanmış olan bir normal komut istemi penceresi olan bir *Geliştirici komut istemi* penceresi gerekir. Neyse ki, Visual C++, komut satırı yapıları için ayarlanmış olan geliştirici komut istemlerini başlatmanız için kısayollar yüklüyor. Ne yazık ki, geliştirici komut istemi kısayollarının ve nerede bulundukları yerlerde, Visual C++ neredeyse her sürümü ve farklı Windows sürümlerinde farklılık vardır. İlk izlenecek yol göreviniz, kullanılacak doğru kısayolu bulmektir.

> [!NOTE]
> Geliştirici komut istemi kısayolu, derleyici ve araçlar için doğru yolları otomatik olarak ayarlar ve tüm gerekli üst bilgiler ve kitaplıklar için. Bu değerlerden bazıları her derleme yapılandırması için farklıdır. Kısayollardan birini kullanmıyorsanız, bu ortam değerlerini kendiniz ayarlamanız gerekir. Daha fazla bilgi için bkz. [komut satırı derlemeleri Için yolu ve ortam değişkenlerini ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md). Derleme ortamı karmaşık olduğundan, kendi kendinize derlemek yerine bir geliştirici komut istemi kısayolunu kullanmanızı önemle tavsiye ederiz.

Bu yönergeler, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

## <a name="open-a-developer-command-prompt-in-visual-studio-2019"></a>Visual Studio 2019 'de bir geliştirici komut istemi açın

Windows 10 ' da Visual Studio 2019 yüklediyseniz, Başlat menüsünü açın ve ardından aşağı kaydırın ve **Visual studio 2019** klasörünü (visual Studio 2019 uygulaması değil) açın. **VS 2019 için geliştirici komut istemi** seçin ve komut istemi penceresini açın.

Farklı bir Windows sürümü kullanıyorsanız, geliştirici komut istemi kısayolunu içeren bir Visual Studio Araçları klasörü için başlangıç menünüzün veya başlangıç sayfası ' na bakın. Windows Search işlevini "Geliştirici komut istemi" ni aramak ve yüklü Visual Studio sürümünüz ile eşleşen bir seçim yapmak için de kullanabilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

::: moniker-end

::: moniker range="vs-2017"

## <a name="open-a-developer-command-prompt-in-visual-studio-2017"></a>Visual Studio 2017 'de bir geliştirici komut istemi açın

Windows 10 ' da Visual Studio 2017 yüklediyseniz, Başlat menüsünü açın ve ardından aşağı kaydırın ve **Visual studio 2017** klasörünü (visual Studio 2017 uygulaması değil) açın. **VS 2017 için geliştirici komut istemi** seçin ve komut istemi penceresini açın.

Farklı bir Windows sürümü çalıştırıyorsanız, geliştirici komut istemi kısayolunu içeren bir Visual Studio Araçları klasörü için başlangıç menünüzün veya başlangıç sayfası ' na bakın. Windows Search işlevini "Geliştirici komut istemi" ni aramak ve yüklü Visual Studio sürümünüz ile eşleşen bir seçim yapmak için de kullanabilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

::: moniker-end

::: moniker range="vs-2015"

## <a name="open-a-developer-command-prompt-in-visual-studio-2015"></a>Visual Studio 2015 'de bir geliştirici komut istemi açın

Windows 10 ' da Microsoft Visual C++ derleme araçları 2015 ' u yüklediyseniz, **Başlat** menüsünü açın ve ardından aşağı kaydırın ve **Visual C++ derleme araçları** klasörünü açın. Komut istemi penceresini açmak için **Visual C++ 2015 x86 yerel araçları komut istemi** seçin.

Farklı bir Windows sürümü çalıştırıyorsanız, geliştirici komut istemi kısayolunu içeren bir Visual Studio Araçları klasörü için başlangıç menünüzün veya başlangıç sayfası ' na bakın. Windows Search işlevini "Geliştirici komut istemi" ni aramak ve yüklü Visual Studio sürümünüz ile eşleşen bir seçim yapmak için de kullanabilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

::: moniker-end

Sonra, Visual C++ Geliştirici komut isteminin doğru şekilde ayarlandığını doğrulayın. Komut istemi penceresinde, yazın `cl` ve çıktının şuna benzer göründüğünü doğrulayın:

```Output
C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
Copyright (C) Microsoft Corporation.  All rights reserved.

usage: cl [ option... ] filename... [ /link linkoption... ]
```

Visual C++ sürümüne ve yüklenen güncelleştirmelere bağlı olarak, geçerli dizin veya sürüm numaralarında farklılıklar olabilir. Yukarıdaki çıkış, gördüklerinize benziyorsa, komut satırında C veya C++ programları oluşturmaya hazırsınız demektir.

> [!NOTE]
> "' CL" gibi bir hata alırsanız bir iç veya dış komut, çalıştırılabilir program veya toplu iş dosyası, "hata C1034 veya hata LNK1104" **CL** komutunu çalıştırdığınızda bir geliştirici komut istemi kullanmıyorsanız ya da Visual C++ yüklemenizde bir sorun oluştu. Devam edebilmeniz için bu sorunu çözmeniz gerekir.

Geliştirici komut istemi kısayolunu bulamazsanız veya girdiğinizde bir hata iletisi alırsanız `cl` Visual C++ yüklemenizin bir sorunu olabilir. Visual Studio 2017 veya sonraki bir sürümünü kullanıyorsanız, Visual Studio yükleyicisi 'nde **C++ iş yüküne sahip masaüstü geliştirmeyi** yeniden yüklemeyi deneyin. Ayrıntılar için bkz. [Visual Studio 'Da C++ desteğini Yüklemeyi](vscpp-step-0-installation.md). Ya da [Visual Studio İndirmeleri](https://visualstudio.microsoft.com/downloads/) sayfasından derleme araçlarını yeniden yükleyin. Bu işe ana kadar bir sonraki bölüme geçmeyin. Visual Studio 'Yu yükleme ve sorun giderme hakkında daha fazla bilgi için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio).

> [!NOTE]
> Bilgisayardaki Windows sürümüne ve sistem güvenlik yapılandırmasına bağlı olarak, geliştirici komut istemi kısayolunun kısayol menüsünü açmak için sağ tıklayıp **yönetici olarak çalıştır** ' ı seçerek bu yönergeyi izleyerek oluşturduğunuz programı başarıyla oluşturup çalıştırın.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C kaynak dosyası oluşturma ve komut satırında derleme

1. Geliştirici komut istemi penceresinde, `cd c:\` geçerli çalışma dizinini C: sürücünüzün köküne değiştirmek için girin. Sonra, `md c:\simple` bir dizin oluşturmak için girin ve ardından `cd c:\simple` Bu dizine geçmek için girin. Bu dizin, kaynak dosyanızı ve derlenen programı tutacaktır.

1. `notepad simple.c`Geliştirici komut istemine yazın. Açılan not defteri uyarı iletişim kutusunda, çalışma dizininizde yeni bir basit. c dosyası oluşturmak için **Evet** ' i seçin.

1. Not defteri 'nde aşağıdaki kod satırlarını girin:

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. **File**  >  Çalışma dizininizde Simple. c dosyasını kaydetmek için Not defteri menü çubuğunda Dosya**Kaydet** ' i seçin.

1. Geliştirici komut istemi penceresine geri dönün. `dir`C:\simple dizininin içeriğini listelemek için komut istemine yazın. Dizin listesinde basit. c kaynak dosyasını görmeniz gerekir, bu, şöyle bir şey görür:

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

   Tarihler ve diğer ayrıntılar bilgisayarınızda farklı olacaktır. Basit. c kaynak kodu dosyanızı görmüyorsanız, oluşturduğunuz c:\simple dizinine değiştirdiğinizden emin olun ve Not defteri 'nde kaynak dosyanızı bu dizine kaydettiğinizden emin olun. Ayrıca, kaynak kodunu. txt uzantısıyla değil. c dosya adı uzantısıyla kaydettiğinizden emin olun.

1. Programınızı derlemek için, `cl simple.c` Geliştirici komut istemine yazın.

   Çalıştırılabilir program adını, derleyicinin görüntülediği çıkış bilgileri satırlarında simple.exe görebilirsiniz:

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
   > "' CL" iç veya dış komut, çalıştırılabilir programı veya toplu iş dosyası, "hata C1034 veya hata LNK1104" gibi bir hata alırsanız, geliştirici komut isteminize doğru şekilde ayarlanmamaktadır. Bu sorunu giderme hakkında daha fazla bilgi için, **Geliştirici komut istemi** bölümüne geri dönün.

   > [!NOTE]
   > Farklı bir derleyici veya bağlayıcı hatası ya da uyarısı alırsanız, hataları düzeltmek için kaynak kodunuzu gözden geçirin, sonra dosyayı kaydedin ve derleyiciyi yeniden çalıştırın. Belirli hatalar hakkında daha fazla bilgi için, bu sayfanın üst kısmındaki arama kutusunu kullanarak hata numarasını arayın.

1. Programınızı çalıştırmak için `simple` komut istemine yazın.

   Program bu metni görüntüler ve sonra çıkar:

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   Tebrikler, komut satırını kullanarak bir C programını derlediniz ve çalıştırdık.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Hello, World" örneği, C programının alabilir kadar basit bir işlemdir. Gerçek dünyada programlar üst bilgi dosyalarına ve daha fazla kaynak dosyasına sahiptir, kitaplıklarda bağlantı sağlar ve yararlı işler yapılır.

Gösterilen örnek kodu yazmak yerine kendi C kodunuzu oluşturmak için bu yönergedeki adımları kullanabilirsiniz. Ayrıca, başka bir yerde bulduğunuz birçok C kod örnek programı da oluşturabilirsiniz. Ek kaynak kodu dosyaları olan bir programı derlemek için, bunları komut satırına şu şekilde girin:

`cl file1.c file2.c file3.c`

Derleyici file1.exe adlı bir program çıkışı verir. Adı program1.exe değiştirmek için, bir [/Out](reference/out-output-file-name.md) bağlayıcı seçeneği ekleyin:

`cl file1.c file2.c file3.c /link /out:program1.exe`

Otomatik olarak daha fazla programlama hatası yakalamak için [/w3](reference/compiler-option-warning-level.md) veya [/W4](reference/compiler-option-warning-level.md) uyarı düzeyi seçeneğini kullanarak derlemeyi öneririz:

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

cl.exe derleyicisinde, kodunuzun derlenmesi, iyileştirilmesi, hata ayıklaması ve çözümlenmesi için uygulayabileceğiniz çok daha fazla seçenek bulunur. Hızlı bir liste için, `cl /?` Geliştirici komut istemine yazın. Ayrıca, ayrı olarak derleyip bağlayabilir ve bağlayıcı seçeneklerini daha karmaşık derleme senaryolarında uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanımı hakkında daha fazla bilgi için bkz.  [C/C++ oluşturma başvurusu](reference/c-cpp-building-reference.md).

Komut satırında daha karmaşık projeler yapılandırmak ve derlemek için NMAKE ve makefiles, MSBuild ve proje dosyalarını kullanabilirsiniz. Bu araçları kullanma hakkında daha fazla bilgi için bkz. [NMAKE Başvurusu](reference/nmake-reference.md) ve [MSBuild](msbuild-visual-cpp.md).

C ve C++ dilleri benzerdir, ancak aynı değildir. Microsoft C/C++ derleyicisi (MSVC), kodunuzu derlediğinde hangi dilin kullanılacağını belirleyen basit bir kural kullanır. Varsayılan olarak, MSVC derleyicisi. c ile biten tüm dosyaları C kaynak kodu olarak ve. cpp ile biten tüm dosyaları C++ kaynak kodu olarak değerlendirir. Derleyicinin tüm dosyaları dosya adı uzantısına bağlı olmayan C olarak kabul etmeye zorlamak için [/TC](reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneğini kullanın.

MSVC, ISO C99 standardı ile uyumludur, ancak kesinlikle uyumlu değildir. Çoğu durumda, taşınabilir C kodu, beklendiği gibi derleyip çalıştırılır. Visual C++ ISO C11/C17 içindeki değişiklikler için destek sağlar. C11/C17 desteğiyle derlemek için, derleyici bayrağını `/std:c11` veya kullanın `/std:c17` . Belirli kitaplık işlevleri ve POSIX işlev adları MSVC tarafından kullanımdan kaldırılmıştır. İşlevler desteklenir, ancak tercih edilen adlar değişmiştir. Daha fazla bilgi için bkz. CRT ve derleyici uyarısında [güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) [(düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Standart C++ Programı Oluşturma](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C dil başvurusu](../c-language/c-language-reference.md)<br/>
[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[Uyumluluk](../c-runtime-library/compatibility.md)
