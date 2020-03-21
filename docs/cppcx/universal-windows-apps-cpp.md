---
title: Evrensel Windows Uygulamaları (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.topic: overview
ms.openlocfilehash: cd90f76cf2ee9b4ca9cb2ceea970cd24b0bf24cf
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079907"
---
# <a name="universal-windows-apps-c"></a>Evrensel Windows Uygulamaları (C++)

Evrensel Windows Platformu (UWP), Windows için modern programlama arabirimidir. UWP sayesinde bir uygulama veya bileşeni bir kez yazıp herhangi bir Windows 10 cihazına dağıtırsınız. İçinde C++ bir bileşen yazabilir ve DIĞER bir UWP uyumlu dilde yazılmış uygulamalar bunu kullanabilir.

UWP belgelerinin çoğu, [Evrensel Windows platformu belgelerindeki](/windows/uwp/)Windows içerik ağacıdır. Başlangıç öğreticilerinin yanı sıra başvuru belgelerini de bulabilirsiniz.

Yeni UWP uygulamaları ve bileşenleri için, Windows çalışma zamanı API 'leri için yeni bir Standart c++ 17 dil projeksiyonu olan [ C++/wınrt](/windows/uwp/cpp-and-winrt-apis/)kullanmanızı öneririz. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlayacak şekilde tasarlanmıştır. C++/CX uygulamasının aksine. C++/Wınrt standart olmayan sözdizimi veya Microsoft dil uzantıları kullanmaz ve en iyi duruma getirilmiş çıkış oluşturmak için C++ derleyicinin tam avantajlarından yararlanır. Daha fazla bilgi için bkz. [/Wınrt 'ye C++giriş](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

Mevcut masaüstü uygulamanızı Microsoft Store aracılığıyla dağıtım için paketlemek üzere masaüstü Köprüsü Uygulama dönüştürücüyü kullanabilirsiniz. Daha fazla bilgi için bkz. [Centennial projesinde C++ ](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü köprüsünde](/windows/uwp/porting/desktop-to-uwp-root)Visual Runtime kullanma.

## <a name="uwp-apps-that-use-ccx"></a>/CX kullanan C++UWP uygulamaları

|||
|-|-|
|[C++/CX dil başvurusu](visual-c-language-reference-c-cx.md)|Windows Çalışma Zamanı API 'lerin kullanımını kolaylaştıran C++ ve özel durumlara dayalı hata işlemeyi etkinleştiren uzantıların kümesini açıklar.|
|[Uygulama ve Kitaplık Oluşturma (C++/CX)](building-apps-and-libraries-c-cx.md)|Bir C++/CX uygulamasından veya bileşeninden erişilebilen dll 'lerin ve statik kitaplıkların nasıl oluşturulacağını açıklar.|
|[Öğretici:/CX 'de C++UWP "Hello, World" uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|/Cx'de C++UWP uygulama geliştirmenin temel kavramlarını tanıtan bir anlatım. |
|[/CX 'de C++Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|Diğer UWP uygulamalarının ve bileşenlerinin tüketebileceği dll 'Lerin nasıl oluşturulacağını açıklar.|
|[UWP oyun programlama](/windows/uwp/gaming/)|Oyunları oluşturmak için DirectX ve C++/CX 'in nasıl kullanılacağını açıklar.|

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows Çalışma Zamanı C++ şablon kitaplığı (WRL) kullanan UWP uygulamaları

Windows Çalışma Zamanı C++ şablon KITAPLıĞı, ISO C++ kodunun özel durum içermeyen bir ortamda WINDOWS çalışma zamanı erişebileceği alt düzey COM arabirimlerini sağlar. Çoğu durumda, UWP uygulama geliştirme için Windows Çalışma Zamanı C++ C++ C++ şablon kitaplığı yerine/wınrt veya/CX kullanmanızı öneririz. Windows Çalışma Zamanı C++ şablon kitaplığı hakkında daha fazla bilgi için bkz [. C++ Windows çalışma zamanı Şablon kitaplığı (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++'ta Windows Programlamasına Genel Bakış](../windows/overview-of-windows-programming-in-cpp.md)<br/>