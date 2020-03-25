---
title: 'Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: f291e982d7f77c63821e5943a5867662ccd1b4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213908"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma

Windows Çalışma Zamanı C++ şablon kitaplığı (WRL)[MICROSOFT:: WRL:: Make](make-function.md) ve [Microsoft:: WR:D l:: makeanınvoınitialize](makeandinitialize-function.md) işlevlerini kullanarak onu tanımlayan modülden bir bileşen örneği oluşturma hakkında bilgi edinin.

Bileşenleri doğrudan örnekleyerek, sınıf fabrikaları veya diğer mekanizmaların gerekli olmadığı durumlarda ek yükü azaltabilirsiniz. Bir bileşeni doğrudan Evrensel Windows Platformu uygulamalarında ve masaüstü uygulamalarında bir bileşen örneği oluşturabilirsiniz.

Klasik bir COM bileşeni oluşturmak ve C++ bunu bir dış masaüstü uygulamasından örneklemek için Windows çalışma zamanı Şablon kitaplığı 'nı nasıl kullanacağınızı öğrenmek için bkz. [nasıl yapılır: klasik bir com bileşeni oluşturma](how-to-create-a-classic-com-component-using-wrl.md).

Bu belgede iki örnek gösterilmektedir. İlk örnek, bir bileşeni başlatmak için `Make` işlevini kullanır. İkinci örnek, oluşturma sırasında başarısız olan bir bileşeni başlatmak için `MakeAndInitialize` işlevini kullanır. (COM genellikle özel durumlar yerine HRESULT değerlerini kullandığından, hataları göstermek için COM türü genellikle oluşturucudan oluşturmaz. `MakeAndInitialize`, bir bileşenin oluşturma bağımsız değişkenlerini `RuntimeClassInitialize` yöntemi aracılığıyla doğrulamasını sağlar.) Her iki örnek de temel bir günlükçü arabirimini tanımlar ve konsola ileti yazan bir sınıf tanımlayarak bu arabirimi uygular.

> [!IMPORTANT]
> Windows Çalışma Zamanı C++ şablon kitaplığı bileşenlerini örneklemek için `new` işlecini kullanamazsınız. Bu nedenle, bir bileşeni doğrudan başlatmak için `Make` veya `MakeAndInitialize` her zaman kullanmanızı öneririz.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Temel bir günlükçü bileşeni oluşturmak ve başlatmak için

1. Visual Studio 'da bir **Win32 konsol uygulaması** projesi oluşturun. Projeyi (örneğin, *Wrlgünlükçü*) adlandırın.

2. Projeye bir **MIDL dosyası (. IDL)** dosyası ekleyin, dosyayı `ILogger.idl`olarak adlandırın ve ardından şu kodu ekleyin:

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. `WRLLogger.cpp`içeriğini değiştirmek için aşağıdaki kodu kullanın.

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Temel günlükçü bileşeni için oluşturma başarısızlığını işlemek için

1. `CConsoleWriter` sınıfının tanımını değiştirmek için aşağıdaki kodu kullanın. Bu sürüm özel bir dize üye değişkeni barındırır ve `RuntimeClass::RuntimeClassInitialize` yöntemini geçersiz kılar. `SHStrDup` çağrısı başarısız olursa `RuntimeClassInitialize` başarısız olur.

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. `wmain`tanımını değiştirmek için aşağıdaki kodu kullanın. Bu sürüm, `CConsoleWriter` nesnesinin örneğini oluşturmak ve HRESULT sonucunu kontrol etmek için `MakeAndInitialize` kullanır.

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft:: WRL:: Make](make-function.md)<br/>
[Microsoft:: WRL::D euçlar:: Makeanınvoınitialize](makeandinitialize-function.md)
