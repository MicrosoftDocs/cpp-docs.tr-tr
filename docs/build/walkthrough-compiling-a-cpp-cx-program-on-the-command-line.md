---
title: 'İzlenecek yol: Derleme C + +/ CX programı komut satırında'
ms.date: 09/24/2018
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 099bef402d22abc12a31f105f63e5405c65a1d82
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766072"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>İzlenecek yol: Derleme C + +/ CX programı komut satırında

Windows çalışma zamanını hedefleyen ve onları komut satırında derleme Visual C++ programlar oluşturabilirsiniz. Visual C++, Visual C++ bileşen uzantıları destekler (C + +/ CX), Windows çalışma zamanı programlama modeli hedeflemek için ek türleri ve işleçler sahip. Kullanabileceğiniz C + +/ CX için evrensel Windows Platformu (UWP), Windows Phone 8.1 ve Windows Masaüstü uygulamaları oluşturmak için. Daha fazla bilgi için [bir tur, c + +/ CX](https://msdn.microsoft.com/magazine/dn166929.aspx) ve [çalışma zamanı platformları için bileşen uzantıları](../extensions/component-extensions-for-runtime-platforms.md).

Bu kılavuzda, temel C + oluşturmak için bir metin düzenleyicisi kullanın +/ CX programı ve sonra komut satırında derleyin. (Kullanabileceğiniz kendi C + +/ CX programı gösterilen bir yazmak yerine veya kullanabileceğiniz bir C + +/ CX kod örneğini başka bir Yardım makalesi. Bu teknik oluşturmak ve UI öğesi içermeyen olan küçük modülleri test etmek için kullanışlıdır.)

> [!NOTE]
> C + derlemek için Visual Studio IDE kullanabilirsiniz +/ CX programlar. IDE tasarım, hata ayıklama, öykünme ve dağıtım desteği, komut satırında kullanılamaz içerdiğinden, Evrensel Windows Platformu (UWP) uygulamaları oluşturmak için IDE'yi kullanmanızı öneririz. Daha fazla bilgi için [c++'ta bir UWP uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

## <a name="prerequisites"></a>Önkoşullar

C++ dilinin temellerini anlamanız.

## <a name="compiling-a-ccx-program"></a>Derleme C + +/ CX programı

Etkinleştirme derleme için C + +/ CX, kullanmalıdır [/ZW](reference/zw-windows-runtime-compilation.md) derleyici seçeneği. MSVC derleyicisi, Windows çalışma zamanını hedefleyen ve gerekli kitaplıklara bağlantılar bir .exe dosyası oluşturur.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>Derlenecek C + +/ CX uygulama komut satırında

1. Açık bir **Geliştirici komut istemi** penceresi. (Üzerinde **Başlat** penceresini açık **uygulamaları**. Açık **Visual Studio Araçları** klasörü altında Visual Studio sürümünüz ve ardından **Geliştirici komut istemi** kısayol.) Bir geliştirici komut istemi penceresi açmak hakkında daha fazla bilgi için bkz. [komut satırından MSVC araç takımı kullanın](building-on-the-command-line.md).

   Yönetici kimlik bilgileri başarıyla bilgisayarın işletim sistemi ve yapılandırmasına bağlı olarak Kodu derlemek için gerekebilir. Komut İstemi penceresini yönetici olarak çalıştırmak için kısayol menüsünü açın **Geliştirici komut istemi** seçip **yönetici olarak çalıştır**.

1. Komut isteminde girin **not defteri basiccx.cpp**.

   Seçin **Evet** istenirse bir dosya oluşturmak için.

1. Not Defteri'nde şu satırı girin:

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. Menü çubuğunda, **dosya** > **Kaydet**.

   Windows çalışma zamanı kullanan bir Visual C++ kaynak dosyasını, oluşturduğunuz [Platform ad alanı](../cppcx/platform-namespace-c-cx.md) ad alanı.

1. Komut isteminde girin **cl/ehsc /ZW basiccx.cpp/Link/Subsystem: Console**. Cl.exe derleyicisi, kaynak kodunu bir .obj dosyasına derler ve basiccx.exe adlı yürütülebilir bir program oluşturmak için bağlayıcı çalıştırır. ( [/Ehsc](reference/eh-exception-handling-model.md) derleyici seçeneği C++ özel durum işleme modelini belirtir ve [/link](reference/link-pass-options-to-linker.md) bayrağı, bir konsol uygulaması belirtir.)

1. Komut isteminde basiccx.exe programı çalıştırmak için girin **basiccx**.

   Program bu metni görüntüler ve çıkar:

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)<br/>
[MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)
