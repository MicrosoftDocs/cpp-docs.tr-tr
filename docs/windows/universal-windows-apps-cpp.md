---
title: Evrensel Windows uygulamaları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ba556ee3803bb00f07032e0589209af2d32addf
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591759"
---
# <a name="universal-windows-apps-c"></a>Evrensel Windows Uygulamaları (C++)

Evrensel Windows Platformu (UWP) uygulamaları otomatik olarak farklı cihazlardaki farklı ekran boyutları için ayarlar içeriğin etrafında ortalanır basit kullanıcı arabirimlerini vurgulayan tasarım ilkeleri kümesini gerçekleştirir. XAML biçimlendirme ve yerel C++ kodunu arka plan kullanıcı arabirimini oluşturun. Ayrıca, diğer dillerde yazılmış UWP uygulamaları tarafından kullanılan bileşenler (DLL'ler) oluşturabilirsiniz. UWP uygulamaları için API yüzeyi, çok çeşitli işletim sistemi hizmetleri sağlayan, katsayıları iyi belirlenmiş bir kitaplıktır Windows Runtime ' dir.

> [!TIP]
> Windows 10 için Microsoft Store aracılığıyla dağıtımı için var olan masaüstü uygulamanızı paketlemek için Masaüstü Köprüsü uygulaması dönüştürücüyü kullanabilirsiniz. Daha fazla bilgi için [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-cwinrt"></a>UWP uygulamaları kullanmak C + +/ WinRT

C + +/ WinRT olan yeni, yalnızca üstbilgi kitaplık tabanlı C++ dil projeksiyon tamamen standart C++, C + aksine kullanan Windows çalışma zamanı için +/ CX uygulaması. C + +/ WinRT standart olmayan söz dizimi veya Microsoft dil uzantılarını kullanmaz ve yüksek oranda iyileştirilmiş çıktı oluşturmak için C++ Derleyici tam avantajlarından yararlanır. Daha fazla bilgi için [C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis). Giriş için C + +/ WinRT ve bir kod hızlı [giriş C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

## <a name="uwp-apps-that-use-ccx"></a>UWP uygulamaları kullanmak C + +/ CX

|||
|-|-|
|[Visual C++ Dil Başvurusu (C + +/ CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows çalışma zamanı API'ları C++ kullanımını kolaylaştıran ve özel durumlar temelinde hata işlemesini etkinleştirmek uzantıları kümesini açıklar.|
|[Uygulama ve Kitaplık Oluşturma (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|DLL'lerin ve C + erişilebilir statik kitaplıklar oluşturmayı açıklar +/ CX uygulama veya bileşen.|
|[Öğretici: bir UWP oluşturma "Hello, World" uygulaması C + +/ CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|UWP uygulama geliştirme C + temel konseptlerini tanıtan bir kılavuz +/ CX. |
|[Windows çalışma zamanı bileşenleri oluşturma C + +/ CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Diğer UWP uygulamaları ve bileşenlerinin kullanabileceği DLL'lerin nasıl oluşturulacağını açıklar.|
|[UWP oyunu programlama](/windows/uwp/gaming/)|DirectX ve C + kullanmayı açıklar +/ CX oyunlar oluşturmak için.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan UWP uygulamaları

Windows çalışma zamanı C++ Şablon kitaplığı, Windows çalışma zamanı özel durum gerektirmeyen bir ortamda erişebilmeniz için ISO C++ kod tarafından alt düzey COM arabirimleri sağlar. Çoğu durumda, C + kullanmanızı öneririz +/ WinRT ya da C + +/ CX UWP uygulama geliştirme için Windows çalışma zamanı C++ Şablon kitaplığı yerine. Windows çalışma zamanı C++ Şablon Kitaplığı hakkında daha fazla bilgi için bkz. [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>