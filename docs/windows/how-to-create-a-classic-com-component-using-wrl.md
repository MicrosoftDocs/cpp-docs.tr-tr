---
title: "Nasıl yapılır: WRL kullanarak klasik COM bileşeni oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e33eaebd49343c5c03b097eaf75d4745c7aaeac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Nasıl yapılır: WRL Kullanarak Klasik COM Bileşeni Oluşturma
Masaüstü uygulamalarında kullanmak için temel klasik COM bileşenleri için kullanmaya ek olarak oluşturmak için Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanabilirsiniz [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] uygulamalar. COM bileşenlerini oluşturulmasında Windows çalışma zamanı C++ Şablon kitaplığı ATL daha az kod gerektirebilir Windows çalışma zamanı C++ Şablon kitaplığı destekleyen COM alt hakkında daha fazla bilgi için bkz: [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
 Bu belge Windows çalışma zamanı C++ Şablon kitaplığı temel bir COM bileşeni oluşturma için nasıl kullanılacağını gösterir. Gereksinimlerine en uygun dağıtım mekanizması kullanabilmenize karşın, bu belgede ayrıca kaydetme ve COM bileşeninin düzgün bir masaüstü uygulaması'ndan kullanmak için temel bir yolunu gösterir.  
  
### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Windows çalışma zamanı C++ Şablon kitaplığı temel klasik COM bileşeni oluşturmak üzere kullanmak için  
  
1.  Visual Studio'da oluşturma bir **boş çözüm** projesi. Örneğin, proje adı `WRLClassicCOM`.  
  
2.  Ekleme bir **Win32 Proje** çözüme. Örneğin, proje adı `CalculatorComponent`. Üzerinde **uygulama ayarları** sekmesine **DLL**.  
  
3.  Ekleme bir **MIDL dosya (.idl)** projesine dosyasını. Örneğin, dosya adı `CalculatorComponent.idl`.  
  
4.  CalculatorComponent.idl için bu kodu ekleyin:  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  CalculatorComponent.cpp içinde tanımlayın `CalculatorComponent` sınıfı. `CalculatorComponent` Sınıfının devraldığı [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md). [Microsoft::WRL::RuntimeClassFlags\<ClassicCom >](../windows/runtimeclassflags-structure.md) sınıfı öğesinden türetilen belirtir [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) ve [Iınspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx). (`IInspectable` yalnızca kullanılabilir [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] uygulama bileşenleri.) `CoCreatableClass` işlevleriyle gibi kullanılabilir sınıfı için bir üreteci oluşturur [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx).  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  DllMain.cpp'yi kodda değiştirmek için aşağıdaki kodu kullanın. Bu dosya, DLL dışarı aktarma işlevleri tanımlar. Bu işlevleri kullanma [Microsoft::WRL::Module](../windows/module-class.md) modülü için sınıf oluşturucuları yönetmek için sınıf.  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  Ekleme bir **modül tanım dosyasını (.def)** projesine dosyasını. Örneğin, dosya adı `CalculatorComponent.def`. Bu dosya dışarı aktarılacak olan işlevlerin adlarını bağlayıcı sağlar.  
  
8.  CalculatorComponent.def için bu kodu ekleyin:  
  
    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE  
    ```

9. Runtimeobject.lib bağlayıcı satırı ekleyin. Bilgi edinmek için bkz. nasıl [. Bağlayıcı girişi dosyaları lib](../build/reference/dot-lib-files-as-linker-input.md).  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Bir masaüstü uygulamasının COM bileşeni kullanmak için  
  
1.  COM bileşeninin Windows kayıt defteri ile kaydedin. Bunu yapmak için bir kayıt girdileri dosyası oluşturun, adlandırın `RegScript.reg`ve aşağıdaki metni ekleyin. Değiştir  *\<dll yolu >* DLL yolu ile — Örneğin, `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`.  
  
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
  
2.  RegScript.reg çalıştırabilir veya, projenizin ekleyebilirsiniz **oluşturma sonrası olay**. Daha fazla bilgi için bkz: [oluşturma öncesi olay/derleme sonrası olay komut satırı iletişim kutusu](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).  
  
3.  Ekleme bir **Win32 konsol uygulaması** çözüme proje. Örneğin, proje adı `Calculator`.  
  
4.  Calculator.cpp içeriğini değiştirmek için bu kodu kullanın:  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Bu belge, Windows çalışma zamanı C++ Şablon kitaplığı bir COM bileşeni yazmak ve tüm COM etkin teknoloji kullanılabilir hale getirmek için kullanabileceğiniz göstermek için standart COM işlevleri kullanır. Windows çalışma zamanı C++ Şablon kitaplığı türleri gibi kullanabilir [Microsoft::wrl:: comptr](../windows/comptr-class.md) COM ve diğer nesneleri ömrünü yönetmek için Masaüstü uygulamanızda. Aşağıdaki kod ömrünü yönetmek için Windows çalışma zamanı C++ Şablon kitaplığı kullanır `ICalculatorComponent` işaretçi. `CoInitializeWrapper` COM kitaplığı serbest bırakılmaz ve COM kitaplığı ömrü outlives garanti eder garanti RAII sarmalayıcı sınıftır `ComPtr` akıllı işaretçi nesnesi.  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)