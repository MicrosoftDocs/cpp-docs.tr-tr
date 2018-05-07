---
title: Visual C++ Dil Başvurusu (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3f6abf92-4e5e-4ed8-8e11-f9252380d30a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2b251a89eee456905fae1e2096a74362fc6c44ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="visual-c-language-reference-ccx"></a>Visual C++ Dil Başvurusu (C + +/ CX)

C + +/ CX C++ dili için Windows uygulamaları ve modern için olabildiğince C++ kapatmak gibi bir deyim Windows çalışma zamanı bileşenleri oluşturulmasını sağlamak uzantıları kümesidir. Kullanın: C + +/ CX Windows uygulamaları ve bileşenleri kolayca Visual C#, Visual Basic ve JavaScript ile etkileşim yerel kod ve Windows çalışma zamanı desteği diğer diller yazma. Ham COM arabirimleri ya da özel durumlu olmayan kod doğrudan erişim gerektiren bu nadir durumlarda kullandığınız [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

> [!NOTE]
> C + +/ WinRT olan yeni, standart C ++ 17 dil projeksiyon Windows çalışma zamanı API'leri için. En son Windows 10 SDK'sı sürümünden 1803 ileriye doğru kullanılabilir. C + +/ WinRT tamamen üstbilgi dosyalarında uygulanan ve modern Windows API ile birinci sınıf erişim sağlamak üzere tasarlanmıştır.

> İle C + +/ WinRT, size hem kullanabilir ve Windows çalışma zamanı herhangi standartlarıyla uyumlu C ++ 17 derleyici kullanarak API'leri yazar. C + +/ WinRT genellikle daha iyi gerçekleştirir ve Windows çalışma zamanı için başka bir dil seçeneği değerinden daha küçük ikili dosyaları üretir. C + desteklemek devam +/ CX ve WRL, ancak yüksek oranda yeni uygulamalar C + kullanmanızı öneririz +/ WinRT. Daha fazla bilgi için bkz: [C + +/ WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).


Kullanarak C + +/ CX, oluşturabilirsiniz:

- XAML kullanıcı tanımlamak için kullanmak C++ Evrensel Windows Platformu (UWP) uygulamaları arabirim ve yerel yığın kullanın. Daha fazla bilgi için bkz: [bir "hello world" uygulaması C++ (UWP) oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

- JavaScript tabanlı Windows uygulamaları tarafından kullanılabilecek C++ Windows çalışma zamanı bileşenleri. Daha fazla bilgi için bkz: [C++'da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

- Windows DirectX oyunları ve grafik yoğun uygulamalar. Daha fazla bilgi için bkz: [DirectX ile basit UWP oyun oluşturmak](/windows/uwp/gaming/tutorial--create-your-first-metro-style-directx-game).

## <a name="related-articles"></a>İlgili makaleler

|||
|-|-|
|[Hızlı Başvuru](../cppcx/quick-reference-c-cx.md)|Tablosu anahtar sözcükleri ve işleçler için C + +/ CX.|
|[Tür Sistemi](../cppcx/type-system-c-cx.md)|Açıklar temel C + +/ CX türleri ve programlama yapıları ve nasıl kullanan C + +/ CX kullanabilir ve Windows çalışma zamanı türleri oluşturmak için.|
|[Yapı uygulamalar ve kitaplıklar](../cppcx/building-apps-and-libraries-c-cx.md)|IDE uygulamaları ve statik kitaplıklarından aned DLL'leri bağlantı oluşturmak için nasıl kullanılacağını açıklar.|
|[Diğer dilleri ile birlikte çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)|Anlatılmaktadır nasıl C + kullanılarak yazılan bileşenleri +/ CX kullanılabilir JavaScript'te yazılmış bileşenleri ile dil, yönetilen veya [!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)].|
|[İş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md)|Oluşturduğunuz bileşenlerin iş parçacığı oluşturma ve hazırlama davranışı belirtmek nasıl ele alınmaktadır.|
|[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)|Varsayılan ad alanı, Platform ad alanı, Platform::Collections ve ilgili ad alanları için başvuru belgeleri.|
|[Evrensel Windows Platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)|Windows çalışma zamanı uygulamaları için kullanılabilir olmayan CRT işlevleri listeler.|
|[Nasıl yapılır kılavuzları Windows 10 uygulamaları için](http://msdn.microsoft.com/library/windows/apps/xaml/mt244352.aspx)|Windows 10 uygulamaları ve daha fazla bilgi için bağlantılar hakkında üst düzey rehberlik sağlar.|
|[C + +/ CX parçası 0 \[n\]: Giriş](https://blogs.msdn.microsoft.com/vcblog/2012/08/29/ccx-part-0-of-n-an-introduction/)<br /><br />[C + +/ CX parçası 1 \[n\]: basit bir sınıf](https://blogs.msdn.microsoft.com/vcblog/2012/09/05/ccx-part-1-of-n-a-simple-class/)<br /><br />[C + +/ CX Kısım 2 / \[n\]: şapkalar takmak türleri](https://blogs.msdn.microsoft.com/vcblog/2012/09/17/ccx-part-2-of-n-types-that-wear-hats/)<br /><br />[C + +/ CX parçası 3 \[n\]: aşamasında](https://blogs.msdn.microsoft.com/vcblog/2012/10/05/ccx-part-3-of-n-under-construction/)<br /><br />[C + +/ CX parçası 4 \[n\]: statik üye işlevleri](https://blogs.msdn.microsoft.com/vcblog/2012/10/19/ccx-part-4-of-n-static-member-functions/)|Bir tanıtım Visual C++ blog seriyi C + +/ CX.|
