---
title: 'İzlenecek Yol: Komut Satırında C++/CX Programı Derleme'
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 83369fc7b458463ea1f44a347bbcd0ca4eb32224
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078202"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında C++/CX Programı Derleme

> [!NOTE]
> Yeni UWP uygulamaları ve bileşenleri için, Windows çalışma zamanı API 'leri için standart bir c++ 17 dil projeksiyonu olan [ C++/wınrt](/windows/uwp/cpp-and-winrt-apis/)kullanmanızı öneririz. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlayacak şekilde tasarlanmıştır.

Microsoft C++ DERLEYICISI (MSVC), Windows çalışma zamanı C++ programlama modelini hedeflemekC++için ek tür ve işleçlere sahip bileşen uzantıları 'nı (/CX) destekler. Evrensel Windows Platformu (UWP C++) ve Windows Masaüstü için uygulama oluşturmak üzere/CX kullanabilirsiniz. Daha fazla bilgi için bkz. [bir C++/CX turu](https://msdn.microsoft.com/magazine/dn166929.aspx) ve [çalışma zamanı platformları için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

Bu kılavuzda, temel C++bir/CX programı oluşturmak ve ardından komut satırında derlemek için bir metin düzenleyicisi kullanın. (Gösterilen birini yazmak yerine kendi C++/CX programınızı kullanabilir ya da başka bir yardım makalesindeki bir C++/CX kod örneği kullanabilirsiniz. Bu teknik, Kullanıcı arabirimi öğeleri olmayan küçük modüller oluşturmak ve test etmek için kullanışlıdır.)

> [!NOTE]
> Ayrıca,/CX programlarını derlemek C++Için VISUAL Studio IDE 'yi de kullanabilirsiniz. IDE, komut satırında kullanılamayan tasarım, hata ayıklama, öykünme ve dağıtım desteği içerdiğinden, Evrensel Windows Platformu (UWP) uygulamaları oluşturmak için IDE 'yi kullanmanızı öneririz. Daha fazla bilgi için, bkz. [' de C++UWP uygulaması oluşturma ](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

## <a name="prerequisites"></a>Önkoşullar

C++ Dilin temellerini anlamış olursunuz.

## <a name="compiling-a-ccx-program"></a>Bir C++/CX programını derleme

/CX için C++derlemeyi etkinleştirmek üzere [/ZW](reference/zw-windows-runtime-compilation.md) derleyici seçeneğini kullanmanız gerekir. MSVC derleyicisi, Windows Çalışma Zamanı ve gerekli kitaplıkların bağlantılarını hedefleyen bir. exe dosyası oluşturur.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>Komut satırında bir C++/CX uygulaması derlemek için

1. **Geliştirici komut istemi** penceresini açın. ( **Başlangıç** penceresinde, **uygulamalar**' ı açın. Visual Studio sürümünüz altında **Visual Studio Araçları** klasörünü açın ve **Geliştirici komut istemi** kısayolunu seçin.) Geliştirici Komut İstemi bir pencerenin nasıl açılacağı hakkında daha fazla bilgi için, bkz. [MSVC araç takımını komut satırından kullanma](building-on-the-command-line.md).

   Bilgisayarın işletim sistemine ve yapılandırmasına bağlı olarak, kodu başarıyla derlemek için yönetici kimlik bilgileri gerekebilir. Komut Istemi penceresini yönetici olarak çalıştırmak için, **Geliştirici komut istemi** kısayol menüsünü açın ve ardından **yönetici olarak çalıştır**' ı seçin.

1. Komut isteminde **Notepad basiccx. cpp**yazın.

   Bir dosya oluşturmanız istendiğinde **Evet** ' i seçin.

1. Not defteri 'nde şu satırları girin:

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. Menü çubuğunda **dosya** > **Kaydet**' i seçin.

   Windows Çalışma Zamanı [Platform ad](../cppcx/platform-namespace-c-cx.md) alanı C++ ad alanını kullanan bir kaynak dosya oluşturdunuz.

1. Komut isteminde **cl/EHsc/ZW basiccx. cpp/LINK/SUBSYSTEM: Console**yazın. CL. exe derleyicisi, kaynak kodu bir. obj dosyasına derler ve ardından, basiccx. exe adlı bir yürütülebilir program oluşturmak için bağlayıcıyı çalıştırır. ( [/EHsc](reference/eh-exception-handling-model.md) derleyici seçeneği C++ özel durum işleme modelini belirtir ve [/Link](reference/link-pass-options-to-linker.md) bayrağı bir konsol uygulaması belirtir.)

1. Basiccx. exe programını çalıştırmak için komut isteminde **basiccx**yazın.

   Program bu metni görüntüler ve çıkar:

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
