---
title: 'İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme'
description: Bir komut isteminden Microsoft C++ derleyicisini kullanın.
ms.custom: conceptual
ms.date: 04/02/2020
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: c24fdfdaef612059d5c2fbaaa58f10d83f5fe3a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335240"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme

Visual Studio, bir komut satırı C ve C++ derleyicisi içerir. Bu uygulamayı, temel konsol uygulamalarından Evrensel Windows Platformu uygulamalar, masaüstü uygulamaları, cihaz sürücüleri ve .NET bileşenlerine yönelik her şeyi oluşturmak için kullanabilirsiniz.

Bu kılavuzda, bir metin düzenleyicisi kullanarak temel, "Merhaba, Dünya" stili C++ programı oluşturursunuz ve ardından bunu komut satırında derleyebilirsiniz. Komut satırını kullanmak yerine Visual Studio IDE 'yi denemek istiyorsanız, bkz. [Izlenecek yol: projeler ve çözümlerle çalışma (c++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ masaüstü geliştirme IÇIN Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

Bu kılavuzda, gösterilen birini yazmak yerine kendi C++ programınızı kullanabilirsiniz. Ya da başka bir yardım makalesindeki C++ kod örneğini kullanabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Bu yönergeyi tamamlamak için, Visual Studio 'Yu ve C++ iş yükünde isteğe bağlı **Masaüstü geliştirmeyi** ya da Visual Studio için komut satırı derleme araçlarını yüklemiş olmanız gerekir.

Visual Studio, *Tümleşik bir geliştirme ortamıdır* (IDE). Birçok dil ve platform için tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyicileri destekler. Kullanılabilir sürümlerde ücretsiz Visual Studio Community Edition bulunur ve hepsi C ve C++ geliştirmeyi destekleyebilir. Visual Studio 'Yu indirme ve yükleme hakkında daha fazla bilgi için bkz. [Visual Studio 'Da C++ desteğini yükleme](vscpp-step-0-installation.md).

Visual Studio için derleme araçları, yalnızca C ve C++ programları derlemek için ihtiyacınız olan komut satırı derleyicilerini, araçları ve kitaplıkları kurar. Derleme laboratuvarları veya sınıf alıştırmaları için idealdir ve görece hızlı bir şekilde yüklenir. Yalnızca komut satırı araçlarını yüklemek için [Visual Studio İndirmeleri](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) sayfasında Visual Studio Için derleme araçları ' nı arayın.

Komut satırında bir C veya C++ programı oluşturabilmeniz için önce araçların yüklü olduğunu doğrulayın ve komut satırından bunlara erişebilirsiniz. Visual C++, komut satırı ortamının kullandığı araçları, üstbilgileri ve kitaplıkları bulması için karmaşık gereksinimlere sahiptir. **Visual C++, bazı hazırlıklar yapmadan düz bir komut istemi penceresinde kullanamazsınız** . Neyse ki Visual C++, komut satırı yapıları için ayarlanmış ortamı olan bir geliştirici komut istemi başlatmanız için kısayollar yüklüyor. Ne yazık ki, geliştirici komut istemi kısayollarının ve nerede bulundukları yerlerde, Visual C++ neredeyse her sürümü ve farklı Windows sürümlerinde farklılık vardır. İlk adım adım göreviniz, kullanmak için doğru olanı buluyor.

> [!NOTE]
> Geliştirici komut istemi kısayolu, derleyici ve araçlar için doğru yolları otomatik olarak ayarlar ve tüm gerekli üst bilgiler ve kitaplıklar için. Normal bir **komut istemi** penceresi kullanıyorsanız, bu ortam değerlerini kendiniz ayarlamanız gerekir. Daha fazla bilgi için bkz. [komut satırı derlemeleri Için yolu ve ortam değişkenlerini ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md). Kendi kendinize oluşturmak yerine Geliştirici komut istemi kısayolunu kullanmanızı öneririz.

### <a name="open-a-developer-command-prompt"></a>Geliştirici komut istemi açın

1. Windows 10 ' da Visual Studio 2017 veya üstünü yüklediyseniz, Başlat menüsünü açın ve **tüm uygulamalar**' ı seçin. Aşağı kaydırın ve **Visual Studio** klasörünü açın (Visual Studio uygulaması değil). **Vs için** , komut istemi penceresini açmak üzere Geliştirici komut istemi seçin.

   Windows 10 ' da Microsoft Visual C++ derleme araçları 2015 ' i yüklediyseniz, **Başlat** menüsünü açın ve **tüm uygulamalar**' ı seçin. Aşağı kaydırın ve **Visual C++ derleme araçları** klasörünü açın. Komut istemi penceresini açmak için **Visual C++ 2015 x86 yerel araçları komut istemi** seçin.

   Windows Search işlevini "Geliştirici komut istemi" ni aramak ve yüklü Visual Studio sürümünüz ile eşleşen bir seçim yapmak için de kullanabilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

