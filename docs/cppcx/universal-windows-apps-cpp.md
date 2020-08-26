---
title: Evrensel Windows Uygulamaları (C++)
ms.date: 03/30/2018
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
ms.topic: overview
ms.openlocfilehash: 45d02a5ab923ee46da97d78a1e5ceb2f4313352a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841681"
---
# <a name="universal-windows-apps-c"></a>Evrensel Windows Uygulamaları (C++)

Evrensel Windows Platformu (UWP), Windows için modern programlama arabirimidir. UWP sayesinde bir uygulama veya bileşeni bir kez yazıp herhangi bir Windows 10 cihazına dağıtırsınız. C++ ' da bir bileşen yazabilir ve diğer bir UWP uyumlu dilde yazılmış uygulamalar bunu kullanabilir.

UWP belgelerinin çoğu, [Evrensel Windows platformu belgelerindeki](/windows/uwp/)Windows içerik ağacıdır. Başlangıç öğreticilerinin yanı sıra başvuru belgelerini de bulabilirsiniz.

Yeni UWP uygulamaları ve bileşenleri için, Windows Çalışma Zamanı API 'Leri için yeni bir standart C++ 17 dil projeksiyonu olan [C++/Wınrt](/windows/uwp/cpp-and-winrt-apis/)kullanmanızı öneririz. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlamak için tasarlanmıştır. C++/CX uygulamasının aksine, C++/Wınrt standart olmayan sözdizimi veya Microsoft dil uzantıları kullanmaz ve en iyi duruma getirilmiş çıkış oluşturmak için C++ derleyicisinden tam olarak yararlanır. Daha fazla bilgi için bkz. [C++/Wınrt 'ye giriş](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt).

Mevcut masaüstü uygulamanızı Microsoft Store aracılığıyla dağıtım için paketlemek üzere masaüstü Köprüsü Uygulama dönüştürücüyü kullanabilirsiniz. Daha fazla bilgi için bkz. [Centennial projesinde](https://devblogs.microsoft.com/cppblog/using-visual-c-runtime-in-centennial-project/) ve [masaüstü köprüsünde](/windows/uwp/porting/desktop-to-uwp-root)Visual C++ çalışma zamanı kullanma.

## <a name="uwp-apps-that-use-ccx"></a>C++/CX kullanan UWP uygulamaları

[C++/CX dil başvurusu](visual-c-language-reference-c-cx.md)\
Windows Çalışma Zamanı API 'lerin C++ tüketimini basitleştiren ve özel durumlara dayalı hata işlemeyi etkinleştiren uzantıların kümesini açıklar.

[Uygulama ve kitaplıklar oluşturma (C++/CX)](building-apps-and-libraries-c-cx.md)\
C++/CX uygulamasından veya bileşeninden erişilebilen dll 'Lerin ve statik kitaplıkların nasıl oluşturulacağını açıklar.

[Öğretici: C++/CX ' te UWP "Merhaba, Dünya" uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)\
C++/CX'DE UWP uygulama geliştirmenin temel kavramlarını tanıtan bir anlatım.

[C++/CX içinde Windows Çalışma Zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)\
Diğer UWP uygulamalarının ve bileşenlerinin tüketebileceği dll 'Lerin nasıl oluşturulacağını açıklar.

[UWP oyun programlama](/windows/uwp/gaming/)\
Oyunları oluşturmak için DirectX ve C++/CX ' nın nasıl kullanılacağını açıklar.

## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows Çalışma Zamanı C++ Şablon kitaplığı (WRL) kullanan UWP uygulamaları

Windows Çalışma Zamanı C++ Şablon kitaplığı, ISO C++ kodunun özel durum içermeyen bir ortamda Windows Çalışma Zamanı erişebileceği alt düzey COM arabirimlerini sağlar. Çoğu durumda, UWP uygulama geliştirme için C++ Şablon kitaplığı Windows Çalışma Zamanı yerine C++/Wınrt veya C++/CX kullanmanızı öneririz. Windows Çalışma Zamanı C++ Şablon Kitaplığı hakkında daha fazla bilgi için bkz. [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](wrl/windows-runtime-cpp-template-library-wrl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)<br/>
[C++ ' da Windows programlamaya genel bakış](../windows/overview-of-windows-programming-in-cpp.md)<br/>
