---
title: C++/CX dil başvurusu
ms.date: 09/15/2017
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
ms.openlocfilehash: 4f3816280630a6a061eb037a33367ef4e9d90375
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403861"
---
# <a name="ccx-language-reference"></a>C++/CX dil başvurusu

C++/CX, C++ diline yönelik bir uzantılar kümesidir ve bu, modern C++ ' ta olabildiğince yakın bir şekilde Windows Uygulamaları ve Windows Çalışma Zamanı bileşenleri oluşturulmasını sağlar. Visual C#, Visual Basic ve JavaScript ile kolayca etkileşim kuran yerel koda Windows Uygulamaları ve bileşenleri yazmak için C++/CX kullanın ve Windows Çalışma Zamanı destekleyen diğer diller vardır. Ham COM arabirimlerine veya olağanüstü olmayan koda doğrudan erişim gerektiren bu nadir durumlarda [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanabilirsiniz.

> [!NOTE]
> **/Wınrt,/CX C++için önerilen alternatiftir. [ C++](/windows/uwp/cpp-and-winrt-apis/index)** Bu, 1803 sürümünün en son Windows 10 SDK 'sında kullanılabilen Windows Çalışma Zamanı API 'Leri için yeni, standart bir C++ 17 dil projeksiyonudur. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlamak için tasarlanmıştır.
>
> C++/Wınrt ile, standartlara uyumlu C++ 17 derleyicisini kullanarak Windows Çalışma Zamanı API 'Leri hem tüketin hem de yazabilirsiniz. C++/Wınrt genellikle daha iyi çalışır ve Windows Çalışma Zamanı için diğer dil seçeneklerinden daha küçük ikili dosyalar üretir. C++/CX ve WRL 'yi desteklemeye devam edeceğiz, ancak yeni uygulamaların C++/Wınrtrtı kullanmasını önemle öneririz. Daha fazla bilgi için bkz. [C++/Wınrt](/windows/uwp/cpp-and-winrt-apis/index).

C++/CX kullanarak şunları oluşturabilirsiniz:

- Kullanıcı arabirimini tanımlamak ve yerel yığını kullanmak için XAML kullanan C++ Evrensel Windows Platformu (UWP) uygulamaları. Daha fazla bilgi için bkz. [C++ ' da bir "Hello World" uygulaması oluşturma (UWP)](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- C++ Windows Çalışma Zamanı JavaScript tabanlı Windows uygulamaları tarafından kullanılabilecek bileşenler. Daha fazla bilgi için bkz. [C++ ' de Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows DirectX oyunları ve grafik yoğun uygulamalar. Daha fazla bilgi için bkz. [DirectX ile basit BIR UWP oyunu oluşturma](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game).

## <a name="related-articles"></a>İlgili makaleler:

| Bağlantı | Açıklama |
|--|--|
| [Hızlı başvuru](../cppcx/quick-reference-c-cx.md) | C++/CXIÇIN anahtar sözcük ve işleçler tablosu. |
| [Tür sistemi](../cppcx/type-system-c-cx.md) | Temel C++/CX türlerini ve programlama yapılarını ve Windows Çalışma Zamanı türlerini kullanmak ve oluşturmak için C++/CX kullanmayı açıklar. |
| [Uygulama ve kitaplık oluşturma](../cppcx/building-apps-and-libraries-c-cx.md) | Uygulamaları oluşturmak ve statik kitaplıklara ve DLL 'lere bağlanmak için IDE 'nin nasıl kullanılacağını açıklar. |
| [Diğer dillerle birlikte çalışma](../cppcx/interoperating-with-other-languages-c-cx.md) | C++/CX kullanılarak yazılan bileşenlerin JavaScript, herhangi bir yönetilen dil veya Windows Çalışma Zamanı C++ Şablon kitaplığı ile yazılmış bileşenlerle nasıl kullanılabileceğini açıklar. |
| [İş parçacığı oluşturma ve sıralama](../cppcx/threading-and-marshaling-c-cx.md) | Oluşturduğunuz bileşenlerin iş parçacığı oluşturma ve sıralama davranışının nasıl kullanılacağını açıklar. |
| [Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md) | Varsayılan ad alanı, Platform ad alanı, Platform:: Collections ve ilgili ad alanları için başvuru belgeleri. |
| [Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) | Windows Çalışma Zamanı uygulamalarda kullanılmak üzere kullanılamayan CRT işlevlerini listeler. |
| [Windows 10 uygulamaları ile çalışmaya başlama](/windows/uwp/get-started/) | Windows 10 uygulamaları ve daha fazla bilgi için bağlantılar hakkında üst düzey rehberlik sağlar. |
| [C++/CX bölüm 0/ \[ n \] : bir giriş](https://devblogs.microsoft.com/cppblog/ccx-part-0-of-n-an-introduction/)<br /><br />[C++/CX Bölüm 1/ \[ n \] : basit bir sınıf](https://devblogs.microsoft.com/cppblog/ccx-part-1-of-n-a-simple-class/)<br /><br />[C++/CX Bölüm 2/ \[ n \] : aşkları yapan türler](https://devblogs.microsoft.com/cppblog/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C++/CX Bölüm 3/ \[ n \] : yapım aşamasında](https://devblogs.microsoft.com/cppblog/ccx-part-3-of-n-under-construction/)<br /><br />[C++/CX Bölüm 4/ \[ n \] : statik üye işlevleri](https://devblogs.microsoft.com/cppblog/ccx-part-4-of-n-static-member-functions/)| C++/cx'teki bir tanıtıcı blog serisi. |
