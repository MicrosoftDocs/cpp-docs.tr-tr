---
title: 'İzlenecek Yol: Komut Satırında C++/CX Programı Derleme'
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 8dcd27ca8fff826f33ee8bd752cd32f2d44d3691
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836718"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>İzlenecek Yol: Komut Satırında C++/CX Programı Derleme

> [!NOTE]
> Yeni UWP uygulamaları ve bileşenleri için, Windows Çalışma Zamanı API 'Leri için standart bir C++ 17 dil projeksiyonu olan [c++/Wınrt](/windows/uwp/cpp-and-winrt-apis/)kullanmanızı öneririz. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlamak için tasarlanmıştır.

Microsoft C++ derleyicisi (MSVC), Windows Çalışma Zamanı programlama modelini hedeflemek için ek tür ve işleçlere sahip C++ Bileşen Uzantıları 'nı (C++/CX) destekler. C++/CX kullanarak Evrensel Windows Platformu (UWP) ve Windows Masaüstü için uygulamalar oluşturabilirsiniz. Daha fazla bilgi için bkz. [çalışma zamanı platformları Için](../extensions/component-extensions-for-runtime-platforms.md) [C++/CX](/archive/msdn-magazine/2013/april/component-extensions-a-tour-of-c-cx) ve bileşen uzantıları turu.

Bu kılavuzda, temel bir C++/CX programı oluşturmak ve ardından komut satırında derlemek için bir metin düzenleyicisi kullanın. (Gösterilen birini yazmak yerine kendi C++/CX programınızı kullanabilir ya da başka bir yardım makalesindeki C++/CX kod örneğini kullanabilirsiniz. Bu teknik, Kullanıcı arabirimi öğeleri olmayan küçük modüller oluşturmak ve test etmek için kullanışlıdır.)

> [!NOTE]
> C++/CX programlarını derlemek için Visual Studio IDE 'yi de kullanabilirsiniz. IDE, komut satırında kullanılamayan tasarım, hata ayıklama, öykünme ve dağıtım desteği içerdiğinden, Evrensel Windows Platformu (UWP) uygulamaları oluşturmak için IDE 'yi kullanmanızı öneririz. Daha fazla bilgi için bkz. [C++ ' da UWP uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

## <a name="prerequisites"></a>Önkoşullar

C++ dilinin temellerini anlamış olursunuz.

## <a name="compiling-a-ccx-program"></a>C++/CX programını derleme

C++/CX için derlemeyi etkinleştirmek üzere [/ZW](reference/zw-windows-runtime-compilation.md) derleyici seçeneğini kullanmanız gerekir. MSVC derleyicisi, Windows Çalışma Zamanı ve gerekli kitaplıkların bağlantılarını hedefleyen bir. exe dosyası oluşturur.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>Komut satırında C++/CX uygulaması derlemek için

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

1. Menü çubuğunda **Dosya**  >  **Kaydet**' i seçin.

   Windows Çalışma Zamanı [Platform ad](../cppcx/platform-namespace-c-cx.md) alanı ad alanını kullanan bir C++ kaynak dosyası oluşturdunuz.

1. Komut isteminde **cl/EHsc/ZW basiccx. cpp/LINK/SUBSYSTEM: Console**yazın. cl.exe derleyicisi, kaynak kodu bir. obj dosyasına derler ve sonra basiccx.exe adlı yürütülebilir bir program oluşturmak için bağlayıcıyı çalıştırır. ( [/EHsc](reference/eh-exception-handling-model.md) derleyici seçeneği C++ özel durum işleme modelini belirtir ve [/Link](reference/link-pass-options-to-linker.md) bayrağı bir konsol uygulaması belirtir.)

1. basiccx.exe programını çalıştırmak için komut isteminde **basiccx**yazın.

   Program bu metni görüntüler ve çıkar:

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC derleyici seçenekleri](reference/compiler-options.md)
