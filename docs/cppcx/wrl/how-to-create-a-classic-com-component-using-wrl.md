---
title: 'Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma'
description: Masaüstü uygulamalarında kullanılmak üzere temel klasik COM bileşenleri oluşturmak için Windows Çalışma Zamanı C++ Şablon kitaplığı (WRL) kullanın.
ms.date: 10/23/2020
ms.topic: reference
ms.openlocfilehash: 417c2e4635b380717662fa0762062f0228659de4
ms.sourcegitcommit: bf54b407169900bb668c85a67b31dbc0f069fe65
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2020
ms.locfileid: "92497196"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma

Evrensel Windows Platformu (UWP) uygulamaları için kullanmanın yanı sıra masaüstü uygulamalarında kullanılmak üzere temel klasik COM bileşenleri oluşturmak için Windows Çalışma Zamanı C++ Şablon kitaplığı (WRL) kullanabilirsiniz. COM bileşenlerinin oluşturulması için Windows Çalışma Zamanı C++ Şablon kitaplığı, ATL 'den daha az kod gerektirebilir. Windows Çalışma Zamanı C++ şablon kitaplığının desteklediği COM alt kümesi hakkında daha fazla bilgi için bkz. [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md).

Bu belgede, temel bir COM bileşeni oluşturmak için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın nasıl kullanılacağı gösterilmektedir. Gereksinimlerinize en uygun dağıtım mekanizmasını kullanabilseniz de, bu belgede COM bileşenini bir masaüstü uygulamasından kaydetmek ve kullanmak için temel bir yol da gösterilmektedir.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Temel klasik bir COM bileşeni oluşturmak için Windows Çalışma Zamanı C++ şablon kitaplığını kullanmak için

1. Visual Studio 'da **boş bir çözüm** projesi oluşturun. Projeyi, örneğin, olarak adlandırın `WRLClassicCOM` .

2. Çözüme bir **Win32 projesi** ekleyin. Projeyi, örneğin, olarak adlandırın `CalculatorComponent` . **Uygulama ayarları** sekmesinde, **DLL**' yi seçin.

3. Projeye bir **MIDL dosya (. IDL)** dosyası ekleyin. Dosyayı, örneğin, olarak adlandırın `CalculatorComponent.idl` .

4. Bu kodu Hesaplatorcomponent. IDL öğesine ekleyin:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. Hesaplatorcomponent. cpp ' de sınıfı tanımlayın `CalculatorComponent` . `CalculatorComponent`Sınıfı [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md)öğesinden devralır. [Microsoft:: WRL:: RuntimeClassFlags \<ClassicCom> ](runtimeclassflags-structure.md) sınıfın [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable)değil, [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) öğesinden türetildiği belirtir. ( `IInspectable` yalnızca Windows çalışma zamanı uygulama bileşenleri için kullanılabilir.) `CoCreatableClass` [Cocreateınstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)gibi işlevlerle kullanılabilecek sınıf için bir fabrika oluşturur.

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. İçindeki kodu değiştirmek için aşağıdaki kodu kullanın `dllmain.cpp` . Bu dosya, DLL dışa aktarma işlevlerini tanımlar. Bu işlevler, modülün sınıf fabrikalarını yönetmek için [Microsoft:: WRL:: Module](module-class.md) sınıfını kullanır.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Projeye bir **modül tanımı dosyası (. def)** dosyası ekleyin. Dosyayı, örneğin, olarak adlandırın `CalculatorComponent.def` . Bu dosya bağlayıcıya aktarılacak işlevlerin adlarını verir. Projeniz için **Özellik sayfaları** iletişim kutusunu açın, ardından **yapılandırma özellikleri**  >  **bağlayıcı**  >  **girişi**altında **modül tanımı dosyası** özelliğini DEF dosyanıza ayarlayın.

8. Bu kodu Hesaplatorcomponent. def öğesine ekleyin:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Bağlayıcı satırına Runtimeobject. lib ekleyin. Nasıl yapılacağını öğrenmek için bkz. [ `.Lib` dosyalar bağlayıcı girişi olarak](../../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>COM bileşenini bir masaüstü uygulamasından kullanmak için

1. COM bileşenini Windows kayıt defteri ile kaydedin. Bunu yapmak için bir kayıt girişleri dosyası oluşturun, bu dosyayı adlandırın `RegScript.reg` ve aşağıdaki metni ekleyin. *\<dll-path>* DLL 'nizin yoluyla değiştirin — Örneğin, `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll` .

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

3. Çözüme bir **Win32 konsol uygulaması** projesi ekleyin. Projeyi, örneğin, olarak adlandırın `Calculator` .

4. İçeriğini değiştirmek için bu kodu kullanın `Calculator.cpp` :

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Güçlü Programlama

Bu belge bir COM bileşeni yazmak ve COM özellikli teknolojinin kullanılabilmesini sağlamak için Windows Çalışma Zamanı C++ şablon kitaplığını kullanabilecebileceğinizi göstermek için standart COM işlevlerini kullanır. COM ve diğer nesnelerin ömrünü yönetmek için masaüstü uygulamanızda [Microsoft:: WRL:: ComPtr](comptr-class.md) gibi Windows çalışma zamanı C++ Şablon kitaplığı türlerini de kullanabilirsiniz. Aşağıdaki kod, işaretçinin ömrünü yönetmek için Windows Çalışma Zamanı C++ şablon kitaplığını kullanır `ICalculatorComponent` . `CoInitializeWrapper`Bu sınıf, com kitaplığının serbest bırakılmış olduğunu garantileyen ve ayrıca com kitaplığının yaşam süresinin akıllı işaretçi nesnesinin kullanımını garanti eden BIR rampasıdır `ComPtr` .

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
