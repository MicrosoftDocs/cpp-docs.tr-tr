---
title: "İzlenecek yol: WRL kullanarak temel Windows çalışma zamanı bileşeni oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 6e3f0986-7905-4f94-90e5-22c2ebfc8cd0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0c57e6b8ffb501ea4c6b75429bab88bbe5dc93eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="walkthrough-creating-a-basic-windows-runtime-component-using-wrl"></a>İzlenecek Yol: WRL Kullanarak Temel Windows Çalışma Zamanı Bileşeni Oluşturma
Bu belge Windows çalışma zamanı C++ Şablon kitaplığı (WRL) temel Windows çalışma zamanı bileşeni oluşturma için nasıl kullanılacağını gösterir. Bileşen iki sayı ekleyen ve sonuç asal olduğunda bir olay başlatır. Bu belge, ayrıca JavaScript kullanan bir evrensel Windows platformu uygulama bileşeninden kullanmayı gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
-   İle deneyimi [Windows çalışma zamanı](http://msdn.microsoft.com/library/windows/apps/br211377.aspx).  
  
-   COM deneyimi  
  
### <a name="to-create-a-basic-windows-runtime-component-that-adds-two-numbers"></a>İki sayı ekleyen bir temel Windows çalışma zamanı bileşeni oluşturma  
  
1.  Visual Studio'da bir Visual C++ oluşturma `WRLClassLibrary` projesi. Belge [sınıf kitaplığı proje şablonu](../windows/wrl-class-library-project-template.md) bu şablonu indirme açıklar. Proje adı `Contoso`.  
  
2.  Contoso.cpp ve Contoso.idl "Makinesiyle" "WinRTClass" tüm örneklerini değiştirin.  
  
3.  Contoso.idl içinde eklemek `Add` yönteme `ICalculator` arabirimi.  
  
     [!code-cpp[wrl-basic-component#1](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_1.idl)]  
  
4.  Contoso.cpp içinde eklemek `Add` yönteme `public` bölümünü `Calculator` sınıfı.  
  
     [!code-cpp[wrl-basic-component#2](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_2.cpp)]  
  
    > [!IMPORTANT]
    >  Bir COM bileşeni oluşturmakta olduğunuz çünkü kullanmayı unutmayın `__stdcall` çağırma.  
  
     Kullanmanızı öneririz `_Out_` ve işlev parametrelerinin nasıl kullandığını tanımlamak için diğer kaynak ek açıklama dili (SAL) ek açıklamaları. SAL ek açıklamaları dönüş değerleri de açıklanmaktadır. SAL ek açıklamaları çalışabilirsiniz [C/C++ kod analizi aracı](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) olası kusurları C ve C++ kaynak kodu bulmak için. Bellek ve kaynak sızıntılarını ve null işaretçiye veya aracı tarafından raporlanan genel kodlama hatalarını arabellek taşmaları, başlatılmamış bellek içerir.  
  
### <a name="to-use-the-component-from-a-universal-windows-platform-app-that-uses-javascript"></a>JavaScript kullanan bir evrensel Windows platformu uygulama bileşeninden kullanmak için  
  
1.  Visual Studio'da yeni bir JavaScript ekleme `Blank App` için proje `Contoso` çözümü. Proje adı `CalculatorJS`.  
  
2.  İçinde `CalculatorJS` proje, bir başvuru ekleyin `Contoso` projesi.  
  
3.  Default.HTML içinde Değiştir `body` bu kullanıcı Arabirimi öğeleri bölümle:  
  
     [!code-html[wrl-basic-component#3](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_3.html)]  
  
4.  Default.js içinde uygulamak `OnClick` işlevi.  
  
     [!code-javascript[wrl-basic-component#4](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_4.js)]  
  
    > [!NOTE]
    >  JavaScript'te, yöntemi adının ilk harfi standart adlandırma kuralları eşleştirmek için çok küçük değiştirilir.  
  
### <a name="to-add-an-event-that-fires-when-a-prime-number-is-calculated"></a>Asal sayı hesaplandığında tetiklenen bir olay eklemek için  
  
1.  Bildirimi önce Contoso.idl içinde `ICalculator`, temsilci türünü tanımlayın `PrimeNumberEvent`, sağlayan bir `int` bağımsız değişkeni.  
  
     [!code-cpp[wrl-basic-component#5](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_5.idl)]  
  
     Kullandığınızda `delegate` anahtar sözcüğü, MIDL derleyici oluşturur içeren bir arabirim bir `Invoke` bu temsilcinin imza eşleşen yöntemi. Bu örnekte, oluşturulan dosya Contoso_h.h tanımlar `IPrimeNumberEvent` bu yordamda daha sonra kullanılan arabirim.  
  
     [!code-cpp[wrl-basic-component#13](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_6.cpp)]  
  
2.  İçinde `ICalculator` arabirim, tanımlayın `PrimeNumberFound` olay. `eventadd` Ve `eventremove` öznitelikleri belirtin tüketicisi `ICalculator` arabirimi hem abone olamaz ve bu olayından aboneliği.  
  
     [!code-cpp[wrl-basic-component#6](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_7.idl)]  
  
3.  Contoso.cpp içinde eklemek bir `private` [Microsoft::WRL::EventSource](../windows/eventsource-class.md) olay aboneleri yönetmek ve olay işleyicisi çağırma için üye değişkeni.  
  
     [!code-cpp[wrl-basic-component#7](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_8.cpp)]  
  
4.  Contoso.cpp içinde uygulamak `add_PrimeNumberFound` ve `remove_PrimeNumberFound` yöntemleri.  
  
     [!code-cpp[wrl-basic-component#8](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_9.cpp)]  
  
### <a name="to-raise-the-event-when-a-prime-number-is-calculated"></a>Asal sayı hesaplandığında olay yükseltmek için  
  
1.  Contoso.cpp içinde eklemek `IsPrime` yönteme `private` bölümünü `Calculator` sınıfı.  
  
     [!code-cpp[wrl-basic-component#12](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_10.cpp)]  
  
2.  Değiştirme `Calculator`'s `Add` çağrılacak yöntem [Microsoft::WRL::EventSource::InvokeAll](../windows/eventsource-invokeall-method.md) asal sayı hesaplandığında yöntemi.  
  
     [!code-cpp[wrl-basic-component#11](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_11.cpp)]  
  
### <a name="to-handle-the-event-from-javascript"></a>JavaScript olayından işlemek için  
  
1.  Default.HTML içinde değişiklik `body` asal sayılar içeren bir metin alanı eklemek için bölüm.  
  
     [!code-html[wrl-basic-component#9](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_12.html)]  
  
2.  Default.js içinde değişiklik `Add` işlemek için işlev `PrimeNumberFound` olay. Olay işleyicisi asal sayı önceki adımı tarafından tanımlandı metin alanı ekler.  
  
     [!code-javascript[wrl-basic-component#10](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_13.js)]  
  
    > [!NOTE]
    >  JavaScript, olay adları için küçük değiştirilir ve "açık" standart adlandırma kurallarına uyan etkileşimlidir.  
  
 Aşağıdaki çizimde temel hesaplayıcı uygulama gösterir.  
  
 ![JavaScript kullanarak temel hesaplayıcı uygulama](../windows/media/wrl_basic_component.png "WRL_Basic_Component")  
  
## <a name="next-steps"></a>Sonraki Adımlar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Sınıf kitaplığı proje şablonu](../windows/wrl-class-library-project-template.md)   
 [C/C++ kod analizi aracı](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)