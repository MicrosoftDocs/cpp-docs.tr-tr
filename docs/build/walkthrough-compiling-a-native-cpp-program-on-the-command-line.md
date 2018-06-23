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
ms.openlocfilehash: eb0d7aab8000febdf07288370da058f437767387
ms.sourcegitcommit: e013acba70aa29fed60ae7945162adee23e19c3b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36322439"
---
# <a name="walkthrough-compiling-a-native-c-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme

Visual C++ her şeyi temel konsol uygulamaları Evrensel Windows platformu uygulamaları, Masaüstü uygulamaları, aygıt sürücülerini ve .NET bileşenlerini oluşturmak için kullanabileceğiniz bir komut satırı C++ Derleyici içerir.

Bu kılavuzda, "Hello, World" basic oluşturma-C++ programı bir metin kullanarak Düzenleyicisi stil ve komut satırında derleme. İsterseniz bkz komut satırını kullanarak yerine Visual Studio IDE deneyin [izlenecek yol: projeler ve çözümler (C++) ile çalışma](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

Bu kılavuzda gösterilen bir yazmak yerine, kendi Visual C++ programı kullanabilirsiniz veya başka bir Yardım makalesinin Visual C++ kodu örnekten kullanabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için Visual Studio ve isteğe bağlı yüklemiş olmalısınız **C++ ile masaüstü geliştirme** iş yükü veya komut satırı derleme araçlarını Visual Studio için.

Visual Studio destekleyen tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyicileri birçok diller ve platformlar için güçlü bir tümleşik geliştirme ortamı (IDE) ' dir. Ücretsiz Visual Studio Community sürümü de dahil olmak üzere Visual Studio karşıdan yükleyip ve C/C++ geliştirme desteği dahil etmek hakkında daha fazla bilgi için bkz: [Visual Studio yükleme C++ Destek](../build/vscpp-step-0-installation.md).

Derleme araçları Visual Studio için yalnızca komut satırı derleyicileri, Araçlar ve C ve C++ programları oluşturmak için gereken kitaplıklar yükler. Yapı Laboratuvarları için mükemmeldir veya sınıf kullanır ve oldukça hızlı bir şekilde yükler. Yalnızca komut satırı araçlarını yüklemek için indirme [derleme araçları Visual Studio 2017 için](https://go.microsoft.com/fwlink/p/?linkid=875721).

Komut satırında C veya C++ programı oluşturmadan önce Araçları yüklenir ve bunları komut satırından erişebildiğinizi doğrulamanız gerekir. Visual C++ Araçları, üst bilgilerinin ve kitaplıklarının kullandığı bulmak için komut satırı ortamı için karmaşık gereksinimleri vardır. **Visual C++ düz komut istemi penceresinde kullanamazsınız** bazı hazırlık yaparken olmadan. Neyse ki, Visual C++, komut satırı derlemeleri için ayarlanan ortam sahip bir geliştirici komut istemi başlatmak kısayol yükler. Ne yazık ki, geliştirici komut istemi kısayolları ve nerede olurlarsa olsunlar adları neredeyse her sürümü Visual C++ ve farklı Windows sürümleri üzerinde farklı. İlk kılavuz göreviniz kullanmak için doğru olanı bulma.

> [!NOTE]
> Bir geliştirici komut istemi kısayoluna doğru yol ve tüm gerekli üst bilgilerinin ve kitaplıklarının derleyici ve araçları için otomatik olarak ayarlar. Normal bir komut istemi penceresi kullanıyorsanız bu ortam değerleri kendiniz ayarlamalısınız. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Kendi planınızı yerine bir geliştirici komut istemi kısayoluna kullanmanızı öneririz.

### <a name="open-a-developer-command-prompt"></a>Bir geliştirici komut istemi açın

1. Visual Studio 2017 üzerinde Windows 10 yüklü değilse Başlat menüsünü açın ve seçin **tüm uygulamalar**. Açık ve aşağı kaydırma **Visual Studio 2017** klasörü (Visual Studio 2017 uygulama değil). Seçin **VS 2017 için geliştirici komut istemi** komut istemi penceresi açın.

   Microsoft Visual C++ derleme araçları 2015 üzerinde Windows 10 yüklü değilse, açmak **Başlat** menü ve **tüm uygulamalar**. Açık ve aşağı kaydırma **Visual C++ derleme Araçları** klasör. Seçin **Visual C++ 2015 x86 yerel Araçları Komut İstemi** komut istemi penceresi açın.

   Visual Studio farklı bir sürümünü kullanıyorsanız veya farklı bir Windows sürümü çalıştıran, başlangıç sayfası için geliştirici komut istemi kısayolunu içeren bir Visual Studio Araçları klasörü veya Başlat menüde arayın. "Geliştirici komut istemi" araması yapın ve yüklü Visual Studio sürümünüzle eşleşen birini seçmek için Windows Arama işlevini de kullanabilirsiniz. Komut İstemi penceresi açmak için kısayolu kullanın.

2. Ardından, Visual C++ Geliştirici komut istemi doğru ayarlandığını doğrulayın. Komut İstemi penceresinde girin `cl` ve çıktı şuna benzediğini doğrulayın:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Geçerli dizinde veya Visual C++ ve yüklü herhangi bir güncelleştirme sürümüne bağlı olarak sürüm numaralarını farklılıklar olabilir. Ardından, görmek için benzer ise, komut satırında C veya C++ programları oluşturmak hazırsınız demektir.

   > [!NOTE]
   > "'Cl' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor"gibi bir hata alırsanız hatası C1034 ya da hatası çalıştırdığınızda LNK1104 **cl** ya da bir geliştirici komut istemi kullanmıyorsanız, komut veya Visual C++ yüklemenizle yanlış bir şeydir. Devam etmeden önce bu sorunu düzeltmeniz gerekir.

   Geliştirici komut istemi kısayoluna bulamazsa ya da bunu girdiğinizde bir hata iletisi alırsanız `cl`, sonra da Visual C++ yüklemenizin bir sorun olabilir. Visual Studio Visual C++ bileşeni yeniden yüklemeyi deneyin veya Microsoft Visual C++ derleme araçları yeniden yükleyin. Bu çalışır kadar sonraki bölüme gidin yok. Yükleme ve Visual C++ sorunlarını giderme hakkında daha fazla bilgi için bkz: [Visual Studio yükleme](/visualstudio/install/install-visual-studio).

   > [!NOTE]
   > Windows sürümü bağlı olarak bilgisayarda ve sistem güvenlik yapılandırması, geliştirici komut istemi kısayoluna için kısayol menüsünü açın ve ardından sağ gerekebilir **yönetici olarak çalıştır** için başarılı bir şekilde oluşturmak ve bu kılavuzu izleyerek oluşturun programını çalıştırın.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C++ kaynak dosyası oluşturma ve komut satırında derleme

1. Geliştirici komut istemi penceresinde girin **md c:\hello** bir dizin oluşturun ve ardından girin **cd c:\hello** bu dizine gidin. Bu kaynak dosyanızı ve derlenmiş program oluşturulan dizindir.

2. Girin **not defteri hello.cpp** komut istemi penceresinde.

   Seçin **Evet** zaman Notepad ister bir dosya oluşturun. Boş bir Not Defteri penceresi, hazır hello.cpp adındaki bir dosyada kodunuzu girmeniz için açılır.

3. Not Defteri'nde, aşağıdaki kod satırlarını girin:

   ```cpp
   #include <iostream>
   using namespace std;
   void main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   Bu ekranda tek satırlık metin yazın ve ardından çıkış çok basit bir programdır. Hatalar en aza indirmek için bu kodu kopyalayın ve Not Defteri'ne yapıştırın.

4. Çalışmalarınızı kaydedin! Not Defteri'nde, üzerinde **dosya** menüsünde seçin **kaydetmek**.

   Tebrikler, bir Visual C++ kaynak dosyası derlemek hazır hello.cpp, oluşturdunuz.

5. Geliştirici komut istemi penceresine dönün. Girin **dir** c:\hello dizinin içeriğini listelemek için komut isteminde. Kaynak dosya hello.cpp şunun gibi dizin listesinde görmeniz gerekir:

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

   Tarihler ve diğer ayrıntıları bilgisayarınızda farklılık gösterir. Kaynak kodu dosyasının görmüyorsanız, hello.cpp, oluşturduğunuz c:\hello dizinine değiştirdiyseniz emin olun ve Not Defteri'nde, bu dizine, kaynak dosyanızı kaydedilmiş olduğundan emin olun. Ayrıca, kaynak kodu bir .cpp dosya adı uzantısı ile .txt uzantısı kaydettiğiniz emin olun.

6. Geliştirici komut isteminde girin `cl /EHsc hello.cpp` programınızı derlemek için.

   Cl.exe derleyicisi derlenmiş kod içeren ve hello.exe adlı bir yürütülebilir programı oluşturmak için bağlayıcı çalıştıran bir .obj dosyası oluşturur. Bu ad derleyici görüntüler çıkış bilgileri satırlarda görünür. Derleyici çıktısı aşağıdakine benzer görünmelidir:

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
   > "'Cl' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor"gibi bir hata alırsanız hatası C1034 ya da hatası LNK1104, geliştirici komut istemi düzgün ayarlanmamış. Bu sorunu düzeltme konusunda daha fazla bilgi için geri dönüp **bir geliştirici komut istemi açın** bölümü.

   > [!NOTE]
   > Farklı derleyici veya bağlayıcı hata veya uyarı alırsanız, hataları düzeltin, ardından dosyayı kaydedin ve derleyici yeniden çalıştırmak için kaynak kodunuzu gözden geçirin. Belirli hataları hakkında daha fazla bilgi için hata numarası aramak için bu MSDN sayfada arama kutusunu kullanın.

7. Komut isteminde hello.exe programı çalıştırmak için şunu girin `hello`.

   Bu metin program görüntüler ve çıkar:

   ```Output
   Hello, world, from Visual C++!
   ```

   Tebrikler, sadece derlenmiş artık ve komut satırı araçlarını kullanarak bir C++ programını çalıştırın.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Hello, World" C++ programı alabilirsiniz hakkında kadar basit örneğidir. Gerçek dünya programlarının kitaplıklarında bağlamak ve yararlı çalışma yapın üstbilgi dosyaları ve daha fazla kaynak dosyaları, vardır.

Bu izlenecek adımları gösterilen örnek kod yazmaya yerine kendi C++ kodu oluşturmak için kullanabilirsiniz. Başka bir yerde Bul birçok C++ kodu örnek programlar da oluşturabilirsiniz. Kaynak kodunuz koyun ve uygulamalarınızı yazılabilir bir dizin oluşturun. Varsayılan olarak, Visual Studio IDE projeleri, Belgeler klasöründe, Visual Studio sürümünüze adlı bir Visual Studio klasörünün projeleri alt oluşturur.

Birden çok kaynak kodu dosyaları olan bir program derlemek için tüm komut satırında, bu gibi girin:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

**/EHsc** C++ özel durum işleme etkinleştirmek için derleyici komut satırı seçeneği bildirir. Daha fazla bilgi için bkz: [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md).

Bu gibi birden çok kaynak dosyaları sağladığında, derleyici ilk giriş dosyası program adı oluşturmak için kullanır. Bu durumda, file1.exe adlı bir programı çıkarır. Eklemek için program1.exe adını değiştirmek için bir [/out](../build/reference/out-output-file-name.md) bağlayıcı seçeneği:

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Daha fazla programlama hataları otomatik olarak yakalamak için derleme kullanarak öneririz [/W3](../build/reference/compiler-option-warning-level.md) veya [/W4](../build/reference/compiler-option-warning-level.md) Uyarısı Düzeyi:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Derleyici, cl.exe, yapı, en iyi duruma getirme, hata ayıklama için geçerlidir ve kodunuzun analiz pek çok seçenek vardır. Hızlı bir listesi için girin **cl /?** Geliştirici komut isteminde. Ayrıca derlemek ve da ayrı ayrı bağlantı ve daha karmaşık yapı senaryolarda bağlayıcı seçenekleri uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanım hakkında daha fazla bilgi için bkz: [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).

Yapılandırmak ve komut satırında derleme daha karmaşık projeleri için NMAKE ve derleme görevleri dosyaları veya MSBuild ve proje dosyalarını kullanabilirsiniz. Bu araçları kullanarak daha fazla bilgi için bkz: [NMAKE başvurusu](../build/nmake-reference.md) ve [MSBuild](../build/msbuild-visual-cpp.md).

C ve C++ dilleri benzer, ancak aynı. Visual C++ derleyicisi basit bir kural kodunuzu derlediğinde kullanılan dili belirlemek için kullanır. Varsayılan olarak, Visual C++ Derleyici .c C kaynak kodu olarak bitiş tüm dosyaları ve C++ kaynak kodu olarak .cpp bitiş tüm dosyaları işler. Tüm dosyalar C++ bağımsız olarak dosya adı uzantısını işlemek için derleyici zorlamak için kullanmak [tp](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneği.

Visual C++ derleyicisi ISO C99 standart uyumludur, ancak tamamen uyumlu bir C çalışma zamanı kitaplığı (CRT) içerir. Çoğu durumda, taşınabilir kodu derleyin ve beklendiği gibi çalıştırın. Visual C++ CRT değişikliklerden bazıları ISO C11 desteklemez. Belirli kitaplık işlevleri ve POSIX işlev adları Visual C++ derleyicisi tarafından kullanım dışı bırakılmıştır. İşlevler desteklenir, ancak tercih edilen adları değiştirilmiştir. Daha fazla bilgi için bkz: [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) ve [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)  
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)  
[Derleyici Seçenekleri](../build/reference/compiler-options.md)  