1. Sonra, Visual C++ Geliştirici komut isteminin doğru şekilde ayarlandığını doğrulayın. Komut istemi penceresinde, yazın `cl` ve çıktının şuna benzer göründüğünü doğrulayın:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Geçerli dizin veya sürüm numaralarında farklılıklar olabilir. Bu değerler, Visual C++ sürümüne ve yüklü tüm güncelleştirmelere bağlıdır. Yukarıdaki çıkış, gördüklerinize benziyorsa, komut satırında C veya C++ programları oluşturmaya hazırsınız demektir.

   > [!NOTE]
   > "' CL ' gibi bir hata alırsanız, bir iç veya dış komut, çalıştırılabilir program veya toplu iş dosyası," hata C1034 veya hata LNK1104 " **`cl`** komutu çalıştırdığınızda, bir geliştirici komut istemi kullanmıyorsanız veya Visual C++ yüklemenizde bir sorun oluştu. Devam edebilmeniz için bu sorunu çözmeniz gerekir.

   Geliştirici komut istemi kısayolunu bulamazsanız veya girdiğinizde `cl`bir hata iletisi alırsanız Visual C++ yüklemenizin bir sorunu olabilir. Visual C++ bileşenini Visual Studio 'da yeniden yüklemeyi deneyin veya Microsoft Visual C++ derleme araçlarını yeniden yükleyin. **`cl`** Komut çalışana kadar bir sonraki bölüme gitmeyin. Visual C++ yükleme ve sorun giderme hakkında daha fazla bilgi için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Bilgisayardaki Windows sürümüne ve sistem güvenlik yapılandırmasına bağlı olarak, geliştirici komut istemi kısayolunun kısayol menüsünü açmak için sağ tıklayıp **yönetici olarak çalıştır** ' ı seçerek bu yönergeyi izleyerek oluşturduğunuz programı başarıyla oluşturup çalıştırın.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Bir Visual C++ kaynak dosyası oluşturun ve komut satırında derleyin

1. Geliştirici komut istemi penceresinde bir dizin oluşturmak için `md c:\hello` girin ve ardından bu dizine geçmek için girin `cd c:\hello` . Bu dizin, kaynak dosyanızın ve derlenmiş programın içinde oluşturulduğu yerdir.

1. Komut `notepad hello.cpp` istemi penceresine girin.

   Not defteri bir dosya oluşturmanızı isterse, **Evet** ' i seçin. Bu adım, kodunuzu Hello. cpp adlı bir dosyaya girmenize yönelik boş bir not defteri penceresi açar.

1. Not defteri 'nde aşağıdaki kod satırlarını girin:

   ```cpp
   #include <iostream>
   using namespace std;
   int main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   Bu kod, ekranda bir metin satırı yazacak ve sonra çıkış yapılacak basit bir programdır. Hataları en aza indirmek için, bu kodu kopyalayın ve Not defteri 'ne yapıştırın.

1. Çalışmanızı kaydedin! Not defteri 'nde **Dosya** menüsünde **Kaydet**' i seçin.

   Tebrikler, derleme için hazırlamış olan bir C++ kaynak dosyası (Hello. cpp) oluşturdunuz.

1. Geliştirici komut istemi penceresine geri dönün. C:\Hello dizininin içeriğini listelemek için komut istemine yazın `dir` . Dizin listesinde Hello. cpp kaynak dosyasını görmeniz gerekir, bu durum şöyle görünür:

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

   Tarihler ve diğer ayrıntılar bilgisayarınızda farklı olacaktır. Kaynak kodu dosyanızı ( *Hello. cpp*) görmüyorsanız, oluşturduğunuz *\\c: Merhaba* dizinine değiştirdiğinizden emin olun. Not defteri 'nde, kaynak dosyanızı bu dizine kaydettiğinizden emin olun. Ayrıca, kaynak kodunu *`.cpp`* *`.txt`* uzantı değil, bir dosya adı uzantısıyla kaydettiğinizden emin olun.

1. Geliştirici komut isteminde, programınızı derlemek için `cl /EHsc hello.cpp` yazın.

   CL. exe derleyicisi, derlenen kodu içeren bir. obj dosyası oluşturur ve ardından, Hello. exe adlı bir yürütülebilir program oluşturmak için bağlayıcıyı çalıştırır. Bu ad, derleyicinin görüntülediği çıkış bilgileri satırlarında görüntülenir. Derleyicinin çıkışı aşağıdakine benzer görünmelidir:

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
   > "' CL" iç veya dış komut, çalıştırılabilir programı veya toplu iş dosyası, "hata C1034 veya hata LNK1104" gibi bir hata alırsanız, geliştirici komut isteminize doğru şekilde ayarlanmamaktadır. Bu sorunu giderme hakkında daha fazla bilgi için, **Geliştirici komut istemi** bölümüne geri dönün.

   > [!NOTE]
   > Farklı bir derleyici veya bağlayıcı hatası ya da uyarısı alırsanız, hataları düzeltmek için kaynak kodunuzu gözden geçirin, sonra dosyayı kaydedin ve derleyiciyi yeniden çalıştırın. Belirli hatalar hakkında daha fazla bilgi için bu MSDN sayfasındaki arama kutusunu kullanarak hata numarasını arayın.

1. Hello. exe programını çalıştırmak için komut isteminde yazın `hello`.

   Program bu metni görüntüler ve çıkar:

   ```Output
   Hello, world, from Visual C++!
   ```

   Tebrikler, komut satırı araçlarını kullanarak bir C++ programını derlediniz ve çalıştırdık.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Hello, World" örneği, C++ programının alabilir kadar basit bir işlemdir. Gerçek dünyada programlar genellikle başlık dosyalarına, daha fazla kaynak dosyasına ve kitaplıklara bağlantı sağlar.

Gösterilen örnek kodu yazmak yerine kendi C++ kodunuzu oluşturmak için bu yönergedeki adımları kullanabilirsiniz. Bu adımlar, başka bir yerde bulduğunuz birçok C++ kod örnek programı oluşturmanıza da imkan tanır. Kaynak kodunuzu yerleştirebilir ve uygulamalarınızı herhangi bir yazılabilir dizine oluşturabilirsiniz. Varsayılan olarak, Visual Studio IDE, bir *kaynak\\deposu* alt klasöründe, Kullanıcı klasörünüzde projeler oluşturur. Daha eski sürümler, projeleri bir *belgeler\\Visual \<Studio sürüm>\\ *projeleri * klasörüne yerleştirebilir.

Ek kaynak kodu dosyaları olan bir programı derlemek için, bunları komut satırına şu şekilde girin:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` Komut satırı seçeneği derleyiciye standart C++ özel durum işleme davranışını etkinleştirmesini söyler. Bu olmadan, oluşturulan özel durumlar, yok etme nesnelerinin ve kaynak sızıntılarına neden olabilir. Daha fazla bilgi için bkz. [/Eh (özel durum Işleme modeli)](reference/eh-exception-handling-model.md).

