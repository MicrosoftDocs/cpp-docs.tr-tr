---
title: 'Nasıl yapılır: doğrudan WRL bileşenlerinin örneğini oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05bd0ab8e402c1d3a926b46bf1df54a084fc9f93
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595181"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma

Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanmayı öğrenin[Microsoft::wrl:: Make](../windows/make-function.md) ve [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) işlevleri modülden bir bileşen örneği oluşturmak için Bu tanımlar.

Sınıf oluşturucular veya başka mekanizmalar ihtiyacınız kalmadığında bileşenleri doğrudan örnekleme, ek yükü azaltabilir. Bir bileşen doğrudan her iki Evrensel Windows platformu uygulamaları ve masaüstü uygulamalarında örneği oluşturabilir.

Klasik COM bileşeni oluşturma ve dış bir masaüstü uygulaması oluşturmak için Windows çalışma zamanı C++ Şablon kitaplığı kullanmayı öğrenmek için bkz: [nasıl yapılır: klasik COM bileşeni oluşturma](../windows/how-to-create-a-classic-com-component-using-wrl.md).

Bu belge, iki örnek gösterir. İlk örnekte `Make` bir bileşen örneği için işlevi. İkinci örnekte `MakeAndInitialize` işlev yapım sırasında başarısız olabilir bir bileşen oluşturur. (COM yerine özel durumlar genellikle HRESULT değerlerini kullandığından, hatalar, belirtmek için bir COM tür genellikle kendi bir oluşturucudan oluşturmaz. `MakeAndInitialize` Yapı bağımsız değişkenlerinden biri aracılığıyla doğrulamak bir bileşen sağlar `RuntimeClassInitialize` yöntemi.) Örneklerin her ikisi de temel bir Günlükçü arabirimi tanımlayın ve iletilerini konsola bir sınıf tanımlayarak bu arabirimi uygulayın.

> [!IMPORTANT]
> Kullanamazsınız **yeni** Windows çalışma zamanı C++ Şablon kitaplığı bileşenlerinin örneğini oluşturma için işleci. Bu nedenle, her zaman kullanmanızı öneririz `Make` veya `MakeAndInitialize` doğrudan bir bileşeni örneği.

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Oluşturmak ve temel bir Günlükçü bileşeni oluşturmak için

1. Visual Studio'da oluşturma bir **Win32 konsol uygulaması** proje. Örneğin, proje adını *WRLLogger*.

2. Ekleme bir **Midl dosyası (.idl)** projeye dosya, dosya adı `ILogger.idl`ve ardından bu kodu ekleyin:

   [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. İçeriğini değiştirmek için aşağıdaki kodu kullanın `WRLLogger.cpp`.

   [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Temel bir Günlükçü bileşeni için yapı hatayı işlemek için

1. Tanımı değiştirmek için aşağıdaki kodu kullanın `CConsoleWriter` sınıfı. Bu sürüm özel dize üye değişkeni ve geçersiz kılmaları tutan `RuntimeClass::RuntimeClassInitialize` yöntemi. `RuntimeClassInitialize` başarısız çağrı `SHStrDup` başarısız olur.

   [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. Tanımı değiştirmek için aşağıdaki kodu kullanın `wmain`. Bu sürümü kullanan `MakeAndInitialize` örneklemek için `CConsoleWriter` nesne ve HRESULT sonucu denetler.

   [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)  
[Microsoft::wrl:: Make](../windows/make-function.md)  
[Microsoft::WRL::details::MakeAndInitialize](../windows/makeandinitialize-function.md)