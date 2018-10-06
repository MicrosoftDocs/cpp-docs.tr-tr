---
title: 'İzlenecek yol: komut satırında C programı derleme | Microsoft Docs'
ms.custom: conceptual
ms.date: 09/24/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
helpviewer_keywords:
- command-line applications [C++], C programs
- Visual C, compiling
- compiling programs [C++]
- C program compiling [C++]
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8361890c264e11fbd5817331e07ba9005da17240
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821380"
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>İzlenecek yol: komut satırında C programı derleme

Visual C++, her şeyin tam Windows Masaüstü uygulamaları, mobil uygulamalar ve daha fazla bilgi için temel bir konsol programlarından oluşturmak için kullanabileceğiniz bir C derleyicisi içerir.

Bu izlenecek yol, temel, "Hello, World" oluşturma işlemi gösterilmektedir-C programının bir metin kullanarak Düzenleyicisi stil ve sonra komut satırında derleyin. C++'ta komut satırında işe yarar olup [izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md). İsterseniz bkz yerine komut satırını kullanarak Visual Studio IDE deneyin [izlenecek yol: projeleri ve çözümleri (C++) çalışma](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için Visual Studio ve Visual C++ isteğe bağlı bileşenler veya derleme araçları Visual Studio için yüklü gerekir.

Visual Studio tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyiciler birçok diller ve platformlar için destekleyen bir güçlü tümleşik geliştirme ortamıdır. Bu özellikler ve ücretsiz Visual Studio Community sürümü dahil olmak üzere Visual Studio yükleyip hakkında daha fazla bilgi için bkz. [Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio).