Ek kaynak dosyaları sağlarsanız, derleyici program adını oluşturmak için ilk giriş dosyasını kullanır. Bu durumda, FILE1. exe adlı bir program çıkışı verir. Adı Program1. exe olarak değiştirmek için, bir [/Out](reference/out-output-file-name.md) bağlayıcı seçeneği ekleyin:

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Otomatik olarak daha fazla programlama hatası yakalamak için [/w3](reference/compiler-option-warning-level.md) veya [/W4](reference/compiler-option-warning-level.md) uyarı düzeyi seçeneğini kullanarak derlemeyi öneririz:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

, CL. exe ' nin birçok daha fazla seçeneği vardır. Kodunuzu derlemek, iyileştirmek, hatalarını ayıklamak ve analiz etmek için uygulayabilirsiniz. Hızlı bir liste için, Geliştirici `cl /?` komut istemine yazın. Ayrıca, ayrı olarak derleyip bağlayabilir ve bağlayıcı seçeneklerini daha karmaşık derleme senaryolarında uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanımı hakkında daha fazla bilgi için bkz. [C/C++ oluşturma başvurusu](reference/c-cpp-building-reference.md).

Komut satırında daha karmaşık projeler yapılandırmak ve derlemek için NMAKE ve makefiles, MSBuild ve proje dosyaları ya da CMake kullanabilirsiniz. Bu araçları kullanma hakkında daha fazla bilgi için bkz. Visual Studio 'da [NMAKE Başvurusu](reference/nmake-reference.md), [MSBuild](msbuild-visual-cpp.md)ve [CMake projeleri](cmake-projects-in-visual-studio.md).

C ve C++ dilleri benzerdir, ancak aynı değildir. MSVC derleyicisi, kodunuzu derlediğinde hangi dilin kullanılacağını belirleyen basit bir kural kullanır. Varsayılan olarak, MSVC derleyicisi, C kaynak kodu *`.c`* olarak biten dosyaları ve C++ kaynak kodu *`.cpp`* olarak biten dosyaları değerlendirir. Derleyicinin dosya adı uzantısından bağımsız olarak tüm dosyaları kabul etmeye zorlamak için [/TP](reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneğini kullanın.

MSVC derleyicisi, küçük özel durumlarla ISO C99 standardına uyan bir C çalışma zamanı kitaplığı (CRT) içerir. Taşınabilir kod genellikle, beklenen şekilde derlenir ve çalışır. Bazı eski kitaplık işlevleri ve birkaç POSIX işlev adı, MSVC derleyicisi tarafından kullanım dışıdır. İşlevler desteklenir, ancak tercih edilen adlar değişmiştir. Daha fazla bilgi için bkz. CRT ve derleyici uyarısında [güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) [(düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
