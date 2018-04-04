---
title: Evrensel Windows uygulamaları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology:
- cpp-windows
ms.topic: article
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 142a9c8e7c25dc9eee559f973f4cbd61337581c0
ms.sourcegitcommit: 78e5e5cdbafd29e2a6ccf68d4cce215136952907
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="universal-windows-apps-c"></a>Evrensel Windows Uygulamaları (C++)

Evrensel Windows Platformu (UWP) uygulamaları, farklı ekran boyutlarına farklı aygıtlar için otomatik olarak ayarlar içerik kalmaz basit kullanıcı arabirimleri vurgulamak tasarım ilkeleri kümesi gerçekleştirir. XAML biçimlendirme ve kod arkasında yerel C++ içinde kullanıcı arabirimini oluşturun. Diğer dillerde yazılmış UWP uygulamaları tarafından kullanılabilecek (dll) bileşenleri de oluşturabilirsiniz. UWP uygulamalar için API yüzeyi çok çeşitli işletim sistemi hizmetleri sağlayan bir iyi faktörlere göre kitaplık Windows Runtime ' dir.

> [!TIP]  
> Windows 10 için Microsoft Store aracılığıyla dağıtımı için varolan Masaüstü uygulamanız paketlemek için Masaüstü köprüsü uygulama dönüştürücü kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-cwinrt"></a>C + kullanan UWP uygulamaları +/ WinRT

C + +/ WinRT olan yeni, yalnızca üstbilgi kitaplığı tabanlı C++ dili projeksiyon aksine C + tamamen standart C++ kullanan Windows çalışma zamanı için +/ CX uygulama. C + +/ WinRT değil standart sözdizimi ve Microsoft dil uzantıları ve onu yüksek oranda iyileştirilmiş çıktı oluşturmak için C++ derleyicisi yararlanır. Daha fazla bilgi için bkz: [C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis). Giriş için C + +/ bkz: WinRT ve bir kod Hızlı Başlangıç [giriş C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

## <a name="uwp-apps-that-use-ccx"></a>C + kullanan UWP uygulamaları +/ CX

|||
|-|-|
|[Visual C++ Dil Başvurusu (C + +/ CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows çalışma zamanı API'leri C++ tüketimini basitleştirmek ve özel durumlara dayalıdır hata işleme etkinleştiren uzantıları açıklar.|
|[Uygulama ve Kitaplık Oluşturma (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|DLL'ler ve C + erişilebilir statik kitaplıklar oluşturmayı açıklar +/ CX uygulama veya bileşen.|
|[Öğretici: bir UWP oluşturma "Hello, World" uygulama C + +/ CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|UWP uygulama geliştirme C + temel kavramlarını tanıtır bir kılavuz +/ CX. |
|[Windows çalışma zamanı bileşenleri oluşturma C + +/ CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Diğer UWP uygulamaları ve bileşenleri tüketebileceği DLL'leri oluşturmayı açıklar.|
|[UWP oyun programlama](/windows/uwp/gaming/)|DirectX ve C + kullanmayı açıklar +/ CX oyunlar oluşturun.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan UWP uygulamaları

Windows çalışma zamanı C++ Şablon kitaplığı ISO C++ kod bir özel durum Serbest ortamında Windows çalışma zamanı erişebilirsiniz alt düzey COM arabirimleri sağlar. Çoğu durumda, C + kullanmanızı öneririz +/ WinRT veya C + +/ CX UWP uygulama geliştirme için Windows çalışma zamanı C++ Şablon kitaplığı yerine. Windows çalışma zamanı C++ Şablon Kitaplığı hakkında daha fazla bilgi için bkz: [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
