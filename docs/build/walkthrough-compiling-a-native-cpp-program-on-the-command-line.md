---
title: 'İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme'
description: Microsoft C++ derleyicisini komut isteminden kullanın.
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

Visual Studio komut satırı C ve C++ derleyicisi içerir. Temel konsol uygulamalarından Evrensel Windows Platformu uygulamalarına, Masaüstü uygulamalarına, aygıt sürücülerine ve .NET bileşenlerine kadar her şeyi oluşturmak için kullanabilirsiniz.

Bu izbarada, bir metin düzenleyicisi kullanarak temel bir "Hello, World" tarzı Bir C++ programı oluşturur ve komut satırında derlersiniz. Komut satırını kullanmak yerine Visual Studio IDE'yi denemek istiyorsanız, [Walkthrough: Projects and Solutions (C++) ile çalışmak](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ Masaüstü Geliştirme için Visual Studio IDE'yi kullanmak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)bölümüne bakın.

Bu izbarada, gösterilenprogramı yazmak yerine kendi C++ programınızı kullanabilirsiniz. Veya başka bir yardım makalesinden C++ kodu örneği kullanabilirsiniz.

## <a name="prerequisites"></a>Ön koşullar

Bu gözden geçirmeyi tamamlamak için Visual Studio'yu ve C++ iş yüküne sahip isteğe bağlı **Masaüstü geliştirmeyi** veya Visual Studio için komut satırı Oluşturma Araçlarını yüklemiş olmalısınız.

Visual Studio entegre bir *geliştirme ortamıdır* (IDE). Birçok dil ve platform için tam özellikli bir düzenleyiciyi, kaynak yöneticilerini, hata ayıklayıcılarını ve derleyicilerini destekler. Mevcut sürümler ücretsiz Visual Studio Community sürümünü içerir ve tümü C ve C++ gelişimini destekleyebilir. Visual Studio'u nasıl indirip yükleyin hakkında bilgi için [Visual Studio'da C++ desteği yükleyin'](vscpp-step-0-installation.md)e bakın.

Visual Studio için Yapı Araçları yalnızca C ve C++ programları oluşturmak için gereken komut satırı derleyicilerini, araçları ve kitaplıkları yükler. Bu laboratuvarlar veya sınıf egzersizleri oluşturmak için mükemmel ve nispeten hızlı yükler. Yalnızca komut satırı araçlarını yüklemek için [Visual Studio İndirmeler](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019) sayfasında Visual Studio için Araçlar Oluştur'u arayın.

Komut satırında bir C veya C++ programı oluşturmadan önce, araçların yüklü olduğunu doğrulayın ve bunlara komut satırından erişebilirsiniz. Visual C++'ın kullandığı araçları, üstbilgi ve kitaplıkları bulmak için komut satırı ortamı için karmaşık gereksinimleri vardır. Bazı hazırlıkyapmadan **Visual C++'ı düz komut istemi penceresinde kullanamazsınız.** Neyse ki, Visual C++ komut satırı oluşturmaları için ortam ayarlı bir geliştirici komut istemi başlatmak için kısayollar yükler. Ne yazık ki, geliştirici komutunun adları kısayolları ve bulundukları yer Visual C++'nin hemen hemen her sürümünde ve Windows'un farklı sürümlerinde farklıdır. İlk gözden geçirme göreviniz kullanmak için doğru olanı bulmaktır.

> [!NOTE]
> Geliştirici komut istemi kısayolu, derleyici ve araçlar ve gerekli üstbilgi ve kitaplıklar için doğru yolları otomatik olarak ayarlar. Normal bir **Komut İstem penceresi** kullanıyorsanız, bu ortam değerlerini kendiniz ayarlamanız gerekir. Daha fazla bilgi için [bkz.](setting-the-path-and-environment-variables-for-command-line-builds.md) Kendi komutunuzu oluşturmak yerine geliştirici komut istemi kısayolu kullanmanızı öneririz.

