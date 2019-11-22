---
title: Statik kitaplıklar (C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: f62ef03cfdf2f424fd4a50c2e866d73b5bdce7fc
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74302937"
---
# <a name="static-libraries-ccx"></a>Statik kitaplıklar (C++/CX)

Evrensel Windows Platformu (UWP) uygulamasında kullanılan statik bir kitaplık, STL türleri dahil olmak üzere ISO standardı C++ kodu ve ayrıca Windows çalışma zamanı uygulama platformundan hariç tutulan Win32 API 'lerine çağrılar içerebilir. Statik Kitaplık Windows Çalışma Zamanı bileşenleri kullanır ve belirli kısıtlamalara sahip Windows Çalışma Zamanı bileşenleri oluşturabilir.

## <a name="creating-static-libraries"></a>Statik kitaplıklar oluşturma


Yeni bir proje oluşturmak için yönergeler, yüklediğiniz Visual Studio sürümüne bağlı olarak farklılık gösterir. Sol üstteki sürüm seçicisine doğru sürüme sahip olduğunuzdan emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>Visual Studio 2019 ' de UWP statik kitaplığı oluşturmak için

1. **Yeni proje oluştur** iletişim kutusunu açmak için menü çubuğunda **dosya** > **Yeni** > **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** olarak **C++** ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **UWP**olarak ayarlayın. 

1. Filtre uygulanmış proje türleri listesinden **statik kitaplık (Evrensel Windows- C++/CX)** öğesini seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, projeye bir ad verin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 veya Visual Studio 2015 ' de UWP statik kitaplığı oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**. **Visual C++**  > **Windows Universal** altında **statik kitaplık (Evrensel Windows)** seçeneğini belirleyin.

1. **Çözüm Gezgini**' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin. **Özellikler** iletişim kutusunda, **yapılandırma özellikleri** > **CC++ /** sayfasında, kullanım **Windows çalışma zamanı uzantısını** **Evet (/ZW)** olarak ayarlayın.

::: moniker-end

Yeni bir statik kitaplık derlerken, UWP uygulamaları için dışlanan bir Win32 API çağrısı yaparsanız, derleyici hata C3861, "tanımlayıcı bulunamadı" olarak oluşturulur. Windows Çalışma Zamanı için desteklenen alternatif bir yöntemi aramak için bkz. [UWP uygulamalarında Windows API 'Lerinin alternatifleri](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

UWP uygulama çözümüne bir C++ statik kitaplık projesi eklersenız, UWP support özelliğinin **Evet**olarak ayarlanması için kitaplık projesinin özellik ayarlarını güncelleştirmeniz gerekebilir. Bu ayar olmadan kod oluşturulur ve bağlar, ancak uygulamayı Microsoft Store doğrulamaya çalıştığınızda bir hata oluşur. Statik LIB, kendisini kullanan projeyle aynı derleyici ayarları ile derlenmelidir.

Ortak `ref` sınıfları, genel arabirim sınıfları veya ortak değer sınıfları oluşturan bir statik kitaplık kullanıyorsanız, bağlayıcı şu uyarıyı oluşturur:

> **Uyarı LNK4264:** /ZW ile derlenen nesne dosyasını statik bir kitaplığa arşivleme; Windows Çalışma Zamanı türler yazarken Windows Çalışma Zamanı meta verileri içeren bir statik kitaplıkla bağlantı önerilmediğini unutmayın.

Yalnızca statik kitaplık, kitaplığın kendisi dışında tüketilen Windows Çalışma Zamanı bileşenleri üretilmediği takdirde uyarıyı güvenle yoksayabilirsiniz. Kitaplık, tanımladığı bir bileşeni tüketmezse, genel meta veriler tür bilgilerini içerse de bağlayıcı, uygulamayı iyileştirebilirler. Bu, bir statik kitaplıktaki ortak bileşenlerin derlenmesi, ancak çalışma zamanında etkinleştirilmeyeceği anlamına gelir. Bu nedenle, diğer bileşenler veya uygulamalar tarafından tüketimi için tasarlanan tüm Windows Çalışma Zamanı bileşenleri dinamik bağlantı kitaplığı 'nda (DLL) uygulanmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[İş Parçacığı Oluşturma ve Hazırlama](../cppcx/threading-and-marshaling-c-cx.md)
