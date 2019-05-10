---
title: 'İzlenecek yol: Derleme bir C++komut satırında /CLI programı'
ms.date: 04/23/2019
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
ms.openlocfilehash: 8a5c5659367350a80725b365ef9c431bbec209d1
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877450"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>İzlenecek yol: Derleme bir C++komut satırında /CLI programı

.NET Framework ortak dil çalışma zamanı (CLR) hedefleyen ve Visual C++ programları oluşturma ve bunları komut satırında oluşturun. Görsel C++ destekler C++/ek türleri ve işleçler .NET programlama modeli hedeflemek için olan dil, programlama CLI. Hakkında genel bilgiler C++/CLI dil bakın [.NET programlama C++/CLI (görsel C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

Bu kılavuzda, temel C + oluşturmak için bir metin düzenleyicisi kullanın +/ CLI programını ve sonra komut satırında derleyin. (Kendi kullanabilirsiniz C++/CLI programını gösterilen bir yazmak yerine veya kullanabileceğiniz bir C++/CLI kod örneğini başka bir Yardım makalesi. Bu teknik oluşturmak ve UI öğesi içermeyen olan küçük modülleri test etmek için kullanışlıdır.)

## <a name="prerequisites"></a>Önkoşullar

C++ dilinin temellerini anlamanız.

## <a name="compiling-a-ccli-program"></a>Derleme bir C++/CLI programı

Aşağıdaki adımlar nasıl yapılandırılabileceğini göstermektedir bir C++.NET Framework sınıfları kullanan /CLI konsol uygulaması.

Derleme için etkinleştirmek için C++/CLI, kullanmalıdır [/CLR](reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. MSVC derleyicisi, MSIL kodu içeren bir .exe dosyası oluşturur — veya karma MSIL ve yerel kod — ve gerekli .NET Framework kitaplıkları bağlanır.

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>Derlemek için bir C++komut satırında /CLI uygulama

1. Açık bir **Geliştirici komut istemi** penceresi. Ayrıntılı yönergeler için bkz: [bir geliştirici komut istemi penceresi açmak için](building-on-the-command-line.md#developer_command_prompt).

   Yönetici kimlik bilgileri başarıyla bilgisayarın işletim sistemi ve yapılandırmasına bağlı olarak Kodu derlemek için gerekebilir. Komut İstemi penceresini yönetici olarak çalıştırmak için komut istemi için kısayol menüsünü açın ve ardından sağ **daha fazla** > **yönetici olarak çalıştır**.

1. Komut isteminde girin `notepad basicclr.cpp`.

   Seçin **Evet** istenirse bir dosya oluşturmak için.

1. Not Defteri'nde şu satırı girin:

   ```cpp
   int main()
   {
       System::Console::WriteLine("This is a C++/CLI program.");
   }
   ```

1. Menü çubuğunda, **dosya** > **Kaydet**.

   .NET Framework sınıfı kullanan bir Visual C++ kaynak dosyasını, oluşturduğunuz (<xref:System.Console>) içinde <xref:System> ad alanı.

1. Komut isteminde girin `cl /clr basicclr.cpp`. Cl.exe derleyicisi, kaynak kodu MSIL içeren ve ardından bağlayıcı basicclr.exe adlı yürütülebilir bir program oluşturmak için çalışan bir .obj dosyasına derler.

1. Komut isteminde basicclr.exe programı çalıştırmak için girin `basicclr`.

   Program bu metni görüntüler ve çıkar:

   ```Output
   This is a C++/CLI program.
   ```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
