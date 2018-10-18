---
title: Visual C++ Dil Başvurusu (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 578df738d2c601c82f530ee32ae30284f6dac5ef
ms.sourcegitcommit: e462e78a2dac06a0a539299facf34cdaeaf4d08c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2018
ms.locfileid: "49401415"
---
# <a name="visual-c-language-reference-ccx"></a>Visual C++ Dil Başvurusu (C + +/ CX)

C + +/ CX Windows uygulamaları ve Windows çalışma zamanı bileşenleri olabildiğince ve modern C++ kapatmak gibi bir deyim oluşturulmasını sağlayan C++ dil uzantıları kümesidir. Kullanmak C + +/ CX Windows uygulamaları ve bileşenleri Visual C#, Visual Basic ve JavaScript ile kolayca etkileşim yerel kod ve Windows çalışma zamanı desteği diğer diller yazılacak. Ham COM arabirimleri ya da özel durumlu olmayan kod doğrudan erişim gerektiren taşıdığı nadir durumlarda, kullandığınız [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> **[C + +/ WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index) önerilen alternatif C + +/ CX**. Bu, bir yeni, standart C ++ 17 dil projeksiyon için Windows çalışma zamanı API'leri, en son Windows 10 SDK sürüm 1803 ileriye doğru kullanılabilir olur. C + +/ WinRT tamamen üstbilgi dosyalarında uygulanan ve modern Windows API ile birinci sınıf erişim sağlayacak şekilde tasarlanmıştır.

> İle C + +/ WinRT, size hem kullanabilir ve Windows çalışma zamanı API'leri kullanarak tüm standartlara uyumlu C ++ 17 derleyici yazar. C + +/ WinRT genellikle daha iyi gerçekleştirir ve Windows çalışma zamanı için diğer bir dil seçeneği değerinden daha küçük ikili dosyaları üretir. Biz C + desteklemeye devam edecektir +/ CX ve WRL, ancak yüksek yeni uygulama C + kullanmanız +/ WinRT. Daha fazla bilgi için [C + +/ WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).

Kullanarak C + +/ CX, oluşturabilirsiniz:

- Kullanıcıyı tanımlamak için XAML kullanan C++ Evrensel Windows Platformu (UWP) uygulamaları arabirim ve yerel yığın kullanın. Daha fazla bilgi için [bir "hello world" uygulaması C++ (UWP) oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- JavaScript tabanlı Windows uygulamaları tarafından tüketilebilecek bir C++ Windows çalışma zamanı bileşenleri. Daha fazla bilgi için [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows DirectX oyunlar ve grafik kullanımı yoğun uygulamalar. Daha fazla bilgi için [DirectX ile basit bir UWP oyunu oluşturma](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game).

## <a name="related-articles"></a>İlgili makaleler

|||
|-|-|
|[Hızlı Başvuru](../cppcx/quick-reference-c-cx.md)|Tablo anahtar sözcükleri ve işleçler için C + +/ CX.|
|[Tür Sistemi](../cppcx/type-system-c-cx.md)|Açıklar temel C + +/ CX türleri ve programlama yapıları ve nasıl kullanmak C + +/ CX kullanma ve Windows çalışma zamanı türleri oluşturmak için.|
|[Uygulamaları oluşturma ve kitaplıkları](../cppcx/building-apps-and-libraries-c-cx.md)|IDE uygulamaları ve statik kitaplıklar aned DLL'leri bağlantı oluşturmak için nasıl kullanılacağını açıklar.|
|[Diğer dillerle birlikte çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)|Açıklar nasıl C + kullanılarak yazılan bileşenleri +/ CX kullanılabilir JavaScript'te yazılmış bileşenler ile tüm yönetilen dil ya da Windows çalışma zamanı C++ Şablon kitaplığı.|
|[İş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md)|Oluşturduğunuz bileşenlerin iş parçacığı oluşturma ve hazırlama davranışını belirtmek nasıl ele alınmaktadır.|
|[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)|Varsayılan ad alanı, Platform ad alanı, Platform::Collections ve ilgili ad alanları için başvuru belgeleri.|
|[Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows çalışma zamanı uygulamaları için kullanılabilir olmayan CRT işlevleri listeler.|
|[Nasıl yapılır kılavuzları, Windows 10 uygulamaları için](https://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 uygulamaları ve daha fazla bilgi için bağlantılar hakkında ileri düzey rehberlik sağlar.|
|[C + +/ CX parçası 0 \[n\]: Giriş](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + +/ CX bölüm 1 / \[n\]: basit bir sınıfı](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + +/ CX parçası 2 \[n\]: Hats Wear türleri](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + +/ CX parçası 3 \[n\]: aşamasında](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + +/ CX parçası 4 \[n\]: statik üye işlevleri](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Bir tanıtım Visual C++ blog serisini C + +/ CX.|
