---
description: 'Daha fazla bilgi edinin: nasıl yapılır: doğrudan WRL bileşenleri örneği oluşturma'
title: 'Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: 424b3ec70921de9558fd8c5035e96b2fe4d58f7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249899"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma

Windows Çalışma Zamanı C++ Şablon kitaplığı (WRL)[Microsoft:: WRL:: Make](make-function.md) ve [Microsoft:: WR:D l:: makeanınvoınitialize](makeandinitialize-function.md) işlevlerini kullanarak onu tanımlayan modülden bir bileşen örneğini oluşturmayı öğrenin.

Bileşenleri doğrudan örnekleyerek, sınıf fabrikaları veya diğer mekanizmaların gerekli olmadığı durumlarda ek yükü azaltabilirsiniz. Bir bileşeni doğrudan Evrensel Windows Platformu uygulamalarında ve masaüstü uygulamalarında bir bileşen örneği oluşturabilirsiniz.

Klasik bir COM bileşeni oluşturmak ve bunu bir dış masaüstü uygulamasından örneklemek için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nı nasıl kullanacağınızı öğrenmek için bkz. [nasıl yapılır: Klasik BIR com bileşeni oluşturma](how-to-create-a-classic-com-component-using-wrl.md).

Bu belgede iki örnek gösterilmektedir. İlk örnek, `Make` bir bileşeni örneklemek için işlevini kullanır. İkinci örnek, `MakeAndInitialize` oluşturma sırasında başarısız olan bir bileşenin örneğini oluşturmak için işlevini kullanır. (COM genellikle özel durumlar yerine HRESULT değerlerini kullandığından, hataları göstermek için COM türü genellikle oluşturucudan oluşturmaz. `MakeAndInitialize` bir bileşenin, oluşturma bağımsız değişkenlerini yöntemi aracılığıyla doğrulamasını sağlar `RuntimeClassInitialize` .) Her iki örnek de temel bir günlükçü arabirimini tanımlar ve konsola ileti yazan bir sınıf tanımlayarak bu arabirimi uygular.

> [!IMPORTANT]
> `new`C++ Şablon kitaplığı bileşenlerini Windows çalışma zamanı örneğini oluşturmak için işlecini kullanamazsınız. Bu nedenle, her zaman `Make` `MakeAndInitialize` doğrudan bir bileşen örneğini oluşturmak için veya kullanmanız önerilir.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Temel bir günlükçü bileşeni oluşturmak ve başlatmak için

1. Visual Studio 'da bir **Win32 konsol uygulaması** projesi oluşturun. Projeyi (örneğin, *Wrlgünlükçü*) adlandırın.

2. Projeye bir **MIDL dosyası (. IDL)** dosyası ekleyin, dosyayı adlandırın `ILogger.idl` ve ardından şu kodu ekleyin:

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. İçeriğini değiştirmek için aşağıdaki kodu kullanın `WRLLogger.cpp` .

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Temel günlükçü bileşeni için oluşturma başarısızlığını işlemek için

1. Sınıfının tanımını değiştirmek için aşağıdaki kodu kullanın `CConsoleWriter` . Bu sürüm özel bir dize üye değişkeni barındırır ve yöntemi geçersiz kılar `RuntimeClass::RuntimeClassInitialize` . `RuntimeClassInitialize` çağrısı başarısız olursa başarısız olur `SHStrDup` .

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. Tanımını değiştirmek için aşağıdaki kodu kullanın `wmain` . Bu sürüm `MakeAndInitialize` , nesnenin örneğini oluşturmak `CConsoleWriter` ve hresult sonucunu kontrol etmek için kullanılır.

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft:: WRL:: Make](make-function.md)<br/>
[Microsoft:: WRL::D euçlar:: Makeanınvoınitialize](makeandinitialize-function.md)
