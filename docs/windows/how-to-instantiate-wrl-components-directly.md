---
title: 'Nasıl yapılır: doğrudan WRL bileşenlerinin örneğini | Microsoft Docs'
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
ms.openlocfilehash: 127a8430e79e7963ea94646f70179df2f30450ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-instantiate-wrl-components-directly"></a>Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma
Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanmayı öğrenin[Microsoft::WRL::Make](../windows/make-function.md) ve [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) işlevleri modülden bir bileşen örneği oluşturmak için Bu tanımlar.  
  
 Sınıf oluşturucuları veya diğer mekanizmaları gerekmediğinde bileşenleri doğrudan oluşturarak, ek yükü azaltabilir. Bir bileşen doğrudan hem Evrensel Windows platformu uygulamaları ve Masaüstü uygulamaları örneğini oluşturabilirsiniz.  
  
Windows çalışma zamanı C++ Şablon kitaplığı klasik COM bileşeni oluşturma ve bir dış masaüstü uygulaması oluşturmak için nasıl kullanılacağını öğrenmek için bkz: [nasıl yapılır: klasik COM bileşeni oluşturma](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 Bu belge, iki örnek gösterilmektedir. İlk örnek kullanan `Make` işlevi bir bileşen oluşturur. İkinci örnek kullanan `MakeAndInitialize` işlevi oluşturma sırasında başarısız olabilir bir bileşen oluşturur. (COM genellikle kullandığından `HRESULT` değerleri, hatalar, belirtmek için özel durumlar, yerine bir COM türü genellikle değil throw kendi oluşturucudan. `MakeAndInitialize` Yapım değişkenlerinin aracılığıyla doğrulamak bir bileşeni `RuntimeClassInitialize` yöntemi.) Örneklerin her ikisi de temel Günlükçü arabirimi tanımlayın ve iletilerini konsola yazar sınıfı tanımlayarak bu arabirimi uygulamalıdır.  
  
> [!IMPORTANT]
>  Kullanamazsınız `new` Windows çalışma zamanı C++ Şablon Kitaplığı bileşenleri örneği oluşturmak için işleç. Bu nedenle, her zaman kullanmanızı öneririz `Make` veya `MakeAndInitialize` bir bileşen doğrudan örneği oluşturmak için.  
  
### <a name="to-create-and-instantiate-a-basic-logger-component"></a>Oluşturma ve temel Günlükçü bileşen örneği  
  
1.  Visual Studio'da oluşturma bir **Win32 konsol uygulaması** projesi. Örneğin, proje adı `WRLLogger`.  
  
2.  Ekleme bir **MIDL dosya (.idl)** projeye dosya, dosya adı `ILogger.idl`ve ardından bu kodu ekleyin:  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  WRLLogger.cpp içeriğini değiştirmek için aşağıdaki kodu kullanın.  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>Temel Günlükçü bileşeni için yapım hatası işlemek için  
  
1.  Tanımını değiştirmek için aşağıdaki kodu kullanın `CConsoleWriter` sınıfı. Bu sürüm özel dize üye değişkeni ve geçersiz kılmalar tutan `RuntimeClass::RuntimeClassInitialize` yöntemi. `RuntimeClassInitialize` başarısız olur çağrısı `SHStrDup` başarısız olur.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  Tanımını değiştirmek için aşağıdaki kodu kullanın `wmain`. Bu sürüm kullanır `MakeAndInitialize` örneği oluşturmak için `CConsoleWriter` nesne ve denetimleri `HRESULT` sonucu.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::details::MakeAndInitialize](../windows/makeandinitialize-function.md)