### <a name="open-a-developer-command-prompt"></a>Geliştirici komut istemiaçma

1. Visual Studio 2017'yi veya daha sonra Windows 10'u yüklediyseniz, Başlat menüsünü açın ve **Tüm uygulamaları**seçin. Aşağı kaydırın ve **Visual Studio** klasörünü açın (Visual Studio uygulaması değil). Komut istemi penceresini açmak **için VS için Geliştirici Komut Komut Ustem'i** seçin.

   Microsoft Visual C++ Build Tools 2015'i Windows 10'a yüklediyseniz, **Başlat** menüsünü açın ve **Tüm uygulamaları**seçin. Aşağı kaydırın ve **Visual C++ Build Tools** klasörünü açın. Komut istemi penceresini açmak için **Visual C++ 2015 x86 Native Tools Komut Komut İstemi'ni** seçin.

   Windows arama işlevini kullanarak "geliştirici komut istemi" arayabilir ve Visual Studio'nun yüklü sürümünüzle eşleşen bir tane seçebilirsiniz. Komut istemi penceresini açmak için kısayolu kullanın.

1. Ardından, Visual C++ geliştirici komut isteminin doğru şekilde ayarlıştırış olduğunu doğrulayın. Komut istemi penceresinde, `cl` çıktının aşağıdaki gibi göründüğünü girin ve doğrulayın:

   ```Output
   C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl
   Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86
   Copyright (C) Microsoft Corporation.  All rights reserved.

   usage: cl [ option... ] filename... [ /link linkoption... ]
   ```

   Geçerli dizin veya sürüm numaralarında farklılıklar olabilir. Bu değerler Visual C++ sürümüne ve yüklenen güncelleştirmeye bağlıdır. Yukarıdaki çıktı gördüklerinizin benzersiyse, komut satırında C veya C++ programları oluşturmaya hazırsınız demektir.

   > [!NOTE]
   > "'cl' gibi bir hata alırsanız bir iç veya dış komut, operable program veya toplu dosya olarak kabul edilmez," hata C1034 veya hata LNK1104 **`cl`** komutu çalıştırdığınızda, o zaman ya bir geliştirici komut istemi kullanmıyorsanız, ya da bir şey Visual C++ yükleme ile yanlış. Devam etmeden önce bu sorunu gidermeniz gerekir.

   Geliştirici komut istemi kısayolu bulamıyorsanız veya girdiğinizde `cl`bir hata iletisi alırsanız, Visual C++ yüklemenizde bir sorun olabilir. Visual Studio'da Visual C++ bileşenini yeniden yüklemeyi veya Microsoft Visual C++ Yapı Araçlarını yeniden yüklemeyi deneyin. Komut çalışana kadar bir sonraki **`cl`** bölüme geçme. Visual C++'ı yükleme ve sorun giderme hakkında daha fazla bilgi için Visual [Studio'ya yükle'ye](/visualstudio/install/install-visual-studio)bakın.

   > [!NOTE]
   > Bilgisayardaki Windows sürümüne ve sistem güvenliği yapılandırmasına bağlı olarak, geliştirici komut istemi kısayolu için kısayol menüsünü açmak için sağ tıklatmanız ve ardından bu gözden geçirmeyi izleyerek oluşturduğunuz programı başarıyla oluşturmak ve çalıştırmak için **yönetici olarak Çalıştır'ı** seçmeniz gerekebilir.

### <a name="create-a-visual-c-source-file-and-compile-it-on-the-command-line"></a>Visual C++ kaynak dosyası oluşturun ve komut satırında derle

1. Geliştirici komut istemi penceresinde, `md c:\hello` bir dizin oluşturmak için `cd c:\hello` girin ve sonra bu dizine değiştirmek için girin. Bu dizin, kaynak dosyanızın ve derlenen programın oluşturulduğu yerdir.

