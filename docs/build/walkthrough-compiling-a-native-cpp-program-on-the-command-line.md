---
title: 'İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme'
description: Bir komut isteminden C++ Microsoft derleyicisini kullanın.
ms.custom: conceptual
ms.date: 04/23/2019
helpviewer_keywords:
- native code [C++]
- Visual C++, native code
- compiling programs [C++]
- command-line applications [C++], native
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
ms.openlocfilehash: d002fd4c4edc99775e62023dda7998fba2c6a44f
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518184"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme

Visual Studio, uygulamaları, masaüstü uygulamaları C++ , aygıt sürücülerini ve .net bileşenlerini Evrensel Windows platformu temel konsol uygulamalarından her şeyi oluşturmak için kullanabileceğiniz bir komut satırı derleyicisi içerir.

Bu kılavuzda, bir metin düzenleyicisi kullanarak temel, "Merhaba, Dünya" stili C++ bir program oluşturur ve ardından bunu komut satırında derleyebilirsiniz. Komut satırını kullanmak yerine Visual Studio IDE 'yi denemek istiyorsanız, bkz. [izlenecek yol: projeler ve çözümlerle çalışma (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [masaüstü geliştirme için C++ Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

Bu kılavuzda, gösterilen birini yazmak yerine kendi görsel C++ programınızı kullanabilir ya da başka bir yardım makalesindeki görsel C++ kod örneğini kullanabilirsiniz.

## <a name="prerequisites"></a>Prerequisites

Bu yönergeyi tamamlamak için, Visual Studio 'yu ve iş yüküyle isteğe bağlı **Masaüstü geliştirmeyi C++**  ya da Visual Studio için komut satırı derleme araçlarını yüklemiş olmanız gerekir.

Visual Studio, birçok dil ve platformda tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyiciler destekleyen güçlü bir tümleşik geliştirme ortamıdır (IDE). Visual Studio 'yu indirme ve yükleme hakkında daha fazla bilgi için, ücretsiz Visual Studio Community Edition ve C/C++ geliştirmeye yönelik destek dahil olmak üzere, bkz. [Visual C++ Studio 'da destek yükleme](vscpp-step-0-installation.md).

Visual Studio için derleme araçları, yalnızca C ve C++ programları derlemek için gereken komut satırı derleyicilerini, araçları ve kitaplıkları kurar. Derleme laboratuvarları veya sınıf alıştırmaları için idealdir ve görece hızlı bir şekilde yüklenir. Yalnızca komut satırı araçlarını yüklemek için [Visual Studio İndirmeleri](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) sayfasında Visual Studio Için derleme araçları ' nı arayın.

Komut satırında bir C veya C++ program oluşturabilmeniz için önce araçların yüklendiğini ve bunlara komut satırından erişebildiğinizi doğrulamanız gerekir. Görsel C++ , komut satırı ortamının kullandığı araçları, üstbilgileri ve kitaplıkları bulması için karmaşık gereksinimlere sahiptir. **Bir hazırlık yapmadan, C++ görseli düz bir komut istemi penceresinde kullanamazsınız** . Neyse ki, C++ görsel, komut satırı yapıları için ayarlanmış ortamı olan bir geliştirici komut istemi başlatmanıza yönelik kısayolları yüklüyor. Ne yazık ki, geliştirici komut istemi kısayollarının ve bulundukları yer adları, neredeyse her görsel C++ sürümü ve farklı Windows sürümlerinde farklıdır. İlk adım adım göreviniz, kullanmak için doğru olanı buluyor.

> [!NOTE]
> Geliştirici komut istemi kısayolu, derleyici ve araçlar için doğru yolları otomatik olarak ayarlar ve tüm gerekli üst bilgiler ve kitaplıklar için. Normal bir **komut istemi** penceresi kullanıyorsanız, bu ortam değerlerini kendiniz ayarlamanız gerekir. Daha fazla bilgi için bkz. [komut satırı derlemeleri Için yolu ve ortam değişkenlerini ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md). Kendi kendinize oluşturmak yerine Geliştirici komut istemi kısayolunu kullanmanızı öneririz.

### <a name="open-a-developer-command-prompt"></a>Geliştirici komut istemi açın

