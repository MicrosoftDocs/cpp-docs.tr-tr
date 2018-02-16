---
title: "Evrensel Windows uygulamaları (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a293f833de7bc575209089362bcaf146d074684b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="universal-windows-apps-c"></a>Evrensel Windows Uygulamaları (C++)
Evrensel Windows Platformu (UWP) uygulamaları, farklı ekran boyutlarına farklı aygıtlar için otomatik olarak ayarlar içerik kalmaz basit kullanıcı arabirimleri vurgulamak tasarım ilkeleri kümesi gerçekleştirir. XAML biçimlendirme ve kod arkasında yerel C++ içinde kullanıcı arabirimini oluşturun. Diğer dillerde yazılmış UWP uygulamaları tarafından kullanılabilecek (dll) bileşenleri de oluşturabilirsiniz. UWP uygulamalar için API yüzeyi çok çeşitli işletim sistemi hizmetleri sağlayan bir iyi faktörlere göre kitaplık Windows Runtime ' dir.  

> [!TIP]  
> Windows 10 için Microsoft Store aracılığıyla dağıtımı için varolan Masaüstü uygulamanız paketlemek için masaüstü uygulaması dönüştürücü kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü uygulamanız için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile Getir](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).
  
  
## <a name="uwp-apps-that-use-ccx"></a>C + kullanan UWP uygulamaları +/ CX  
  
|||  
|-|-|  
|[Visual C++ Dil Başvurusu (C + +/ CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows çalışma zamanı API'leri C++ tüketimini basitleştirmek ve özel durumlara dayalıdır hata işleme etkinleştiren uzantıları açıklar.|  
|[Uygulama ve Kitaplık Oluşturma (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|DLL'ler ve C + erişilebilir statik kitaplıklar oluşturmayı açıklar +/ CX uygulama veya bileşen.|  
|[Öğretici: C++ kullanarak ilk UWP uygulamanızı oluşturma](https://docs.microsoft.com/en-us/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C++ UWP uygulama geliştirme temel kavramlarını tanıtır bir kılavuz. (Henüz Windows 10 UWP geliştirme için güncelleştirilmiştir.)|  
|[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Diğer UWP uygulamaları ve bileşenleri tüketebileceği DLL'leri oluşturmayı açıklar.|  
|[Oyunlar geliştirme](https://docs.microsoft.com/en-us/windows/uwp/gaming/)|DirectX ve C++ oyun oluşturmak için nasıl kullanılacağını açıklar.|  
  
## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan UWP uygulamaları 
 Windows çalışma zamanı C++ Şablon kitaplığı ISO C++ kod bir özel durum Serbest ortamında Windows çalışma zamanı erişebilirsiniz alt düzey COM arabirimleri sağlar. Çoğu durumda, C + kullanmanızı öneririz +/ CX UWP uygulama geliştirme için Windows çalışma zamanı C++ Şablon kitaplığı yerine. Windows çalışma zamanı C++ Şablon Kitaplığı hakkında daha fazla bilgi için bkz: [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++](../visual-cpp-in-visual-studio.md)

