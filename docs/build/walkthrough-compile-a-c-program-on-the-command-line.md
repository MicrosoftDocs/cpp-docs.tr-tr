---
title: 'İzlenecek yol: komut satırında C programı derleme | Microsoft Docs'
ms.custom: conceptual
ms.date: 11/04/2016
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
ms.openlocfilehash: 033c29ff9871a427222b59fbf5c8350794a9bbe2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-compile-a-c-program-on-the-command-line"></a>İzlenecek yol: komut satırında C programı derleme
Visual C++ her şeyin tam Windows Masaüstü uygulamaları, mobil uygulamaları ve daha fazla bilgi için temel konsol programlardan oluşturmak için kullanabileceğiniz bir C Derleyici içerir.  
  
 Bu kılavuzda "Hello, World" basic oluşturulacağını gösterir-C programı bir metin kullanarak Düzenleyicisi stil ve komut satırında derleme. C++'ta komut satırında işe, bkz: [izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md). İsterseniz bkz komut satırını kullanarak yerine Visual Studio IDE deneyin [izlenecek yol: projeler ve çözümler (C++) ile çalışma](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) veya [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu izlenecek yolu tamamlamak için Visual Studio ve isteğe bağlı Visual C++ bileşenler veya Microsoft Visual C++ derleme araçları yüklü gerekir.  
  
 Visual Studio birçok diller ve platformlar için tam özellikli bir düzenleyici, kaynak yöneticileri, hata ayıklayıcıları ve derleyicileri destekleyen bir güçlü tümleşik geliştirme ortamıdır. Bu özellikler ve nasıl karşıdan yüklenir ve ücretsiz Visual Studio Community sürümü de dahil olmak üzere Visual Studio yükleme hakkında bilgi için bkz: [VisualStudio.com](https://www.visualstudio.com/).  
  
 Yapı Visual Studio Araçları, yalnızca komut satırı derleyicileri, Araçlar ve C ve C++ programları oluşturmak için gereken kitaplıklar yükler. Yapı Laboratuvarları için mükemmeldir veya sınıf kullanır ve oldukça hızlı bir şekilde yükler. Yalnızca komut satırı araçlarını yüklemek için indirme [Visual Studio derleme Araçları](https://go.microsoft.com/fwlink/p/?linkid=840931) ve yükleyiciyi çalıştırın. Daha fazla bilgi için bkz: [Visual C++ derleme Araçları](http://landinghub.visualstudio.com/visual-cpp-build-tools).  
  
 Komut satırında C veya C++ programı oluşturmadan önce Araçları yüklenir ve bunları komut satırından erişebildiğinizi doğrulamanız gerekir. Visual C++ Araçları, üst bilgilerinin ve kitaplıklarının kullandığı bulmak için komut satırı ortamı için karmaşık gereksinimleri vardır. **Visual C++ düz komut istemi penceresinde kullanamazsınız**. Gereksinim duyduğunuz bir *Geliştirici komut istemi* tüm gerekli ortam değişkenleri kümesini sahip bir normal bir komut istemi penceresi penceresi. Neyse ki, Visual C++, komut satırı derlemeleri için ayarlanan ortam sahip bir geliştirici komut istemlerini başlatmak kısayol yükler. Ne yazık ki, geliştirici komut istemi kısayolları ve nerede olurlarsa olsunlar adları neredeyse her sürümü Visual C++ ve farklı Windows sürümleri üzerinde farklı. İlk kılavuz göreviniz kullanmak için doğru kısayol bulmaktır.  
  
> [!NOTE]
>  Bir geliştirici komut istemi kısayoluna doğru yol ve tüm gerekli üst bilgilerinin ve kitaplıklarının derleyici ve araçları için otomatik olarak ayarlar. Bu değerlerden bazıları her yapı yapılandırması için farklı olur. Kısayollar birini kullanmıyorsanız, bu ortam değerleri kendiniz ayarlamanız gerekir. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../build/setting-the-path-and-environment-variables-for-command-line-builds.md). Yapı ortamı karmaşık olduğu için kendi oluşturmak yerine bir geliştirici komut istemi kısayoluna kullanmanız önerilir.  
  
## <a name="open-a-developer-command-prompt"></a>Bir geliştirici komut istemi açın  
  
1.  Visual Studio 2017 üzerinde Windows 10 yüklü değilse Başlat menüsünü açın ve ardından aşağı kaydırın ve açın **Visual Studio 2017** klasörü (Visual Studio 2017 uygulama değil). Seçin **VS 2017 için geliştirici komut istemi** komut istemi penceresi açın.  
  
     Microsoft Visual C++ derleme araçları 2015 üzerinde Windows 10 yüklü değilse, açmak **Başlat** menüsünde ve sonra aşağı kaydırın ve açık **Visual C++ derleme Araçları** klasör. Seçin **Visual C++ 2015 x86 yerel Araçları Komut İstemi** komut istemi penceresi açın.  
  
     Visual Studio farklı bir sürümünü kullanıyorsanız veya farklı bir Windows sürümü çalıştıran, başlangıç sayfası için geliştirici komut istemi kısayolunu içeren bir Visual Studio Araçları klasörü veya Başlat menüde arayın. "Geliştirici komut istemi" araması yapın ve yüklü Visual Studio sürümünüzle eşleşen birini seçmek için Windows Arama işlevini de kullanabilirsiniz. Komut İstemi penceresi açmak için kısayolu kullanın.  
  
2.  Ardından, Visual C++ Geliştirici komut istemi doğru ayarlandığını doğrulayın. Komut İstemi penceresinde girin `cl` ve çıktı şuna benzediğini doğrulayın:  
  
    ```Output  
    C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>cl  
    Microsoft (R) C/C++ Optimizing Compiler Version 19.10.25017 for x86  
    Copyright (C) Microsoft Corporation.  All rights reserved.  
    
    usage: cl [ option... ] filename... [ /link linkoption... ]  
    
    C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise>  
    ```  
  
     Geçerli dizinde veya Visual C++ ve yüklü herhangi bir güncelleştirme sürümüne bağlı olarak sürüm numaralarını farklılıklar olabilir. Ardından, görmek için benzer ise, komut satırında C veya C++ programları oluşturmak hazırsınız demektir.  
  
    > [!NOTE]
    >  "'Cl' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor"gibi bir hata alırsanız hatası C1034 ya da hatası çalıştırdığınızda LNK1104 **cl** ya da bir geliştirici komut istemi kullanmıyorsanız, komut veya Visual C++ yüklemenizle yanlış bir şeydir. Devam etmeden önce bu sorunu düzeltmeniz gerekir.  
  
     Geliştirici komut istemi kısayoluna bulamazsa ya da bunu girdiğinizde bir hata iletisi alırsanız `cl`, sonra da Visual C++ yüklemenizin bir sorun olabilir. Visual Studio Visual C++ bileşeni yeniden yüklemeyi deneyin veya Visual Studio Araçları yapı yeniden yükleyin. Bu çalışır kadar sonraki bölüme gidin yok. Yükleme ve Visual C++ sorunlarını giderme hakkında daha fazla bilgi için bkz: [Visual Studio yükleme](/visualstudio/install/install-visual-studio).  
  
    > [!NOTE]
    >  Windows sürümü bağlı olarak bilgisayarda ve sistem güvenlik yapılandırması, geliştirici komut istemi kısayoluna için kısayol menüsünü açın ve ardından sağ gerekebilir **yönetici olarak çalıştır** için başarılı bir şekilde oluşturmak ve bu kılavuzu izleyerek oluşturun programını çalıştırın.  
  
## <a name="create-a-c-source-file-and-compile-it-on-the-command-line"></a>C kaynak dosyası oluşturma ve komut satırında derleme  
  
1.  Geliştirici komut istemi penceresinde girin **cd c:\\**  C: sürücüsünün köküne geçerli çalışma dizini değiştirmek için. Ardından, girin **md c:\simple** bir dizin oluşturun ve ardından girin **cd c:\simple** bu dizine gidin. Bu kaynak dosyanızı ve derlenmiş program içeren dizindir.  
  
2.  Girin **not defteri simple.c** Geliştirici komut isteminde. Açılır not defteri uyarı iletişim kutusunda, seçin **Evet** çalışma dizininizde yeni simple.c dosya oluşturulamadı.  
  
3.  Not Defteri'nde, aşağıdaki kod satırlarını girin:  
  
    ```C  
    #include <stdio.h>  
  
    int main()  
    {  
        printf("Hello, World! This is a native C program compiled on the command line.\n");  
        return 0;  
    }   
    ```  
  
4.  Not Defteri'ni menü çubuğunda seçin **dosya**, **kaydetmek** simple.c çalışma dizininizi kaydetmek için.  
  
5.  Geliştirici komut istemi penceresine dönün. Girin **dir** c:\simple dizinin içeriğini listelemek için komut isteminde. Kaynak dosya simple.c şunun gibi dizin listesinde görmeniz gerekir:  
  
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
  
     Tarihler ve diğer ayrıntıları bilgisayarınızda farklılık gösterir. Kaynak kodu dosyasının görmüyorsanız, simple.c, oluşturduğunuz c:\simple dizinine değiştirdiyseniz emin olun ve Not Defteri'nde, bu dizine, kaynak dosyanızı kaydedilmiş olduğundan emin olun. Ayrıca, kaynak kodu bir .c dosya adı uzantısı ile .txt uzantısı kaydettiğiniz emin olun.  
  
6.  Programınızı derlemek için girin **cl simple.c** Geliştirici komut isteminde.  
  
     Yürütülebilir program adı, derleyici görüntüler çıkış bilgileri satırlarında simple.exe görebilirsiniz:  
  
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
    >  "'Cl' iç ya da dış komut, çalıştırılabilir program ya da toplu iş dosyası tanınmıyor"gibi bir hata alırsanız hatası C1034 ya da hatası LNK1104, geliştirici komut istemi düzgün ayarlanmamış. Bu sorunu düzeltme konusunda daha fazla bilgi için geri dönüp **bir geliştirici komut istemi açın** bölümü.  
  
    > [!NOTE]
    >  Farklı derleyici veya bağlayıcı hata veya uyarı alırsanız, hataları düzeltin, ardından dosyayı kaydedin ve derleyici yeniden çalıştırmak için kaynak kodunuzu gözden geçirin. Belirli hataları hakkında daha fazla bilgi için hata numarası aramak için bu MSDN sayfada arama kutusunu kullanın.  
  
7.  Programınızı çalıştırmak için girin **basit** komut isteminde.  
  
     Program bu metni görüntüleyen ve çıkar:  
  
    ```Output  
    Hello, World! This is a native C program compiled on the command line.  
    ```  
  
     Tebrikler, sadece derlenmiş artık ve komut satırı kullanarak C programı çalıştırın.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 Bu "Hello, World" örnek C programı alabilirsiniz gibi yaklaşık olarak basit bir işlemdir. Gerçek dünya programlarının kitaplıklarında bağlamak ve yararlı çalışma yapın üstbilgi dosyaları ve daha fazla kaynak dosyaları, vardır.  
  
 Bu izlenecek adımları gösterilen örnek kod yazmaya yerine kendi C kodu oluşturmak için kullanabilirsiniz. Başka bir yerde Bul birçok C kodu örnek programlar da oluşturabilirsiniz. Birden çok kaynak kodu dosyaları olan bir program derlemek için tüm komut satırında, bu gibi girin:  
  
 `cl file1.c file2.c file3.c`  
  
 Derleyici file1.exe adlı bir programı çıkarır. Eklemek için program1.exe adını değiştirmek için bir [/out](../build/reference/out-output-file-name.md) bağlayıcı seçeneği:  
  
 `cl file1.c file2.c file3.c /link /out:program1.exe`  
  
 Daha fazla programlama hataları otomatik olarak yakalamak için derleme kullanarak öneririz [/W3](../build/reference/compiler-option-warning-level.md) veya [/W4](../build/reference/compiler-option-warning-level.md) Uyarısı Düzeyi:  
  
 `cl /W4 file1.c file2.c file3.c /link /out:program1.exe`  
  
 Derleyici, cl.exe, yapı, en iyi duruma getirme, hata ayıklama için geçerlidir ve kodunuzun analiz pek çok seçenek vardır. Hızlı bir listesi için girin **cl /?** Geliştirici komut isteminde. Ayrıca derlemek ve da ayrı ayrı bağlantı ve daha karmaşık yapı senaryolarda bağlayıcı seçenekleri uygulayabilirsiniz. Derleyici ve bağlayıcı seçenekleri ve kullanım hakkında daha fazla bilgi için bkz: [C/C++ oluşturma başvurusu](../build/reference/c-cpp-building-reference.md).  
  
 Yapılandırmak ve komut satırında derleme daha karmaşık projeleri için NMAKE ve derleme görevleri dosyaları veya MSBuild ve proje dosyalarını kullanabilirsiniz. Bu araçları kullanarak daha fazla bilgi için bkz: [NMAKE başvurusu](../build/nmake-reference.md) ve [MSBuild](../build/msbuild-visual-cpp.md).  
  
 C ve C++ dilleri benzer, ancak aynı. Visual C++ derleyicisi basit bir kural kodunuzu derlediğinde kullanılan dili belirlemek için kullanır. Varsayılan olarak, Visual C++ Derleyici .c C kaynak kodu olarak bitiş tüm dosyaları ve C++ kaynak kodu olarak .cpp bitiş tüm dosyaları işler. Tüm dosyalar C bağımsız olarak dosya adı uzantısını işlemek için derleyici zorlamak için kullanmak [tp](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneği.  
  
 Visual C++ C Derleyici ISO C99 standart uyumlu genellikle, ama kesinlikle uyumlu değildir. Çoğu durumda, taşınabilir C kodu derleyin ve beklendiği gibi çalıştırın. Visual C++ değişiklikleri çoğunu ISO C11 desteklemez. Belirli kitaplık işlevleri ve POSIX işlev adları Visual C++ derleyicisi tarafından kullanım dışı bırakılmıştır. İşlevler desteklenir, ancak tercih edilen adları değiştirilmiştir. Daha fazla bilgi için bkz: [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md) ve [Derleyici Uyarısı (Düzey 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: bir standart C++ programı (C++) oluşturma](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)   
 [C Dil Başvurusu](../c-language/c-language-reference.md)   
 [C/C++ programları oluşturma](../build/building-c-cpp-programs.md)   
 [Uyumluluk](../c-runtime-library/compatibility.md)