---
title: 'İzlenecek yol: derleme C + +/ CLI programını komut satırında | Microsoft Docs'
ms.custom: ''
ms.date: 09/24/2018
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
ms.openlocfilehash: bdc09d5c1de2e74f7e24b72439910068fe9f6c1a
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820639"
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında C++/CLI Programını Derleme

.NET Framework ortak dil çalışma zamanı (CLR) hedefleyen ve Visual C++ programları oluşturma ve bunları komut satırında oluşturun. Visual C++ destekler C + +/ ek türleri ve işleçler .NET programlama modeli hedeflemek için CLI programlama dili. Genel bilgiler hakkında C + +/ CLI dilinin bkz [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

Bu kılavuzda, temel C + oluşturmak için bir metin düzenleyicisi kullanın +/ CLI programını ve sonra komut satırında derleyin. (Kullanabileceğiniz kendi C + +/ CLI programını gösterilen bir yazmak yerine veya kullanabileceğiniz bir C + +/ CLI kod örneğini başka bir Yardım makalesi. Bu teknik oluşturmak ve UI öğesi içermeyen olan küçük modülleri test etmek için kullanışlıdır.)

> [!NOTE]
> C + derlemek için Visual Studio IDE kullanabilirsiniz +/ CLI programlar. Daha fazla bilgi için [izlenecek yol: Visual Studio'da CLR'yi hedefleyen C++ programını derleme](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md).

## <a name="prerequisites"></a>Önkoşullar

C++ dilinin temellerini anlamanız.

## <a name="compiling-a-ccli-program"></a>Derleme C + +/ CLI programını

Aşağıdaki adımlarda nasıl yapılandırılabileceğini C + +/ CLI konsol .NET Framework sınıfları kullanan bir uygulama.

Etkinleştirme derleme için C + +/ CLI, kullanmalıdır [/CLR](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. Visual C++ derleyicisi, MSIL kodu içeren bir .exe dosyası oluşturur — veya karma MSIL ve yerel kod — ve gerekli .NET Framework kitaplıkları bağlanır.

### <a name="to-compile-a-ccli-application-on-the-command-line"></a>Derlenecek C + +/ CLI uygulama komut satırında

1. Açık bir **Geliştirici komut istemi** penceresi. Ayrıntılı yönergeler için bkz: [bir geliştirici komut istemi penceresi açmak için](../build/building-on-the-command-line.md#developer_command_prompt).

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
[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br/>
[Derleyici Seçenekleri](../build/reference/compiler-options.md)
