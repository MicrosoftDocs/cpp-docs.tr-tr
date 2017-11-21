---
title: "WRL sınıf kitaplığı proje şablonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea8f4609be920c03ff718ab79ba5a3693ec7d8e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="wrl-class-library-project-template"></a>WRL Sınıf Kitaplığı Proje Şablonu
Windows çalışma zamanı C++ Şablon kitaplığı (WRL) proje yazmak için Visual Studio kullanıyorsanız WRL sınıf kitaplığı proje şablonu yükleyerek, görevini büyük ölçüde kolaylaştırabilir.  
  
> [!NOTE]
>  Varolan projeyi Proje ayarlarını el ile güncelleştirmeniz varsa, bkz: [DLL'leri (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## <a name="download-the-wrl-project-template"></a>WRL proje şablonu indirme  
 Visual Studio şablon Windows çalışma zamanı C++ Şablon Kitaplığı projelerinde sağlamaz. Windows çalışma zamanı C++ Şablon kitaplığı ile Evrensel Windows platformu uygulamaları için temel sınıf kitaplığı oluşturan bir proje şablonu indirme bırakılır.  
  
#### <a name="to-download-the-wrl-project-template"></a>WRL proje şablonu karşıdan yüklemek için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni proje**.  
  
2.  Sol bölmesinde **yeni proje** iletişim kutusunda **çevrimiçi**ve ardından **şablonları**.  
  
3.  İçinde **arama çevrimiçi şablonlar** sağ üst köşedeki, türü kutusunda `WRL Class Library`. Şablon arama sonuçlarında görüntülendiğinde seçin **Tamam** düğmesi.  
  
4.  İçinde **yükleyip** iletişim kutusunda, lisans kabul etmesi durumunda koşulları, seçin **yüklemek** düğmesi.  
  
5.  Seçerek bir proje şablonu yüklendikten sonra oluşturma **dosya**, **yeni proje**ve ardından seçerek `WRLClassLibrary` şablonu. DLL projesi oluşturur.  
  
## <a name="examples-that-use-the-project-template"></a>Proje şablonu kullanma örnekleri  
 Okuma [izlenecek yol: bir temel Windows çalışma zamanı bileşeni oluşturma](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) Windows çalışma zamanı bileşeni oluşturmak için bu şablonu kullanan bir örnek.  
  
## <a name="what-the-project-template-provides"></a>Proje şablonu sağlar  
 Proje şablonu sağlar:  
  
-   sınıf uygulaması temel bir arabirim MIDL özniteliklerini bildirir .idl dosyası. Bir örnek verilmiştir.  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   sınıf uygulamasını tanımlayan bir .cpp dosyası. Bir örnek verilmiştir.  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     [RuntimeClass](../windows/runtimeclass-class.md) temel sınıf modülündeki tüm nesnelerin genel başvuru yönetilmesine yardımcı olur ve yöntemlerinin bildirir [IUnknown](http://msdn.microsoft.com/en-us/33f1d79a-33fc-4ce5-a372-e08bda378332) ve [Iınspectable](http://msdn.microsoft.com/en-us/0657e51f-d4c0-46c6-927d-b01e54b6846c) arabirimleri. [Inspectableclass](../windows/inspectableclass-macro.md) makrosu uygulayan `IUnknown` ve `IInspectable`. [ActivatableClass](../windows/activatableclass-macros.md) makrosu sınıfının örnekleri oluşturan bir sınıf üreteci oluşturur.  
  
-   Kitaplık tanımlar module.cpp adlı bir dosyaya dışa aktarır `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory`, ve `DllGetClassObject`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)