1. Komut `notepad hello.cpp` istemi penceresine girin.

   Not Defteri bir dosya oluşturmanızı istediğinde **Evet'i** seçin. Bu adım, hello.cpp adlı bir dosyaya kodunuzu girmeniz için hazır boş bir Not Defteri penceresi açar.

1. Not Defteri'nde aşağıdaki kod satırlarını girin:

   ```cpp
   #include <iostream>
   using namespace std;
   int main()
   {
       cout << "Hello, world, from Visual C++!" << endl;
   }
   ```

   Bu kod, ekrana bir metin satırı yazıp sonra çıkan basit bir programdır. Hataları en aza indirmek için bu kodu kopyalayın ve Not Defteri'ne yapıştırın.

1. İşini kurtar! Not Defteri'nde, **Dosya** menüsünde **Kaydet'i**seçin.

   Tebrikler, derlemeye hazır bir C++ kaynak dosyası, hello.cpp oluşturdunuz.

1. Geliştirici komut istemi penceresine geri dön. c:\hello dizininin içeriğini listelemek için komut istemine girin. `dir` Bu gibi bir şey görünüyor dizin listesinde kaynak dosya hello.cpp görmelisiniz:

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

   Tarihler ve diğer ayrıntılar bilgisayarınızda farklılık gösterir. Kaynak kod dosyanızı görmüyorsanız, *hello.cpp,* oluşturduğunuz *\\c: hello* dizinini değiştirdiğinizden emin olun. Not Defteri'nde, kaynak dosyanızı bu dizine kaydettiğinizden emin olun. Ayrıca, kaynak kodunu bir *`.cpp`* *`.txt`* uzantıyla değil, bir dosya adı uzantısı ile kaydettiğinden emin olun.

1. Geliştirici komut isteminde, `cl /EHsc hello.cpp` programınızı derlemek için girin.

   CL.exe derleyicisi derlenmiş kodu içeren bir .obj dosyası oluşturur ve sonra hello.exe adlı yürütülebilir bir program oluşturmak için bağlayıcıyı çalıştırır. Bu ad, derleyicinin görüntülenebilen çıktı bilgileri satırlarında görünür. Derleyicinin çıktısı aşağıdaki gibi görünmelidir:

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
   > "'cl' gibi bir hata alırsanız, "dahili veya harici komut, çalışabilir program veya toplu iş dosyası" hatası C1034 veya lNK1104 hatası olarak tanımlanamazsa, geliştirici komut isteminiz doğru şekilde ayarlanmaz. Bu sorunun nasıl giderilenhakkında bilgi için **geliştirici komut istemi** aç bölümüne geri dön.

   > [!NOTE]
   > Farklı bir derleyici veya bağlayıcı hatası veya uyarı alırsanız, hataları düzeltmek için kaynak kodunuzu gözden geçirin, ardından kaydedin ve derleyiciyi yeniden çalıştırın. Belirli hatalar hakkında bilgi almak için, hata numarasını aramak için bu MSDN sayfasındaki arama kutusunu kullanın.

1. hello.exe programını çalıştırmak için komut istemine `hello`girin.

   Program bu metni görüntüler ve çıkar:

   ```Output
   Hello, world, from Visual C++!
   ```

   Tebrikler, komut satırı araçlarını kullanarak bir C++ programını derleyip çalıştırDın.

## <a name="next-steps"></a>Sonraki adımlar

Bu "Merhaba, Dünya" örneği, bir C++ programının alabildiği kadar basittir. Gerçek dünya programları genellikle üstbilgi dosyaları, daha fazla kaynak dosyaları ve kitaplıklara bağlantı var.

Bu izbindeki adımları, gösterilen örnek kodu yazmak yerine kendi C++ kodunuzu oluşturmak için kullanabilirsiniz. Bu adımlar, başka bir yerde bulduğunuz birçok C++ kodu örnek programı oluşturmanıza da izin verir. Kaynak kodunuzu koyabilir ve uygulamalarınızı yazılabilir herhangi bir dizinde oluşturabilirsiniz. Varsayılan olarak, Visual Studio IDE kullanıcı klasörünüzde, bir *kaynak\\deposu* alt klasöründe projeler oluşturur. Eski sürümler projeleri *Documents\\Visual \<Studio \\sürümüne *>Projeler* klasörüne koyabilir.

