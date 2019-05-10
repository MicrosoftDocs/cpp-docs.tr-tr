---
title: Statik kitaplıklar (C++/CX)
ms.date: 02/03/2017
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
ms.openlocfilehash: 188ba06518bf6cdd154b7d6bd61216ed1e4ffad3
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877250"
---
# <a name="static-libraries-ccx"></a>Statik kitaplıklar (C++/CX)

Evrensel Windows Platformu (UWP) bir uygulamada kullanılan bir statik kitaplığı STL türleri ve Windows çalışma zamanı uygulama platformdan hariç Win32 API çağrıları dahil olmak üzere, ISO standardı C++ kod içerebilir. Statik kitaplık, Windows çalışma zamanı bileşenlerini kullanır ve Windows çalışma zamanı bileşenleri ile ilgili bazı kısıtlamalar oluşturabilirsiniz.

## <a name="creating-static-libraries"></a>Statik kitaplıklar oluşturma


Yeni bir proje oluşturmak için yönergeler, yüklediğiniz Visual Studio'nun hangi sürümünün bağlı olarak değişir. Sola doğru sürüme ayarlayın üst sürüm Seçici olduğundan emin olun.

::: moniker range="vs-2019"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2019"></a>İçinde Visual Studio 2019 UWP statik kitaplık oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje** açmak için **yeni bir proje oluşturma** iletişim kutusu.

1. İletişim kutusunun üstündeki ayarlamak **dil** için **C++** ayarlayın **Platform** için **Windows**, ayarlayıp **proje türü** için **UWP**. 

1. Filtrelenmiş proje türleri listesinden seçim **statik kitaplık (Evrensel Windows - C++/CX)** ardından **sonraki**. Sonraki sayfada, projeye bir ad verin ve istenen proje konumu belirtin.

1. Seçin **Oluştur** projeyi oluşturmak için.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-a-uwp-static-library-in-visual-studio-2017-or-visual-studio-2015"></a>Visual Studio 2017 veya Visual Studio 2015'te UWP statik kitaplık oluşturmak için

1. Menü çubuğunda, **dosya** > **yeni** > **proje**. Altında **Visual C++** > **Windows Evrensel** seçin **statik kitaplık (Evrensel Windows)**.

1. İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**. İçinde **özellikleri** iletişim kutusundaki **yapılandırma özellikleri** > **C/C++** sayfasında **Windows çalışma zamanı uzantısınıkullanma** için **(/ZW) Evet**.

::: moniker-end

Yeni bir statik kitaplık için UWP uygulamaları hariç tutulan bir Win32 API çağrısı yapıyorsa derlediğinizde, derleyici hatası C3861, "tanımlayıcısı bulunamadı." oluşturacak Windows çalışma zamanı için desteklenen alternatif bir yöntem aramak için bkz: [UWP uygulamalarında Windows API'lere alternatifler](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

Bir UWP uygulaması çözüme bir C++ statik kitaplık projesi eklerseniz, kitaplık projesinin özellik ayarlarını güncelleştirin, böylece UWP desteği özelliği gerekebilir **Evet**. Bu ayar olmadan kod derlenir ve bağlantılar, ancak bir hata için Microsoft Store uygulaması doğrulamaya olduğunda gerçekleşir. Statik kitaplık, projenin kullandığı aynı derleyici ayarları ile derlenmelidir.

Genel oluşturan bir statik kitaplık kazanabilirsiniz `ref` sınıfları, ortak arabirim sınıfları veya genel değer sınıfları, bağlayıcı bu uyarıyı oluşturur:

> **LNK4264 Uyarı:** statik kitaplığa; /ZW ile derlenen nesne dosyası arşivleme, Windows çalışma zamanı türleri yazılırken, Windows çalışma zamanı meta verileri içeren statik bir kitaplıkla bağlamak için önerilmediğini unutmayın.

Yalnızca statik kitaplık kitaplık dışında kullanılan Windows çalışma zamanı bileşenleri vermiyor, uyarıyı güvenle yoksayabilirsiniz. Kitaplık tanımlayan bir bileşen kullanmaz, tür bilgilerini ortak meta veriler içeriyor olsa bile ardından bağlayıcı hemen uygulama en iyi duruma getirebilirsiniz. Başka bir deyişle, statik kitaplıkta ortak bileşenler derleyeceği fakat çalışma zamanında etkinleştirmez. Bu nedenle, bir dinamik bağlantı kitaplığı (DLL) tüketim için hazırlanmış herhangi bir Windows çalışma zamanı bileşeni tarafından diğer bileşenler veya uygulamaları uygulanmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[İş Parçacığı Oluşturma ve Hazırlama](../cppcx/threading-and-marshaling-c-cx.md)
