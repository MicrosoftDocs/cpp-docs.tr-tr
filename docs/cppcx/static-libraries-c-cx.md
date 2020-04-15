---
title: Statik Kitaplıklar (C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: 3c4bfd28b805903a2e596ef6d648ff31b0b8261c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358106"
---
# <a name="static-libraries-ccx"></a>Statik Kitaplıklar (C++/CX)

Evrensel Windows Platformu (UWP) uygulamasında kullanılan statik kitaplık, STL türleri de dahil olmak üzere ISO standardı C++ kodu içerebilir ve Windows Runtime uygulama platformunun dışında olmayan Win32 API'lerini de çağırabilir. Statik kitaplık Windows Runtime bileşenlerini tüketir ve belirli kısıtlamalarla Windows Runtime bileşenleri oluşturabilir.

## <a name="creating-static-libraries"></a>Statik kitaplıklar oluşturma

Yeni bir proje oluşturma yönergeleri Visual Studio'nun hangi sürümünü yüklediğinize bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>Visual Studio 2019'da UWP statik kitaplığı oluşturmak için

1. Menü çubuğunda, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **UWP**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Statik Kitaplık'ı (Evrensel Windows - C++/CX)** seçin ve **ardından İleri'yi**seçin. Bir sonraki sayfada, projeye bir ad verin ve istenirse proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 veya Visual Studio 2015'te UWP statik kitaplığı oluşturmak için

1. Menü çubuğunda**Yeni** > **Proje** **yi seçin.** >  **Visual C++** > **Windows Universal** altında Statik **Kitaplık (Evrensel Windows)** seçin.

1. **Çözüm Gezgini'nde,** proje için kısayol menüsünü açın ve ardından **Özellikler'i**seçin. **Özellikler** iletişim kutusunda, Configuration **Properties** > **C/C++** sayfasında, **Windows Runtime Extension'ı** Evet **(/ZW)** olarak ayarlayın.

::: moniker-end

Yeni bir statik kitaplık derlediğinizde, UWP uygulamaları için hariç olan Win32 API'sini ararsanız, derleyici C3861 hatasını yükseltir, "Tanımlayıcı bulunamadı." Windows Runtime için desteklenen alternatif bir yöntem aramak için [UWP uygulamalarında Windows API'larına Alternatifler'e](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)bakın.

UWP uygulaması çözümüne C++ statik kitaplık projesi eklerseniz, UWP destek özelliğinin **Evet**olarak ayarlanması için kitaplık projesinin özellik ayarlarını güncelleştirmeniz gerekebilir. Bu ayar olmadan, kod oluşturur ve bağlantılar, ancak Microsoft Mağazası için uygulamayı doğrulamaya çalıştığınızda bir hata oluşur. Statik lib, onu tüketen projeyle aynı derleyici ayarlarıyla derlenmelidir.

Ortak sınıflar, ortak `ref` arabirim sınıfları veya ortak değer sınıfları oluşturan statik bir kitaplık tüketirseniz, bağlayıcı şu uyarıyı yükseltir:

> **uyarı LNK4264:** /ZW ile derlenen nesne dosyasının statik bir kitaplığa arşivleme; Windows Runtime türlerini yazarken, Windows Runtime meta verilerini içeren statik bir kitaplıkla bağlantı kurmanın önerilmediğini unutmayın.

Yalnızca statik kitaplık kitaplığın kendisi dışında tüketilen Windows Runtime bileşenlerini üretmiyorsa, uyarıyı güvenle yoksayabilirsiniz. Kitaplık tanımladığı bir bileşeni tüketmiyorsa, ortak meta veriler tür bilgilerini içerse bile bağlayıcı uygulamayı en iyi duruma getirebilir. Bu, statik kitaplıktaki ortak bileşenlerin derleşeceği, ancak çalışma zamanında etkinleştirilen anlamına gelir. Bu nedenle, diğer bileşenler veya uygulamalar tarafından tüketilmesi amaçlanan herhangi bir Windows Runtime bileşeni dinamik bağlantı kitaplığında (DLL) uygulanmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[İş Parçacığı Oluşturma ve Hazırlama](../cppcx/threading-and-marshaling-c-cx.md)
