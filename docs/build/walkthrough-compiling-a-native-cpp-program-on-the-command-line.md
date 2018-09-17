---
title: 'İzlenecek yol: komut satırında yerel C++ programı derleme | Microsoft Docs'
ms.custom: conceptual
ms.date: 06/21/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 855b3e3947839a08d920bb27b664ea4ce1027bf8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713129"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme

Visual C++ Evrensel Windows platformu uygulamaları için temel bir konsol uygulamaları, Masaüstü uygulamaları, cihaz sürücüleri ve .NET bileşenleri her şeyi oluşturmak için kullanabileceğiniz komut satırı bir C++ derleyicisi içerir.

Bu kılavuzda, temel, "Hello, World" Oluştur-C++ programı bir metin kullanarak Düzenleyicisi stil ve sonra komut satırında derleyin. İsterseniz bkz yerine komut satırını kullanarak Visual Studio IDE deneyin [izlenecek yol: projeleri ve çözümleri (C++) çalışma](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

Bu izlenecek yolda gösterilen bir yazmak yerine kendi Visual C++ programını kullanabilirsiniz veya başka bir Yardım makalesi bir Visual C++ kod örneğini kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için Visual Studio ve isteğe bağlı yüklediğiniz gerekir **C++ ile masaüstü geliştirme** iş yükü veya komut satırı derleme araçları Visual Studio için.

Visual Studio tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyiciler birçok diller ve platformlar için destekleyen bir güçlü tümleşik geliştirme ortamı (IDE) ' dir. Ücretsiz Visual Studio Community sürümü dahil olmak üzere Visual Studio karşıdan yüklenip kurulacak ve C/C++ geliştirme desteği dahil etmek hakkında daha fazla bilgi için bkz. [Visual Studio'da C++ yükleme desteği](../build/vscpp-step-0-installation.md).