Visual Studio'nun Visual Studio sürümü için derleme araçları, yalnızca komut satırı araç takımı, derleyiciler, araçları ve kitaplıkları C ve C++ programları oluşturmak için ihtiyacınız yükler. Derleme laboratuvarlarının için mükemmeldir veya sınıf sınayan ve oldukça hızlı bir şekilde yükler. Yalnızca komut satırı araç takımı'nı yüklemek için Yükle [Visual Studio derleme Araçları](https://go.microsoft.com/fwlink/p/?linkid=875721) ve yükleyiciyi çalıştırın.

Komut satırında C veya C++ programı oluşturmadan önce araçların yüklendiğini ve bunları komut satırından erişebildiğinizi doğrulamanız gerekir. Visual C++ için Araçlar, üstbilgiler ve kitaplıkları kullanır bulmak komut satırı ortamını karmaşık gereksinimleri vardır. **Visual C++ bir düz bir komut istemi penceresinde kullanamazsınız** bazı hazırlık olmadan. Gereksinim duyduğunuz bir *Geliştirici komut istemi* ayarlanmış tüm gerekli ortam değişkenleri içeren bir normal komut istemi penceresi penceresinde. Neyse ki, Visual C++ komut satırı derlemeleri için ayarlanan ortam sahip bir geliştirici komut istemleri başlatmak, kısayol yükler. Ne yazık ki, geliştirici komut istemi kısayolları ve bulundukları neredeyse her sürümünde, Visual C++ ve Windows farklı sürümlerini farklı adlarıdır. İlk kılavuz göreviniz, kullanılacak doğru kısayol bulmaktır.

> [!NOTE]
> Bir geliştirici komut istemi kısayolunun doğru yolları derleyici ve araçları ve tüm gerekli üst bilgileri ve kitaplıkları otomatik olarak ayarlar. Her derleme yapılandırması için bu değerlerden bazıları farklıdır. Kısayolları kullanmıyorsanız, bu ortam değerleri kendiniz ayarlamalısınız. Daha fazla bilgi için [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlamak](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Yapı ortamı karmaşık olduğundan, kendi oluşturmak yerine bir geliştirici komut istemi kısayolunun kullanmanız önerilir.

## <a name="open-a-developer-command-prompt"></a>Bir geliştirici komut istemi açın

1. Windows 10'da Visual Studio 2017 yüklediyseniz, Başlat menüsü açın ve ardından aşağı kaydırın ve açın **Visual Studio 2017** klasörü (Visual Studio 2017 uygulama değil). Seçin **VS 2017 için geliştirici komut istemi** komut istemi penceresi açın.

   Windows 10'da Microsoft Visual C++ derleme araçları 2015 yüklü değilse, açmak **Başlat** menüsünü ve sonra aşağı kaydırın ve açık **Visual C++ derleme Araçları** klasör. Seçin **Visual C++ 2015 x86 yerel Araçlar komut istemi** komut istemi penceresi açın.

   Visual Studio'nun farklı bir sürümünü kullanıyorsanız veya farklı bir Windows sürümü çalıştıran arayın, Başlat menüsünde veya başlangıç sayfası için geliştirici komut istemi kısayolunun içeren bir Visual Studio Araçları klasörü. Windows arama işlevi, yüklü Visual Studio sürümünüzle eşleşen birini seçin ve "Geliştirici komut istemi için" arama için de kullanabilirsiniz. Komut İstemi penceresini açmak için kısayolu kullanın.

1. Ardından, Visual C++ Geliştirici komut istemi doğru şekilde ayarlandığını doğrulayın. Komut İstemi penceresinde girin `cl` ve çıktı şuna benzer olduğunu doğrulayın:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Geçerli dizinde veya Visual C++ ve yüklü herhangi bir güncelleştirme sürümüne bağlı olarak, sürüm numaraları farklılıklar olabilir. Yukarıdaki gördüğünüz için benzer bir çıkış, daha sonra komut satırında C veya C++ programları oluşturmaya hazırsınız.

   > [!NOTE]
   > "'Temizle' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor gibi" hata alırsanız hata C1034 veya hata çalıştırdığınızda LNK1104 **cl** ya da bir geliştirici komut istemi kullanmıyorsanız, komut veya Visual C++ yüklemenizle yanlış bir şeydir. Devam etmeden önce bu sorunu düzeltmeniz gerekiyor.

   Geliştirici komut istemi kısayolunun bulamazsa ya da bir hata iletisi alırsanız, girdiğiniz zaman `cl`, sonra da Visual C++ yüklemenizin bir sorun olabilir. Visual Studio 2017'yi kullanıyorsanız, yeniden yüklemeyi deneyin **C++ ile masaüstü geliştirme** Visual Studio Yükleyicisi'nde iş yükü. Ayrıntılar için bkz [Visual Studio'da C++ yükleme desteği](../build/vscpp-step-0-installation.md). Ya da yeniden [Visual Studio derleme Araçları](https://go.microsoft.com/fwlink/p/?linkid=875721). Bu işlemin çalıştığı kadar sonraki bölüme gidin yok. Yükleme ve Visual Studio sorunlarını giderme hakkında daha fazla bilgi için bkz. [Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Sürümüne Windows bilgisayarda ve sistem güvenlik yapılandırmasına, geliştirici komut istemi kısayolunun ilişkin kısayol menüsünü açın ve ardından sağ gerekebilir **yönetici olarak çalıştır** için başarılı bir şekilde oluşturun ve bu izlenecek yolu takip ederek oluşturduğunuz programı çalıştırın.

## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>Bir C kaynak dosyası oluşturun ve komut satırında derleme

1. Geliştirici komut istemi penceresinde girin `cd c:\` , C: sürücüsünün köküne geçerli çalışma dizini değiştirmek için. Ardından, girin `md c:\simple` bir dizin oluşturun ve girmeniz `cd c:\simple` bu dizine gidin. Bu dizin, kaynak dosyanızı ve derlenmiş programın tutar.

1. Girin `notepad simple.c` Geliştirici komut isteminde. Görüntülenen iletideki Not Defteri uyarı iletişim kutusunda, seçmek **Evet** çalışma dizininizde yeni simple.c dosyası oluşturmak için.

1. Not Defteri'nde, aşağıdaki kod satırlarını girin:

    ```C
    #include <stdio.h>

    int main()
    {
        printf("Hello, World! This is a native C program compiled on the command line.\n");
        return 0;
    }
    ```

1. Not Defteri'ni menü çubuğunda **dosya** > **Kaydet** simple.c çalışma dizininizde kaydetmek için.

1. Geliştirici komut istemi penceresine geçin. Girin `dir` c:\simple dizininin içeriğini listelemek için komut isteminde. Kaynak dosya simple.c şuna benzer şekilde görünür dizin listesinde görmeniz gerekir:

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

   Bilgisayarınızda tarih ve diğer ayrıntıları farklılık gösterir. Kaynak kod dosyanız görmüyorsanız simple.c, oluşturduğunuz c:\simple dizine değiştirdiğinizi doğrulayın ve Not Defteri'nde, kaynak dosyanız bu dizine kaydedilmiş emin olun. Ayrıca, kaynak kodu .c dosya adı uzantısına sahip, .txt uzantısı kaydettiğiniz emin olun.

1. Programınızı derlemek için girin `cl simple.c` Geliştirici komut isteminde.

   Yürütülebilir program adını derleyicinin görüntülediği çıktı bilgisi satırlarında simple.exe görebilirsiniz:

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
   > "'Temizle' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor gibi" hata alırsanız hata C1034 veya hatası LNK1104, geliştirici komut istemi, doğru şekilde ayarlanmamış. Bu sorunun çözümü hakkında daha fazla bilgi için geri dön **bir geliştirici komut istemi açın** bölümü.

   > [!NOTE]
   > Farklı bir derleyici veya bağlayıcı hata veya uyarı alırsanız, hataları düzeltin, ardından dosyayı kaydedin ve derleyici yeniden çalıştırmak için kaynak kodu gözden geçirin. Kendi hatalarıyla ilgili daha fazla bilgi için hata numarası aramak için bu sayfanın en üstündeki arama kutusunu kullanın.

1. Programınızı çalıştırmak için girin `simple` komut isteminde.

   Program bu metni görüntüler ve kapanır:

    ```Output
    Hello, World! This is a native C program compiled on the command line.
    ```

   Tebrikler, derlenmiş ve komut satırını kullanarak bir C programını çalıştırın.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Hello, World" örnek olarak bir C programının alabilirsiniz hakkında kadar kolaydır. Gerçek dünya programlarının üst bilgi dosyaları ve daha fazla kaynak dosyaları, bağlantı kitaplıklarında ve yararlı işi vardır.

Gösterilen örnek kod yazmak yerine kendi C kodu derlemek için bu izlenecek yolda adımları kullanabilirsiniz. Ayrıca, başka bir yerde bulabileceğiniz birçok C kodu örnek programını da oluşturabilirsiniz. Ek kaynak kodu dosyaları olan bir program derlemek için bunları tüm komut satırında gibi girin:

`cl file1.c file2.c file3.c`

Derleyici file1.exe adlı bir programı çıkarır. Ekleme için program1.exe adını değiştirmek için bir [/out](../build/reference/out-output-file-name.md) bağlayıcı seçeneği:

`cl file1.c file2.c file3.c /link /out:program1.exe`

Daha fazla programlama hatalarını otomatik olarak çekmek için derleme kullanarak öneririz [/W3](../build/reference/compiler-option-warning-level.md) veya [/W4](../build/reference/compiler-option-warning-level.md) Uyarısı Düzeyi:

`cl /W4 file1.c file2.c file3.c /link /out:program1.exe`

Derleyici, cl.exe'yi uygulama oluşturmak için en iyi duruma getirme, hata ayıklama ve kod çözümleme kullanabileceğiniz pek çok seçenek vardır. Hızlı bir listesi için girin `cl /?` Geliştirici komut isteminde. Ayrıca derlemek ve da ayrı ayrı bağlayın ve derleme daha karmaşık senaryolarda bağlayıcı seçenekleri uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanım hakkında daha fazla bilgi için bkz. [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

NMAKE ve derleme görevleri dosyası ve MSBuild ve proje dosyaları, yapılandırmak ve komut satırında daha karmaşık projeleri oluşturmak için kullanabilirsiniz. Bu araçları kullanarak daha fazla bilgi için bkz: [NMAKE başvurusu](../build/nmake-reference.md) ve [MSBuild](../build/msbuild-visual-cpp.md).

C ve C++ dillerinin benzerdir ancak aynı değildir. Visual C++ derleyicisi, kodunuzu derleyen sırasında kullanmak için hangi dilin belirlemek için basit bir kuralı kullanır. Varsayılan olarak, Visual C++ derleyicisi, .c C kaynak kodu biten tüm dosyaları ve C++ kaynak kodu, .cpp ile biten tüm dosyaları işler. Tüm dosyaları C bağımlı olmayan dosya adı uzantısıyla derleyicinin zorlamak için kullanan [/Tc](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneği.

Visual C++ C Derleyici ISO C99 standardı ile uyumludur, ancak tamamen uyumlu değildir. Çoğu durumda, taşınabilir C kodu derleyin ve beklendiği gibi çalıştırın. Visual C++ ISO C11 içinde yapılan değişikliklerin çoğu desteklemiyor. Belirli bir kitaplığı işlevleri ve POSIX işlev adlarını Visual C++ derleyicisi tarafından kullanım dışı bırakılmıştır. İşlevler desteklenir, ancak tercih edilen adlar değişmiştir. Daha fazla bilgi için [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) ve [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Standart C++ Programı Oluşturma](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)<br/>
[C Dil Başvurusu](../c-language/c-language-reference.md)<br/>
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>
[Uyumluluk](../c-runtime-library/compatibility.md)
