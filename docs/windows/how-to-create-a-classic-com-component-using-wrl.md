---
title: 'Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: 025f369b002abcdbe2091a6cae4b38894f370863
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437849"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma

Windows çalışma zamanı C++ Şablon kitaplığı (WRL), Evrensel Windows Platformu (UWP) uygulamaları için kullanmanın yanı sıra masaüstü uygulamalarında kullanmak için temel klasik COM bileşenleri oluşturmak için kullanabilirsiniz. COM bileşenleri oluşturmak için Windows çalışma zamanı C++ Şablon Kitaplığı daha az kod ATL gerektirebilir. Windows çalışma zamanı C++ Şablon kitaplığı destekleyen COM alt hakkında daha fazla bilgi için bkz [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

Bu belge, temel bir COM bileşeni oluşturmak için Windows çalışma zamanı C++ Şablon kitaplığı kullanma işlemi gösterilmektedir. Gereksinimlerinize en uygun dağıtım mekanizması kullanabilirsiniz, ancak bu belge ayrıca kaydetme ve bir masaüstü uygulamasından COM bileşeni kullanmak için basit bir yol gösterir.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Temel klasik COM bileşeni oluşturmak için Windows çalışma zamanı C++ Şablon kitaplığı kullanmak için

1. Visual Studio'da oluşturma bir **boş çözüm** proje. Örneğin, proje adını `WRLClassicCOM`.

2. Ekleme bir **Win32 projesi** çözüm. Örneğin, proje adını `CalculatorComponent`. Üzerinde **uygulama ayarları** sekmesinde **DLL**.

3. Ekleme bir **Midl dosyası (.idl)** projeye dosya. Örneğin, dosya adını `CalculatorComponent.idl`.

4. CalculatorComponent.idl için şu kodu ekleyin:

   [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. CalculatorComponent.cpp içinde tanımlayın `CalculatorComponent` sınıfı. `CalculatorComponent` Sınıfının devraldığı [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md). [Microsoft::WRL::RuntimeClassFlags\<ClassicCom >](../windows/runtimeclassflags-structure.md) öğesinden türetilen sınıfın belirtir [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) değil [Iınspectable](https://msdn.microsoft.com/library/br205821). (`IInspectable` yalnızca Windows çalışma zamanı uygulama bileşenleri için kullanılabilir.) `CoCreatableClass` işlevlerinde aşağıdaki gibi kullanılabilir sınıf için bir Üreteç oluşturur [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

   [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. Kodu değiştirmek için aşağıdaki kodu kullanın `dllmain.cpp`. Bu dosya, DLL dışarı aktarma işlevleri tanımlar. Bu işlevleri [Microsoft::WRL::Module](../windows/module-class.md) sınıf üreteçlerini modülüyle ilgili yönetmek için sınıf.

   [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Ekleme bir **modül tanım dosyasını (.def)** projeye dosya. Örneğin, dosya adını `CalculatorComponent.def`. Bu dosya, bağlayıcı dışarı aktarılacak işlevlerin adlarını sağlar.

8. CalculatorComponent.def için şu kodu ekleyin:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Runtimeobject.lib bağlayıcı satırına ekleyin. Bilgi edinmek için bkz. nasıl [. Bağlayıcı girişi dosyaları lib](../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Bir masaüstü uygulamasından COM bileşeni kullanma

1. COM bileşeni, Windows kayıt defteri ile kaydedin. Bunu yapmak için bir kayıt girdileri dosyası oluşturun, adlandırın `RegScript.reg`, aşağıdaki metni ekleyin. Değiştirin  *\<dll yolu >* dll yolu ile — Örneğin, `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`.

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

2. RegScript.reg çalıştırın veya projenizin ekleme **derleme sonrası olay**. Daha fazla bilgi için [derleme öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).

3. Ekleme bir **Win32 konsol uygulaması** çözüme bir proje. Örneğin, proje adını `Calculator`.

4. İçeriğini değiştirmek için bu kodu kullanın `Calculator.cpp`:

   [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Güçlü Programlama

Bu belge, bir COM bileşeni yazmak ve herhangi bir COM özellikli teknoloji kullanılabilir hale getirmek için Windows çalışma zamanı C++ Şablon kitaplığı kullanabileceğini göstermeyi standart COM işlevleri kullanır. Windows çalışma zamanı C++ Şablon kitaplığı türleri gibi kullanabilirsiniz [Microsoft::wrl:: comptr](../windows/comptr-class.md) COM ve diğer nesnelerin ömrünü yönetmek için Masaüstü uygulamanızda. Aşağıdaki kod, ömrünü yönetmek için Windows çalışma zamanı C++ Şablon kitaplığı kullanan `ICalculatorComponent` işaretçi. `CoInitializeWrapper` COM kitaplığı serbest bırakılır ve de COM kitaplığının kullanım ömrü outlives olduğunu garanti garanti eden bir RAII sarmalayıcı bir sınıftır `ComPtr` akıllı işaretçi nesnesinin.

[!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)