---
title: Evrensel Windows Uygulamaları (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.openlocfilehash: fbd5366ee52dfe32baef9458a82c16914666699e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392069"
---
# <a name="universal-windows-apps-c"></a>Evrensel Windows Uygulamaları (C++)

Evrensel Windows Platformu (UWP) Windows için modern programlama arabirimidir. UWP ile bir uygulama veya bileşen bir kez yazın ve tüm Windows 10 cihazlarda dağıtın. Bir bileşen C++ olarak yazabilir ve diğer bir UWP uyumlu dilde yazılmış uygulamalar için bunu kullanabilirsiniz.

UWP belgeleri çoğunu olan Windows içerik ağacını [Evrensel Windows platformu belgeleri](/windows/uwp/). Başlangıç öğreticileri bulabiliriz başvuru belgeleri. 

Yeni UWP uygulamaları ve bileşenleri için kullanmanızı öneririz [ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/), yeni standart C ++ 17 dil projeksiyon Windows Runtime API'ları için. C++/ WinRT Windows 10 SDK sürüm 1803 ileriye doğru kullanıma sunulmuştur. C++/ WinRT tamamen üstbilgi dosyalarında uygulanır ve modern Windows API ile birinci sınıf erişim sağlamak için tasarlanmıştır. Farklı C++/CX uygulaması. C++/ WinRT standart olmayan söz dizimi veya Microsoft dil uzantılarını kullanmaz ve tam avantajlarından yararlanır C++ yüksek oranda iyileştirilmiş çıktı oluşturmak için derleyici. Daha fazla bilgi için [giriş C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

Microsoft Store aracılığıyla dağıtımı için var olan masaüstü uygulamanızı paketlemek için Masaüstü Köprüsü uygulaması dönüştürücüyü kullanabilirsiniz. Daha fazla bilgi için [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="uwp-apps-that-use-ccx"></a>Kullanan UWP uygulamaları C++/CX

|||
|-|-|
|[Görsel C++ dil başvurusu (C++/CX)](visual-c-language-reference-c-cx.md)|Windows çalışma zamanı API'ları C++ kullanımını kolaylaştıran ve özel durumlar temelinde hata işlemesini etkinleştirmek uzantıları kümesini açıklar.|
|[Uygulama ve Kitaplık Oluşturma (C++/CX)](building-apps-and-libraries-c-cx.md)|DLL'lerin ve C + erişilebilir statik kitaplıklar oluşturmayı açıklar +/ CX uygulama veya bileşen.|
|[Öğretici: Bir UWP oluşturma "Hello, World" uygulamasında C++/CX](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|UWP uygulama geliştirme C + temel konseptlerini tanıtan bir kılavuz +/ CX. |
|[Windows çalışma zamanı bileşenleri oluşturma C++/CX](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Diğer UWP uygulamaları ve bileşenlerinin kullanabileceği DLL'lerin nasıl oluşturulacağını açıklar.|
|[UWP oyunu programlama](/windows/uwp/gaming/)|DirectX ve C + kullanmayı açıklar +/ CX oyunlar oluşturmak için.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanan UWP uygulamaları

Windows çalışma zamanı C++ Şablon kitaplığı, Windows çalışma zamanı özel durum gerektirmeyen bir ortamda erişebilmeniz için ISO C++ kod tarafından alt düzey COM arabirimleri sağlar. Çoğu durumda, biz kullanmanızı öneririz. C++/WinRT veya C++Windows çalışma zamanı yerine /CX C++ UWP uygulama geliştirme için Şablon kitaplığı. Windows çalışma zamanı C++ Şablon Kitaplığı hakkında daha fazla bilgi için bkz. [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++'ta Windows Programlamasına Genel Bakış](../windows/overview-of-windows-programming-in-cpp.md)<br/>