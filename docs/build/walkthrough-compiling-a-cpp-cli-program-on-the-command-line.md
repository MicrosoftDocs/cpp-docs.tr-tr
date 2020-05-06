---
title: 'İzlenecek Yol: Komut Satırında C++/CLI Programını Derleme'
ms.date: 04/23/2019
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
ms.openlocfilehash: 8a5c5659367350a80725b365ef9c431bbec209d1
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877450"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında C++/CLI Programını Derleme

Ortak dil çalışma zamanını (CLR) hedefleyen Visual C++ programlar oluşturabilir ve .NET Framework kullanabilir ve bunları komut satırında oluşturabilirsiniz. Visual C++, .NET programlama modelini hedeflemek için ek tür ve işleçlere sahip C++/CLı programlama dilini destekler. C++/CLı dili hakkında genel bilgi için bkz. [c++/CLI ile .NET programlama (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

Bu kılavuzda, temel bir C++/CLı programı oluşturmak ve ardından komut satırında derlemek için bir metin düzenleyicisi kullanın. (Gösterilen birini yazmak yerine kendi C++/CLı programınızı kullanabilir ya da başka bir yardım makalesindeki C++/CLı kod örneğini kullanabilirsiniz. Bu teknik, Kullanıcı arabirimi öğeleri olmayan küçük modüller oluşturmak ve test etmek için kullanışlıdır.)

## <a name="prerequisites"></a>Ön koşullar

C++ dilinin temellerini anlamış olursunuz.

## <a name="compiling-a-ccli-program"></a>C++/CLı programını derleme

Aşağıdaki adımlarda .NET Framework sınıfları kullanan bir C++/CLı konsol uygulamasının nasıl derlenmesi gösterilmektedir.

C++/CLı için derlemeyi etkinleştirmek üzere [/clr](reference/clr-common-language-runtime-compilation.md) derleyici seçeneğini kullanmanız gerekir. MSVC derleyicisi, MSIL kodu içeren bir. exe dosyası ya da karma MSIL ve yerel kod ve gerekli .NET Framework kitaplıklarına bağlantılar oluşturur.

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>Komut satırında C++/CLı uygulaması derlemek için

1. **Geliştirici komut istemi** penceresini açın. Belirli yönergeler için bkz. [bir geliştirici komut istemi penceresi açmak için](building-on-the-command-line.md#developer_command_prompt).

   Bilgisayarın işletim sistemine ve yapılandırmasına bağlı olarak, kodu başarıyla derlemek için yönetici kimlik bilgileri gerekebilir. Komut istemi penceresini yönetici olarak çalıştırmak için sağ tıklayarak komut istemi için kısayol menüsünü açın ve **daha** > sonra**yönetici olarak çalıştır**' ı seçin.

1. Komut isteminde, girin `notepad basicclr.cpp`.

   Bir dosya oluşturmanız istendiğinde **Evet** ' i seçin.

1. Not defteri 'nde şu satırları girin:

   ```cpp
   int main()
   {
       System::Console::WriteLine("This is a C++/CLI program.");
   }
   ```

1. Menü çubuğunda **Dosya** > **Kaydet**' i seçin.

   <xref:System> Ad alanında .NET Framework Class (<xref:System.Console>) kullanan bir Visual C++ kaynak dosyası oluşturdunuz.

1. Komut isteminde, girin `cl /clr basicclr.cpp`. CL. exe derleyicisi, kaynak kodu MSIL içeren bir. obj dosyasına derler ve sonra, basicclr. exe adlı bir yürütülebilir program oluşturmak için bağlayıcıyı çalıştırır.

1. Basicclr. exe programını çalıştırmak için komut isteminde yazın `basicclr`.

   Program bu metni görüntüler ve çıkar:

   ```Output
   This is a C++/CLI program.
   ```

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