1. Windows 10 ' da Visual Studio 2017 veya üstünü yüklediyseniz, Başlat menüsünü açın ve **tüm uygulamalar**' ı seçin. Aşağı kaydırın ve **Visual Studio** klasörünü açın (Visual Studio uygulaması değil). **Vs için** , komut istemi penceresini açmak üzere Geliştirici komut istemi seçin.

   Windows 10 ' da Microsoft Visual C++ derleme araçları 2015 ' ü yüklediyseniz, **Başlat** menüsünü açın ve **tüm uygulamalar**' ı seçin. Aşağı kaydırın ve  **C++ Visual derleme araçları** klasörünü açın. Komut istemi penceresini açmak için  **C++ Visual 2015 x86 yerel araçları komut istemi** seçin.

   Windows Search işlevini "Geliştirici komut istemi" ni aramak ve yüklü Visual Studio sürümünüz ile eşleşen bir seçim yapmak için de kullanabilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

1. Ardından, Visual C++ Developer komut isteminin doğru şekilde ayarlandığını doğrulayın. Komut istemi penceresinde `cl` girin ve çıktının şuna benzer göründüğünü doğrulayın:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Geçerli dizin veya sürüm numaralarında, görsel C++ sürümüne ve yüklü güncelleştirmelerden bağlı olarak farklılıklar olabilir. Yukarıdaki çıkış, gördüklerinize benzer ise, komut satırında C veya C++ programları oluşturmaya hazırsınız demektir.

   > [!NOTE]
   > "' CL" gibi bir hata alırsanız bir iç veya dış komut, çalıştırılabilir program veya toplu iş dosyası, "hata C1034 veya hata LNK1104" **CL** komutunu çalıştırdığınızda bir geliştirici komut istemi kullanmıyorsanız ya da görsel C++yüklemenizde bir sorun oluştu. Devam edebilmeniz için bu sorunu çözmeniz gerekir.

   Geliştirici komut istemi kısayolunu bulamazsanız veya `cl`girdiğinizde bir hata iletisi alırsanız, görsel C++ yüklemenizin bir sorunu olabilir. Visual Studio 'da görsel C++ bileşeni yeniden yüklemeyi deneyin veya Microsoft Visual C++ derleme araçları 'nı yeniden yükleyin. Bu işe ana kadar bir sonraki bölüme geçmeyin. Görsel C++yükleme ve sorun giderme hakkında daha fazla bilgi için bkz. [Visual Studio 'yu yükleme](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Bilgisayardaki Windows sürümüne ve sistem güvenlik yapılandırmasına bağlı olarak, geliştirici komut istemi kısayolunun kısayol menüsünü açmak için sağ tıklayıp **yönetici olarak çalıştır** ' ı seçerek bu yönergeyi izleyerek oluşturduğunuz programı başarıyla oluşturup çalıştırın.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Görsel C++ kaynak dosyası oluşturma ve komut satırında derleme

1. Geliştirici komut istemi penceresinde bir dizin oluşturmak için `md c:\hello` girin ve ardından bu dizine değiştirmek için `cd c:\hello` girin. Bu dizin, kaynak dosyanızın ve derlenmiş programın içinde oluşturulduğu yerdir.

1. Komut istemi penceresine `notepad hello.cpp` girin.

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

   Tebrikler, derleme için hazırlamış C++ olan Hello. cpp kaynak dosyasını oluşturdunuz.

1. Geliştirici komut istemi penceresine geri dönün. C:\Hello dizininin içeriğini listelemek için komut istemine `dir` yazın. Dizin listesinde Hello. cpp kaynak dosyasını görmeniz gerekir, bu durum şöyle görünür:

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

   Tarihler ve diğer ayrıntılar bilgisayarınızda farklı olacaktır. Kaynak kodu dosyanızı (Hello. cpp) görmüyorsanız, oluşturduğunuz c:\Hello dizinine değiştirdiğinizden emin olun ve Not defteri 'nde kaynak dosyanızı bu dizine kaydettiğinizden emin olun. Ayrıca, kaynak kodunu. txt uzantısıyla değil,. cpp dosya adı uzantısıyla kaydettiğinizden emin olun.

1. Geliştirici komut isteminde, programınızı derlemek için `cl /EHsc hello.cpp` girin.

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

1. Hello. exe programını çalıştırmak için komut isteminde `hello`girin.

   Program bu metni görüntüler ve çıkar:

   ```Output
   Hello, world, from Visual C++!
   ```

   Tebrikler, komut satırı araçlarını kullanarak bir C++ programı derlediniz ve çalıştırdık.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Hello, World" örneği, bir program tarafından alabileceğiniz kadar C++ basit bir işlemdir. Gerçek dünyada programlar üst bilgi dosyalarına ve daha fazla kaynak dosyasına sahiptir, kitaplıklarda bağlantı sağlar ve yararlı işler yapılır.

Gösterilen örnek kodu yazmak yerine kendi C++ kodunuzu oluşturmak için bu yönergedeki adımları kullanabilirsiniz. Ayrıca, başka bir yerde C++ bulduğunuz birçok kod örnek programı da oluşturabilirsiniz. Kaynak kodunuzu yerleştirebilir ve uygulamalarınızı herhangi bir yazılabilir dizine oluşturabilirsiniz. Varsayılan olarak, Visual Studio IDE, Visual Studio sürümünüz için adlı bir Visual Studio klasörünün projeler alt klasöründeki Belgeler klasörünüzde projeler oluşturur.

Ek kaynak kodu dosyaları olan bir programı derlemek için, bunları komut satırına şu şekilde girin:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` komut satırı seçeneği derleyiciye özel durum işlemeyi etkinleştirmesini C++ söyler. Daha fazla bilgi için bkz. [/Eh (özel durum Işleme modeli)](reference/eh-exception-handling-model.md).

Ek kaynak dosyaları sağlarsanız, derleyici program adını oluşturmak için ilk giriş dosyasını kullanır. Bu durumda, FILE1. exe adlı bir program çıkışı verir. Adı Program1. exe olarak değiştirmek için, bir [/Out](reference/out-output-file-name.md) bağlayıcı seçeneği ekleyin:

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Otomatik olarak daha fazla programlama hatası yakalamak için [/w3](reference/compiler-option-warning-level.md) veya [/W4](reference/compiler-option-warning-level.md) uyarı düzeyi seçeneğini kullanarak derlemeyi öneririz:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

, CL. exe ' nin, kodunuzu derlemek, iyileştirmek, hatalarını ayıklamak ve analiz etmek için uygulayabileceğiniz birçok daha fazla seçeneği vardır. Hızlı bir liste için, geliştirici komut isteminde `cl /?` girin. Ayrıca, ayrı olarak derleyip bağlayabilir ve bağlayıcı seçeneklerini daha karmaşık derleme senaryolarında uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanımı hakkında daha fazla bilgi için bkz. [CC++ /Building Reference](reference/c-cpp-building-reference.md).

Komut satırında daha karmaşık projeler yapılandırmak ve derlemek için NMAKE ve makefiles, MSBuild ve proje dosyalarını kullanabilirsiniz. Bu araçları kullanma hakkında daha fazla bilgi için bkz. [NMAKE Başvurusu](reference/nmake-reference.md) ve [MSBuild](msbuild-visual-cpp.md).

C ve C++ diller benzerdir, ancak aynı değildir. MSVC derleyicisi, kodunuzu derlediğinde hangi dilin kullanılacağını belirleyen basit bir kural kullanır. Varsayılan olarak, MSVC derleyicisi. c ile biten tüm dosyaları C kaynak kodu olarak ve. cpp ile biten tüm dosyaları kaynak kodu olarak C++ değerlendirir. Derleyicinin tüm dosyaları dosya adı uzantısına bağımlı olmayan olarak C++ görmesini zorlamak için [/TP](reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneğini kullanın.

MSVC derleyicisi, ISO C99 standardı ile uyumlu ancak kesinlikle uyumlu olmayan bir C çalışma zamanı kitaplığı (CRT) içerir. Çoğu durumda, taşınabilir kod, beklendiği gibi derleyip çalıştırılır. Visual C++ , ISO C11 içindeki CRT değişikliklerinden bazılarını desteklemez. Belirli kitaplık işlevleri ve POSIX işlev adları MSVC derleyicisi tarafından kullanım dışıdır. İşlevler desteklenir, ancak tercih edilen adlar değişmiştir. Daha fazla bilgi için bkz. CRT ve derleyici uyarısında [güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) [(düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