Ek kaynak kodu dosyaları olan bir program derlemek için, bunların tümlerini komut satırına girin:

`cl /EHsc file1.cpp file2.cpp file3.cpp`

`/EHsc` Komut satırı seçeneği, derleyiciye standart C++ özel durum işleme davranışını etkinleştirmesini bildirir. Bu olmadan, atılan özel durumlar yok edilmemiş nesnelere ve kaynak sızıntılarına neden olabilir. Daha fazla bilgi için bkz: [/EH (Özel Durum Taşıma Modeli).](reference/eh-exception-handling-model.md)

Ek kaynak dosyaları sağladığınızda, derleyici program adını oluşturmak için ilk giriş dosyasını kullanır. Bu durumda, file1.exe adlı bir program çıktırıyor. Adı program1.exe olarak değiştirmek için [bir /out](reference/out-output-file-name.md) bağlayıcı seçeneği ekleyin:

`cl /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Daha fazla programlama hatasını otomatik olarak yakalamak için [/W3](reference/compiler-option-warning-level.md) veya [/W4](reference/compiler-option-warning-level.md) uyarı düzeyi seçeneğini kullanarak derlemenizi öneririz:

`cl /W4 /EHsc file1.cpp file2.cpp file3.cpp /link /out:program1.exe`

Derleyici, cl.exe, çok daha fazla seçenek vardır. Bunları kodunuzu oluşturmak, optimize etmek, hata ayıklamak ve çözümlemek için uygulayabilirsiniz. Hızlı bir liste `cl /?` için geliştirici komut istemine girin. Ayrıca ayrı ayrı derleyebilir ve bağlantı kurabilir ve daha karmaşık yapı senaryolarında bağlayıcı seçenekleri uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanımı hakkında daha fazla bilgi için [C/C++ Yapı Başvurusu'na](reference/c-cpp-building-reference.md)bakın.

Komut satırında daha karmaşık projeleri yapılandırmak ve oluşturmak için NMAKE ve makefiles, MSBuild ve proje dosyaları veya CMake'i kullanabilirsiniz. Bu araçları kullanma hakkında daha fazla bilgi için Visual Studio'daki [NMAKE Reference,](reference/nmake-reference.md) [MSBuild](msbuild-visual-cpp.md)ve [CMake projelerine](cmake-projects-in-visual-studio.md)bakın.

C ve C++ dilleri benzerdir, ancak aynı değildir. MSVC derleyicisi, kodunuzu derlediğinde hangi dili kullanacağınızı belirlemek için basit bir kural kullanır. Varsayılan olarak, MSVC derleyicisi C *`.c`* kaynak kodu olarak biten dosyaları *`.cpp`* ve C++ kaynak kodu olarak biten dosyaları ele alır. Derleyiciyi dosya adı uzantısından bağımsız olarak tüm dosyaları C++ olarak ele almaya zorlamak için [/TP](reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneğini kullanın.

MSVC derleyicisi, küçük istisnalar dışında ISO C99 standardına uygun bir C Runtime Kitaplığı (CRT) içerir. Taşınabilir kod genellikle derler ve beklendiği gibi çalışır. Bazı eski kitaplık işlevleri ve birkaç POSIX işlev adları, MSVC derleyicisi tarafından amortismana alınır. Işlevler desteklenir, ancak tercih edilen adlar değişti. Daha fazla bilgi için [CRT](../c-runtime-library/security-features-in-the-crt.md) ve [Derleyici Uyarısı'ndaki Güvenlik Özellikleri (düzey 3) C4996'ya](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Referansı](../cpp/cpp-language-reference.md)<br/>
[Projeler ve yapı sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
