---
title: Görsel C++ dil başvurusu (C++/CX)
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: 0b2d344f9889d5669164cd917ba569b5f35d83a5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498420"
---
# <a name="visual-c-language-reference-ccx"></a>Görsel C++ dil başvurusu (C++/CX)

C++/CX, modern C++bir şekilde olabildiğince yakın bir C++ şekilde Windows Uygulamaları ve Windows çalışma zamanı bileşenleri oluşturulmasını etkinleştiren dile yönelik bir dizi uzantıdır. Visual C++ C#, Visual Basic ve JavaScript ve Windows çalışma zamanı destekleyen diğer dillerde kolayca etkileşim kuran yerel koda Windows Uygulamaları ve bileşenleri yazmak için/CX kullanın. Ham COM arabirimlerine veya olağanüstü olmayan koda doğrudan erişim gerektiren bu nadir durumlarda [Windows çalışma zamanı C++ şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanabilirsiniz.

> [!NOTE]
> **/Wınrt,/CX C++için önerilen alternatiftir. [ C++](/windows/uwp/cpp-and-winrt-apis/index) Bu, 1803 sürümünün en son Windows 10 SDK 'sında kullanılabilen Windows Çalışma Zamanı API 'Leri için yeni, standart bir C++ 17 dil projeksiyonudur. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlamak için tasarlanmıştır.
>
> /Wınrt ile C++, standartlara uyumlu c++ 17 derleyicisini kullanarak Windows çalışma zamanı API 'leri hem tüketin hem de yazabilirsiniz. C++/Wınrt genellikle daha iyi gerçekleştirir ve Windows Çalışma Zamanı diğer dil seçeneklerinden daha küçük ikili dosyalar üretir. /CX ve WRL 'yi C++desteklemeye devam edeceğiz, ancak yeni uygulamaların/Winrtı kullanmasını C++önemle tavsiye ederiz. Daha fazla bilgi için bkz [ C++./wınrt](/windows/uwp/cpp-and-winrt-apis/index).

/CX kullanarak C++şunları oluşturabilirsiniz:

- C++Kullanıcı arabirimini tanımlamak ve yerel yığını kullanmak için XAML kullanan Evrensel Windows Platformu (UWP) uygulamalar. Daha fazla bilgi için bkz. [(UWP) içinde C++ bir "Hello World" uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- C++JavaScript tabanlı Windows uygulamaları tarafından tüketilen bileşenleri Windows Çalışma Zamanı. Daha fazla bilgi için bkz. [içinde C++Windows çalışma zamanı bileşenleri oluşturma ](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows DirectX oyunları ve grafik yoğun uygulamalar. Daha fazla bilgi için bkz. [DirectX ile basit BIR UWP oyunu oluşturma](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game).

## <a name="related-articles"></a>İlgili makaleler

|||
|-|-|
|[Hızlı Başvuru](../cppcx/quick-reference-c-cx.md)|/Cxiçin C++anahtar sözcükler ve işleçler tablosu.|
|[Tür Sistemi](../cppcx/type-system-c-cx.md)|Temel C++/CX türlerini ve programlama yapılarını ve Windows çalışma zamanı türlerini kullanmak ve oluşturmak C++için/CX kullanmayı açıklar.|
|[Uygulama ve kitaplık oluşturma](../cppcx/building-apps-and-libraries-c-cx.md)|Uygulamaları oluşturmak ve statik kitaplıklara ve DLL 'lere bağlanmak için IDE 'nin nasıl kullanılacağını açıklar.|
|[Diğer Dillerle Birlikte Çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)|/CX kullanılarak C++yazılan bileşenlerin JavaScript, herhangi bir yönetilen dil veya Windows çalışma zamanı C++ şablon kitaplığı ile yazılmış bileşenlerle nasıl kullanılabileceğini açıklar.|
|[İş Parçacığı Oluşturma ve Hazırlama](../cppcx/threading-and-marshaling-c-cx.md)|Oluşturduğunuz bileşenlerin iş parçacığı oluşturma ve sıralama davranışının nasıl kullanılacağını açıklar.|
|[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)|Varsayılan ad alanı, Platform ad alanı, Platform:: Collections ve ilgili ad alanları için başvuru belgeleri.|
|[Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows Çalışma Zamanı uygulamalarda kullanılmak üzere kullanılamayan CRT işlevlerini listeler.|
|[Windows 10 uygulamaları ile çalışmaya başlama](/windows/uwp/get-started/)|Windows 10 uygulamaları ve daha fazla bilgi için bağlantılar hakkında üst düzey rehberlik sağlar.|
|[C++/CX bölüm 0/ \[n\]: Giriş](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX Bölüm 1/ \[n\]: Basit bir sınıf](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX Bölüm 2/ \[n\]: Bu tür bir HATS](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++/CX Bölüm 3/ \[n\]: Yapım aşamasında](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C++/CX Bölüm 4/ \[n\]: Statik üye Işlevleri](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|/Cxüzerinde C++ C++bir giriş görsel blog serisi.|
