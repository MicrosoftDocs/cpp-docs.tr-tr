---
title: 'İzlenecek yol: derleme C + +/ CLI programını komut satırında | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81e5b8119c8921da28c6ad93b257234e0998083a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında C++/CLI Programını Derleme
Ortak dil çalışma zamanı (CLR) hedeflemek ve .NET Framework kullanan Visual C++ programları oluşturma ve bunları komut satırında derleme. Visual C++ destekler C + +/ ek türleri ve işleçler .NET programlama modeli hedeflemek için CLI programlama dili. Giriş için C + +/ CLI dilinin bkz [saf C++: C + Hello, +/ CLI](http://msdn.microsoft.com/magazine/cc163681.aspx). Genel bilgi için bkz: [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 Bu kılavuzda, temel C + oluşturmak için bir metin düzenleyicisi kullanın +/ CLI programını ve komut satırında derleme. (Kullanabileceğiniz kendi C + +/ CLI programını gösterilen bir yazmak yerine veya kullanabilirsiniz C + +/ CLI kodunu örnekten başka bir Yardım makalesi. Bu teknik oluşturma ve hiçbir kullanıcı Arabirimi öğeleri içeren küçük modülleri sınamak için kullanışlıdır.)  
  
> [!NOTE]
>  C + derlemek için Visual Studio IDE kullanabilirsiniz +/ CLI programlar. Daha fazla bilgi için bkz: [izlenecek yol: Visual Studio'da CLR'yi hedefleyen C++ programını derleme](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).  
  
## <a name="prerequisites"></a>Önkoşullar  
 C++ dil temelleri anlamanız gerekir.  
  
## <a name="compiling-a-ccli-program"></a>Derleme C + +/ CLI programını  
 Aşağıdaki adımları Göster nasıl yapılandırılabileceğini C + +/ CLI konsol .NET Framework sınıfları kullanan bir uygulama.  
  
 Derleme için C + etkinleştirmek için +/ CLI, kullanmalıdır [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. Visual C++ derleyicisi MSIL kodu içeren bir .exe dosyası oluşturur — veya karma MSIL ve yerel kodu — ve gerekli .NET Framework kitaplıklarına bağlantılar.  
  
#### <a name="to-compile-a-ccli-application-on-the-command-line"></a>Derlenecek C + +/ CLI uygulama komut satırında  
  
1.  Açık bir **Geliştirici komut istemi** penceresi. Ayrıntılı yönergeler için bkz: [bir geliştirici komut istemi penceresi açmak için](../build/building-on-the-command-line.md#developer_command_prompt).  
  
     Yönetici kimlik bilgileri başarıyla bilgisayarın işletim sistemine ve yapılandırmasına bağlı olarak kod derlemek için gerekli. Komut İstemi penceresi bir yönetici olarak çalıştırmak için komut istemi için kısayol menüsünü açın ve ardından sağ **daha fazla**, **yönetici olarak çalıştır**.  
  
2.  Komut isteminde girin **not defteri basicclr.cpp**.  
  
     Seçin **Evet** sizden istendiğinde dosya oluşturulamadı.  
  
3.  Not Defteri'nde, bu satırları girin:  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  Menü çubuğunda seçin **dosya**, **kaydetmek**.  
  
     .NET Framework sınıf kullanan bir Visual C++ kaynak dosyası oluşturdunuz (<xref:System.Console>) içinde <xref:System> ad alanı.  
  
5.  Komut isteminde girin **cl/CLR basicclr.cpp**. Cl.exe derleyicisi kaynak kodunu MSIL içeren ve basicclr.exe adlı bir yürütülebilir programı oluşturmak için bağlayıcı çalıştıran bir .obj dosyasına kaydeder.  
  
6.  Komut isteminde basicclr.exe programı çalıştırmak için şunu girin **basicclr**.  
  
     Bu metin program görüntüler ve çıkar:  
  
    ```Output  
    This is a C++/CLI program.  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C/C++ programları oluşturma](../build/building-c-cpp-programs.md)   
 [Derleyici Seçenekleri](../build/reference/compiler-options.md)