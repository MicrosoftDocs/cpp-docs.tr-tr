---
title: Visual Studio'da Clang-Tidy kullanma
description: Microsoft C++ kod analizi için Visual Studio'da Clang-Tidy nasıl kullanılır?
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: ff32f522eaacee67e19aedaa1153b2c68edc98d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355156"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Visual Studio'da Clang-Tidy kullanma

::: moniker range="<=vs-2017"

Clang-Tidy desteği Visual Studio 2019 sürüm 16.4 veya daha sonra gerektirir. Bu sürümün belgelerini görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=vs-2019"

Kod Analizi, ister Clang ister MSVC araç kümeleri kullanarak olsun, hem MSBuild hem de CMake projeleri için [Clang-Tidy'yi](https://clang.llvm.org/extra/clang-tidy/) doğal olarak destekler. Clang-Tidy denetimleri arka plan kodu çözümlemesi bir parçası olarak çalıştırılabilir. Bunlar editör içi uyarılar (dalgalı) olarak görünür ve Hata Listesinde görüntülenir.

Clang-Tidy desteği Visual Studio 2019 sürüm 16.4'ten itibaren mevcuttur. Visual Studio Yükleyici'de C++ iş yükünü seçtiğinizde otomatik olarak dahil edilir.

Clang-Tidy, HEM MSBuild hem de CMake'de bulunan LLVM/clang-cl araç setini kullanırken varsayılan analiz aracıdır. Standart Kod Analizi deneyiminin yanında çalışmak veya değiştirmek için bir MSVC araç kümesi ni kullanırken yapılandırabilirsiniz. Clang-cl araç kümesini kullanıyorsanız, Microsoft Code Analysis kullanılamaz.

Clang-Tidy başarılı derleme sonra çalışır. Clang-Tidy sonuçları almak için kaynak kodu hatalarını çözmeniz gerekebilir.

## <a name="msbuild"></a>MSBuild

Clang-Tidy'yi hem Kod Çözümlemesi'nin bir parçası olarak çalışacak hem de Proje Özellikleri **penceresindeki Kod Analizi** > **Genel** sayfası altında oluşturacak şekilde yapılandırabilirsiniz. Aracı yapılandırma seçenekleri Clang-Tidy alt menüsü altında bulunabilir.

Daha fazla bilgi için [bkz: C/C++ Projeleri için Kod Çözümleme Özelliklerini Ayarla.](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md)

## <a name="cmake"></a>CMake

CMake projelerinde, Clang-Tidy denetimlerini `CMakeSettings.json`içinde yapılandırabilirsiniz. Açıldıktan sonra CMake Project Settings Editor'un sağ üst köşesindeki "JSON'u Düzelt"i tıklayın. Aşağıdaki anahtarlar tanınır:

- `enableMicrosoftCodeAnalysis`: Microsoft Kod Analizini sağlar
- `enableClangTidyCodeAnalysis`: Clang-Tidy analizini sağlar
- `clangTidyChecks`: Clang-Tidy yapılandırması, virgülle ayrılmış bir liste olarak belirtilir, yani etkinleştirilecek veya devre dışı bırakılırsa denetler

"Etkinleştirme" seçeneklerinden hiçbiri belirtilmemişse, Visual Studio kullanılan Platform Araç Kümesiile eşleşen çözümleme aracını seçer.

## <a name="warning-display"></a>Uyarı ekranı

Clang-Tidy çalışır hatalar listesinde görüntülenen uyarılar neden ve kod ilgili bölümleri altında editör-in-squiggles gibi. Clang-Tidy uyarılarını sıralamak ve düzenlemek için Hata Listesi'ndeki "Kategori" sütununa kullanın. **Araçlar** > **Seçenekleri**altında "Kod AnaliziSquiggles Devre Dışı" ayarı geçiş yaparak editör içi uyarıları yapılandırabilirsiniz.

## <a name="clang-tidy-configuration"></a>Clang-Tidy yapılandırması

**Clang-Tidy Checks** seçeneği ile Visual Studio içinde clang-tidy çalışan çekleri yapılandırabilirsiniz. Bu giriş, aracın **--denetimleri** bağımsız değişkenine sağlanır. Başka yapılandırma özel *`.clang-tidy`* dosyalara eklenebilir. Daha fazla bilgi için, [LLVM.org Clang-Tidy belgelerine](https://clang.llvm.org/extra/clang-tidy/)bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [MSBuild Projeleri için Clang/LLVM Desteği](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [CMake Projeleri için Clang/LLVM Desteği](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end
