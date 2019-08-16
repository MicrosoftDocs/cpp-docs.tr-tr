---
title: 'Nasıl yapılır: WRL kullanarak klasik bir COM bileşeni oluşturma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: ec762b07caa30ce9aa6f4c67f84bb66ae884a7cf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498382"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Nasıl yapılır: WRL kullanarak klasik bir COM bileşeni oluşturma

Evrensel Windows Platformu (UWP) uygulamaları C++ için kullanmanın yanı sıra masaüstü uygulamalarında kullanılmak üzere temel klasik com bileşenleri oluşturmak için Windows çalışma zamanı Şablon kitaplığı (WRL) kullanabilirsiniz. COM bileşenlerinin oluşturulması için Windows Çalışma Zamanı C++ şablon KITAPLıĞı, ATL 'den daha az kod gerektirebilir. Windows Çalışma Zamanı C++ şablon KITAPLıĞıNıN desteklediği com alt kümesi hakkında daha fazla bilgi için, bkz. [Windows çalışma zamanı C++ şablon kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md).

Bu belgede, temel bir COM bileşeni oluşturmak C++ için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağı gösterilmektedir. Gereksinimlerinize en uygun dağıtım mekanizmasını kullanabilseniz de, bu belgede COM bileşenini bir masaüstü uygulamasından kaydetmek ve kullanmak için temel bir yol da gösterilmektedir.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Temel klasik bir COM C++ bileşeni oluşturmak için Windows çalışma zamanı şablon kitaplığını kullanmak için

1. Visual Studio 'da **boş bir çözüm** projesi oluşturun. Projeyi, örneğin, olarak `WRLClassicCOM`adlandırın.

2. Çözüme bir **Win32 projesi** ekleyin. Projeyi, örneğin, olarak `CalculatorComponent`adlandırın. **Uygulama ayarları** sekmesinde, **DLL**' yi seçin.

3. Projeye bir **MIDL dosya (. IDL)** dosyası ekleyin. Dosyayı, örneğin, olarak `CalculatorComponent.idl`adlandırın.

4. Bu kodu Hesaplatorcomponent. IDL öğesine ekleyin:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. Hesaplatorcomponent. cpp ' de `CalculatorComponent` sınıfı tanımlayın. Sınıfı Microsoft [:: WRL:: RuntimeClass](runtimeclass-class.md)öğesinden devralır. `CalculatorComponent` [Microsoft:: WRL:: RuntimeClassFlags\<sınıfıcom >](runtimeclassflags-structure.md) , sınıfın, [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable)değil, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) öğesinden türetildiğinden emin belirtir. (`IInspectable` yalnızca Windows çalışma zamanı uygulama bileşenleri için kullanılabilir.) CoCreateInstance gibi işlevlerle kullanılabilecek sınıf için bir fabrika oluşturur. [](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) `CoCreatableClass`

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. İçindeki `dllmain.cpp`kodu değiştirmek için aşağıdaki kodu kullanın. Bu dosya, DLL dışa aktarma işlevlerini tanımlar. Bu işlevler, modülün sınıf fabrikalarını yönetmek için [Microsoft:: WRL:: Module](module-class.md) sınıfını kullanır.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Projeye bir **modül tanımı dosyası (. def)** dosyası ekleyin. Dosyayı, örneğin, olarak `CalculatorComponent.def`adlandırın. Bu dosya bağlayıcıya aktarılacak işlevlerin adlarını verir.

8. Bu kodu Hesaplatorcomponent. def öğesine ekleyin:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Bağlayıcı satırına Runtimeobject. lib ekleyin. Hakkında bilgi edinmek için bkz [. Bağlayıcı girişi olarak lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>COM bileşenini bir masaüstü uygulamasından kullanmak için

1. COM bileşenini Windows kayıt defteri ile kaydedin. Bunu yapmak için bir kayıt girişleri dosyası oluşturun, bu `RegScript.reg`dosyayı adlandırın ve aşağıdaki metni ekleyin. *\<Dll-Path >* yerine dll 'nizin yolunu koyun — Örneğin,. `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. RegScript. reg dosyasını çalıştırın veya projenizin **Derleme sonrası olayına**ekleyin. Daha fazla bilgi için bkz. [derleme öncesi olay/oluşturma sonrası olay komut satırı Iletişim kutusu](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).

3. Çözüme bir **Win32 konsol uygulaması** projesi ekleyin. Projeyi, örneğin, olarak `Calculator`adlandırın.

4. İçeriğini değiştirmek için bu kodu kullanın `Calculator.cpp`:

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Güçlü Programlama

Bu belge bir COM bileşeni yazmak ve COM özellikli teknolojinin kullanılabilmesini sağlamak için Windows Çalışma Zamanı C++ şablon kitaplığını kullanabilecebileceğinizi göstermek IÇIN standart com işlevlerini kullanır. COM ve diğer nesnelerin ömrünü C++ yönetmek için masaüstü uygulamanızda [Microsoft:: WRL:: comptr](comptr-class.md) gibi Windows çalışma zamanı Şablon kitaplığı türlerini de kullanabilirsiniz. Aşağıdaki kod, `ICalculatorComponent` işaretçinin ömrünü yönetmek C++ için Windows çalışma zamanı şablon kitaplığını kullanır. Bu sınıf, com kitaplığının serbest bırakılmış olduğunu garantileyen ve ayrıca com kitaplığının `ComPtr` yaşam süresinin akıllı işaretçi nesnesinin kullanımını garanti eden bir rampasıdır. `CoInitializeWrapper`

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)