---
title: Visual Studio 'da Clang-Tidy kullanma
description: Microsoft C++ kod analizi için Visual Studio 'da Clang-Tidy kullanma.
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
ms.openlocfilehash: 30378ab0713d5e00e704f778646b9d60856f2234
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842474"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Visual Studio 'da Clang-Tidy kullanma

::: moniker range="<=vs-2017"

Clang-Tidy için destek, Visual Studio 2019 sürüm 16,4 veya üstünü gerektirir. Bu sürümün belgelerini görmek için bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=vs-2019"

Kod Analizi, Clang veya MSVC Toolsets 'Ler kullanıp, hem MSBuild hem de CMake projeleri için [Clang-Tidy](https://clang.llvm.org/extra/clang-tidy/) 'ı yerel olarak destekler. Clang-Tidy denetimleri, arka plan kodu analizinin bir parçası olarak çalışabilir. Bunlar, düzenleyici uyarıları (dalgalı çizgiler) olarak görünürler ve Hata Listesi görüntülenir.

Clang-Tidy desteği, Visual Studio 2019 sürüm 16,4 ' den başlayarak kullanılabilir. Visual Studio Yükleyicisi bir C++ iş yükünü seçtiğinizde bu otomatik olarak eklenir.

Clang-tidy, hem MSBuild hem de CMake 'te bulunan LLVM/Clang-CL araç takımını kullanırken varsayılan analiz aracıdır. Bu işlemi, birlikte çalışacak şekilde bir MSVC araç kümesi kullanırken veya standart kod analizi deneyimini değiştirmek için yapılandırabilirsiniz. Clang-CL araç takımını kullanırsanız, Microsoft Kod Analizi kullanılamaz.

Clang-Tidy başarıyla derlemeden sonra çalışır. Clang-Tidy sonuçlarını almak için kaynak kodu hatalarını çözmeniz gerekebilir.

## <a name="msbuild"></a>MSBuild

Clang-Tidy ' i hem kod analizinin bir parçası olarak, hem de proje Özellikler penceresi **Kod Analizi**  >  **genel** sayfası altında çalışacak şekilde yapılandırabilirsiniz. Aracı yapılandırma seçenekleri, Clang-Tıdy alt menüsü altında bulunabilir.

Daha fazla bilgi için bkz. [nasıl yapılır: C/C++ projeleri Için kod analizi özelliklerini ayarlama](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md).

## <a name="cmake"></a>CMake

CMake projelerinde, içindeki Clang-Tidy denetimlerini yapılandırabilirsiniz `CMakeSettings.json` . Açıldıktan sonra CMake proje ayarları Düzenleyicisi 'nin sağ üst köşesindeki "JSON 'u Düzenle" seçeneğini belirleyin. Aşağıdaki anahtarlar tanınmalıdır:

- `enableMicrosoftCodeAnalysis`: Microsoft Kod analizini etkinleştirilir
- `enableClangTidyCodeAnalysis`: Clang-Tıdy analizini etkinleştirilir
- `clangTidyChecks`: Virgülle ayrılmış bir liste olarak belirtilen Clang-Tidy yapılandırması, etkin veya devre dışı bırakılacak denetimler

"Etkinleştir" seçeneklerinin hiçbiri belirtilmediyse, Visual Studio kullanılan platform araç takımı ile eşleşen analiz aracını seçer.

## <a name="warning-display"></a>Uyarı görüntüleme

Clang-tidy, Hata Listesi ve kodun ilgili bölümlerinin altında, düzenleyici olarak dalgalı çizgiler olarak görünen uyarılarla sonuçlanır. Clang-Tıdy uyarılarını sıralamak ve düzenlemek için Hata Listesi "Category" sütununu kullanın. **Araç**seçenekleri altındaki "Kod analizini devre dışı bırak" ayarını değiştirerek düzenleyici uyarılarını yapılandırabilirsiniz  >  **Options**.

## <a name="clang-tidy-configuration"></a>Clang-Tidy yapılandırması

Clang-Tidy 'ın, **Clang-Tidy denetimleri** seçeneği aracılığıyla Visual Studio içinde çalıştığı denetimleri yapılandırabilirsiniz. Bu giriş, **`--checks`** aracın bağımsız değişkenine sağlanır. Diğer yapılandırma, özel *`.clang-tidy`* dosyalara eklenebilir. Daha fazla bilgi için LLVM.org adresindeki [Clang-Tidy belgelerine](https://clang.llvm.org/extra/clang-tidy/)bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [MSBuild projeleri için Clang/LLVM desteği](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [CMake projeleri için Clang/LLVM desteği](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
