---
title: 'Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: a1507a1a980dfd98a235b7456d73add955c02043
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213921"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma

Evrensel Windows Platformu (UWP) uygulamaları C++ için kullanmanın yanı sıra masaüstü uygulamalarında kullanılmak üzere temel klasik com bileşenleri oluşturmak için Windows çalışma zamanı Şablon kitaplığı (WRL) kullanabilirsiniz. COM bileşenlerinin oluşturulması için Windows Çalışma Zamanı C++ şablon KITAPLıĞı, ATL 'den daha az kod gerektirebilir. Windows Çalışma Zamanı C++ şablon KITAPLıĞıNıN desteklediği com alt kümesi hakkında daha fazla bilgi için, bkz. [Windows çalışma zamanı C++ şablon kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md).

Bu belgede, temel bir COM bileşeni oluşturmak C++ için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağı gösterilmektedir. Gereksinimlerinize en uygun dağıtım mekanizmasını kullanabilseniz de, bu belgede COM bileşenini bir masaüstü uygulamasından kaydetmek ve kullanmak için temel bir yol da gösterilmektedir.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Temel klasik bir COM C++ bileşeni oluşturmak için Windows çalışma zamanı şablon kitaplığını kullanmak için

1. Visual Studio 'da **boş bir çözüm** projesi oluşturun. Projeyi, örneğin `WRLClassicCOM`olarak adlandırın.

2. Çözüme bir **Win32 projesi** ekleyin. Projeyi, örneğin `CalculatorComponent`olarak adlandırın. **Uygulama ayarları** sekmesinde, **DLL**' yi seçin.

3. Projeye bir **MIDL dosya (. IDL)** dosyası ekleyin. Dosyayı adlandırın, örneğin `CalculatorComponent.idl`.

4. Bu kodu Hesaplatorcomponent. IDL öğesine ekleyin:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. Hesap \ bileşen. cpp ' de `CalculatorComponent` sınıfını tanımlayın. `CalculatorComponent` sınıfı [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md)öğesinden devralır. [Microsoft:: WRL:: RuntimeClassFlags\<ClassicCom >](runtimeclassflags-structure.md) , sınıfın [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable)değil, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) öğesinden türetildiğinden emin belirtir. (`IInspectable` yalnızca Windows Çalışma Zamanı uygulama bileşenleri için kullanılabilir.) `CoCreatableClass`, [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)gibi işlevlerle kullanılabilecek sınıf için bir fabrika oluşturur.

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. `dllmain.cpp`kodundaki kodu değiştirmek için aşağıdaki kodu kullanın. Bu dosya, DLL dışa aktarma işlevlerini tanımlar. Bu işlevler, modülün sınıf fabrikalarını yönetmek için [Microsoft:: WRL:: Module](module-class.md) sınıfını kullanır.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Projeye bir **modül tanımı dosyası (. def)** dosyası ekleyin. Dosyayı adlandırın, örneğin `CalculatorComponent.def`. Bu dosya bağlayıcıya aktarılacak işlevlerin adlarını verir.

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

1. COM bileşenini Windows kayıt defteri ile kaydedin. Bunu yapmak için bir kayıt girişleri dosyası oluşturun, `RegScript.reg`adlandırın ve aşağıdaki metni ekleyin. *\<dll-path >* dll 'nizin yoluyla değiştirin — örneğin, `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`.

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

3. Çözüme bir **Win32 konsol uygulaması** projesi ekleyin. Projeyi, örneğin `Calculator`olarak adlandırın.

4. `Calculator.cpp`içeriğini değiştirmek için bu kodu kullanın:

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Güçlü Programlama

Bu belge bir COM bileşeni yazmak ve COM özellikli teknolojinin kullanılabilmesini sağlamak için Windows Çalışma Zamanı C++ şablon kitaplığını kullanabilecebileceğinizi göstermek IÇIN standart com işlevlerini kullanır. COM ve diğer nesnelerin ömrünü C++ yönetmek için masaüstü uygulamanızda [Microsoft:: WRL:: comptr](comptr-class.md) gibi Windows çalışma zamanı Şablon kitaplığı türlerini de kullanabilirsiniz. Aşağıdaki kod, `ICalculatorComponent` işaretçisinin ömrünü C++ yönetmek için Windows çalışma zamanı şablon kitaplığını kullanır. `CoInitializeWrapper` sınıfı, COM kitaplığının serbest bırakılmış olduğunu garantileyen ve ayrıca COM kitaplığının kullanım ömrünün, `ComPtr` akıllı işaretçi nesnesinin kullanımını garanti eden bir RAMPASıDıR.

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