Visual Studio derleme araçları, yalnızca komut satırı derleyicileri, araçları ve kitaplıklarını C ve C++ programları oluşturmak için ihtiyacınız yükler. Derleme laboratuvarlarının için mükemmeldir veya sınıf sınayan ve oldukça hızlı bir şekilde yükler. Yalnızca komut satırı araçlarını yüklemek için Yükle [Visual Studio 2017 için derleme Araçları](https://go.microsoft.com/fwlink/p/?linkid=875721).

Komut satırında C veya C++ programı oluşturmadan önce araçların yüklendiğini ve bunları komut satırından erişebildiğinizi doğrulamanız gerekir. Visual C++, Araçlar, üstbilgiler ve kitaplıkları kullanır bulmak için komut satırı ortamı için karmaşık gereksinimleri vardır. **Visual C++ bir düz bir komut istemi penceresinde kullanamazsınız** bazı hazırlık yapmadan olmadan. Neyse ki, Visual C++ komut satırı derlemeleri için ayarlanan ortam sahip bir geliştirici komut istemi başlatmak, kısayol yükler. Ne yazık ki, geliştirici komut istemi kısayolları ve nerede olurlarsa olsunlar adlarını Visual C++'ın ve farklı Windows sürümleri üzerinde neredeyse her sürümde farklıdır. İlk kılavuz göreviniz kullanmak için doğru olanı buluyor.

> [!NOTE]
> Bir geliştirici komut istemi kısayolunun doğru yolları derleyici ve araçları ve tüm gerekli üst bilgileri ve kitaplıkları otomatik olarak ayarlar. Normal bir komut istemi penceresi kullanıyorsanız, bu ortam değerleri kendiniz ayarlamanız gerekir. Daha fazla bilgi için [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlamak](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Kendi oluşturmak yerine bir geliştirici komut istemi kısayolunun kullanmanızı öneririz.

### <a name="open-a-developer-command-prompt"></a>Bir geliştirici komut istemi açın

1. Windows 10'da Visual Studio 2017 yüklediyseniz, Başlat menüsünü açın ve seçin **tüm uygulamalar**. Aşağı kaydırın ve açık **Visual Studio 2017** klasörü (Visual Studio 2017 uygulama değil). Seçin **VS 2017 için geliştirici komut istemi** komut istemi penceresi açın.

   Windows 10'da Microsoft Visual C++ derleme araçları 2015 yüklü değilse, açmak **Başlat** menüsünü seçip **tüm uygulamalar**. Aşağı kaydırın ve açık **Visual C++ derleme Araçları** klasör. Seçin **Visual C++ 2015 x86 yerel Araçlar komut istemi** komut istemi penceresi açın.

   Visual Studio'nun farklı bir sürümünü kullanıyorsanız veya farklı bir Windows sürümü çalıştıran, arayın, Başlat menüsünde veya başlangıç sayfası için geliştirici komut istemi kısayolunun içeren bir Visual Studio Araçları klasörü. Windows arama işlevi, yüklü Visual Studio sürümünüzle eşleşen birini seçin ve "Geliştirici komut istemi için" arama için de kullanabilirsiniz. Komut İstemi penceresini açmak için kısayolu kullanın.

2. Ardından, Visual C++ Geliştirici komut istemi doğru şekilde ayarlandığını doğrulayın. Komut İstemi penceresinde girin `cl` ve çıkış şuna benzediğini doğrulayın:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Geçerli dizinde veya Visual C++ ve yüklü herhangi bir güncelleştirme sürümüne bağlı olarak, sürüm numaraları farklılıklar olabilir. Gördüğünüz üzere benzer ise, siz komut satırında C veya C++ programları derlemek için hazır olursunuz.

   > [!NOTE]
   > "'Temizle' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor gibi" hata alırsanız hata C1034 veya hata çalıştırdığınızda LNK1104 **cl** ya da bir geliştirici komut istemi kullanmıyorsanız, komut veya Visual C++ yüklemenizle yanlış bir şeydir. Devam etmeden önce bu sorunu düzeltmeniz gerekiyor.

   Geliştirici komut istemi kısayolunun bulamazsa ya da bir hata iletisi alırsanız, girdiğiniz zaman `cl`, sonra da Visual C++ yüklemenizin bir sorun olabilir. Visual Studio'da Visual C++ bileşeni yeniden yüklemeyi deneyin veya Microsoft Visual C++ derleme araçları yeniden yükleyin. Bu işlemin çalıştığı kadar sonraki bölüme gidin yok. Yükleme ve Visual C++ sorunlarını giderme hakkında daha fazla bilgi için bkz. [Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Sürümüne Windows bilgisayarda ve sistem güvenlik yapılandırmasına, geliştirici komut istemi kısayolunun ilişkin kısayol menüsünü açın ve ardından sağ gerekebilir **yönetici olarak çalıştır** için başarılı bir şekilde oluşturun ve bu izlenecek yolu takip ederek oluşturduğunuz programı çalıştırın.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Bir Visual C++ kaynak dosyası oluşturun ve komut satırında derleme

1. Geliştirici komut istemi penceresinde girin **md c:\hello** bir dizin oluşturun ve girmeniz **cd c:\hello** bu dizine gidin. Bu kaynak dosyanızı ve derlenmiş programın oluşturulan dizinidir.

2. Girin **not defteri hello.cpp** komut istemi penceresinde.

   Seçin **Evet** zaman not defteri ister bir dosya oluşturun. Bu, boş bir Not Defteri penceresi, hazır hello.cpp adlı bir dosya içinde kodunuzu girmeniz için açar.

3. Not Defteri'nde, aşağıdaki kod satırlarını girin:

   ```cpp
   #include <iostream>
   using namespace std;
   void main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   Bu ekranda tek satırlık metin yazın ve ardından çıkış çok basit bir programdır. Hataları en aza indirmek için bu kodu kopyalayın ve Not Defteri'ne yapıştırın.

4. Çalışmanızı kaydetmek! Not Defteri'nde, üzerinde **dosya** menüsünde seçin **Kaydet**.

   Tebrikler, bir Visual C++ kaynak dosyasını derlemek hazır olan hello.cpp oluşturdunuz.

5. Geliştirici komut istemi penceresine geçin. Girin **dir** c:\hello dizininin içeriğini listelemek için komut isteminde. Kaynak dosya hello.cpp şuna benzer dizin listesinde görmeniz gerekir:

   ```Output
   c:\hello>dir
    Volume in drive C has no label.
    Volume Serial Number is CC62-6545

    Directory of c:\hello

   05/24/2016  05:36 PM    <DIR>          .
   05/24/2016  05:36 PM    <DIR>          ..
   05/24/2016  05:37 PM               115 hello.cpp
                  1 File(s)            115 bytes
                  2 Dir(s)  571,343,446,016 bytes free

   ```

   Bilgisayarınızda tarih ve diğer ayrıntıları farklılık gösterir. Kaynak kod dosyanız görmüyorsanız hello.cpp, oluşturduğunuz c:\hello dizine değiştirdiğinizi doğrulayın ve Not Defteri'nde, kaynak dosyanız bu dizine kaydedilmiş emin olun. Ayrıca, kaynak kodu, .cpp dosya adı uzantısına sahip, .txt uzantısı kaydettiğiniz emin olun.

6. Geliştirici komut isteminde girin `cl /EHsc hello.cpp` programınızı derlemek için.

   Cl.exe derleyicisi derlenmiş kodunu içeren ve ardından bağlayıcı hello.exe adlı yürütülebilir bir program oluşturmak için çalışan bir .obj dosyası üretir. Bu ad, derleyicinin görüntülediği çıktı bilgisi satırlarında görünür. Derleyici çıktısı aşağıdakine benzer görünmelidir:

   ```Output
   c:\hello>cl /EHsc hello.cpp
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   hello.cpp
   Microsoft (R) Incremental Linker Version 14.10.25017.0
   Copyright (C) Microsoft Corporation.  All rights reserved.

   /out:hello.exe
   hello.obj
   ```

   > [!NOTE]
   > "'Temizle' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor gibi" hata alırsanız hata C1034 veya hatası LNK1104, geliştirici komut istemi, doğru şekilde ayarlanmamış. Bu sorunun çözümü hakkında daha fazla bilgi için geri dön **bir geliştirici komut istemi açın** bölümü.

   > [!NOTE]
   > Farklı bir derleyici veya bağlayıcı hata veya uyarı alırsanız, hataları düzeltin, ardından dosyayı kaydedin ve derleyici yeniden çalıştırmak için kaynak kodu gözden geçirin. Belirli hatalar hakkında daha fazla bilgi için hata numarası aramak için bu MSDN sayfasında arama kutusunu kullanın.

7. Komut isteminde hello.exe programı çalıştırmak için girin `hello`.

   Program bu metni görüntüler ve çıkar:

   ```Output
   Hello, world, from Visual C++!
   ```

   Tebrikler, yalnızca derlenmiş ve komut satırı araçlarını kullanarak bir C++ programını çalıştırın.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Hello, World" örnek C++ programını alabilirsiniz olarak yaklaşık kadar kolaydır. Gerçek dünya programlarının üst bilgi dosyaları ve daha fazla kaynak dosyaları, bağlantı kitaplıklarında ve yararlı işi vardır.

Gösterilen örnek kod yazmak yerine, kendi C++ kodunuzu derlemek için bu izlenecek yolda adımları kullanabilirsiniz. Ayrıca, başka bir yerde bulabileceğiniz birçok C++ kodu örnek programını da oluşturabilirsiniz. Kaynak kodunuzu yerleştirin ve uygulamalarınızda herhangi bir yazılabilir dizini oluşturun. Varsayılan olarak, Visual Studio IDE, Belgeler klasöründe bir Visual Studio klasörün Visual Studio sürümünüz için bir proje alt projeler oluşturur.

Birden çok kaynak kodu dosyaları olan bir program derlemek için bu gibi komut satırında tüm girin:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

**/Ehsc** C++ özel durum işlemeyi etkinleştirme derleyici komut satırı seçeneği bildirir. Daha fazla bilgi için [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md).

Bu gibi birden çok kaynak dosyaları sağladığında, derleyici ilk giriş dosyasının program adı oluşturmak için kullanır. Bu durumda, file1.exe adlı bir programı çıkarır. Ekleme için program1.exe adını değiştirmek için bir [/out](../build/reference/out-output-file-name.md) bağlayıcı seçeneği:

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Daha fazla programlama hatalarını otomatik olarak çekmek için derleme kullanarak öneririz [/W3](../build/reference/compiler-option-warning-level.md) veya [/W4](../build/reference/compiler-option-warning-level.md) Uyarısı Düzeyi:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Derleyici, cl.exe'yi uygulama oluşturmak için en iyi duruma getirme, hata ayıklama ve kod çözümleme kullanabileceğiniz pek çok seçenek vardır. Hızlı bir listesi için girin **cl /?** Geliştirici komut istemi. Ayrıca derlemek ve da ayrı ayrı bağlayın ve derleme daha karmaşık senaryolarda bağlayıcı seçenekleri uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanım hakkında daha fazla bilgi için bkz. [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

NMAKE ve derleme görevleri dosyası ve MSBuild ve proje dosyaları, yapılandırmak ve komut satırında daha karmaşık projeleri oluşturmak için kullanabilirsiniz. Bu araçları kullanarak daha fazla bilgi için bkz: [NMAKE başvurusu](../build/nmake-reference.md) ve [MSBuild](../build/msbuild-visual-cpp.md).

C ve C++ dillerinin benzerdir ancak aynı değildir. Visual C++ derleyicisi, kodunuzu derleyen sırasında kullanmak için hangi dilin belirlemek için basit bir kuralı kullanır. Varsayılan olarak, Visual C++ derleyicisi, .c C kaynak kodu biten tüm dosyaları ve C++ kaynak kodu, .cpp ile biten tüm dosyaları işler. Dosya adı uzantısına bakmaksızın tüm dosyaları C++ değerlendirilecek zorlamak için kullanan [/TC](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneği.

Visual C++ Derleyici ISO C99 standardı ile uyumludur, ancak tamamen uyumlu bir C çalışma zamanı kitaplığı (CRT) içerir. Çoğu durumda, taşınabilir kod derlemek ve beklendiği gibi çalıştırın. Visual C++ bazı CRT değişiklikler ISO C11 desteklemez. Belirli bir kitaplığı işlevleri ve POSIX işlev adlarını Visual C++ derleyicisi tarafından kullanım dışı bırakılmıştır. İşlevler desteklenir, ancak tercih edilen adlar değişmiştir. Daha fazla bilgi için [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) ve [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>
[Derleyici Seçenekleri](../build/reference/compiler-options.md)
