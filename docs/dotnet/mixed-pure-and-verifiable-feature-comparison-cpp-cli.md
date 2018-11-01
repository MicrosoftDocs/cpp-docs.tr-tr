---
title: Karışık, saf ve doğrulanabilen özellik karşılaştırması (C + +/ CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- safe assemblies [C++], vs. pure
- mixed assemblies [C++], vs. pure
- safe assemblies [C++], vs. mixed
- pure MSIL [C++]
- verifiable assemblies [C++]
- pure MSIL [C++], vs. safe
- pure MSIL [C++], vs. mixed
- pure MSIL [C++], compared to mixed and safe
- verifiable assemblies [C++], vs. mixed
- mixed assemblies [C++], vs. safe
- verifiable assemblies [C++], vs. pure
- pure assemblies [C++]
- safe assemblies [C++]
- mixed assemblies [C++]
ms.assetid: 3f7a82ba-0e69-4927-ba0c-fbc3160e4394
ms.openlocfilehash: 81fcf986ee68f5f8f64c8070bb992fa1cda1683b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482084"
---
# <a name="mixed-pure-and-verifiable-feature-comparison-ccli"></a>Karışık, saf ve doğrulanabilen özellik karşılaştırması (C + +/ CLI)

Bu konuda özelliklerin yanı sıra farklı karşılaştırır **/CLR** derleme modlarını. Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md).

> [!IMPORTANT]
> **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="feature-comparison"></a>Özellik karşılaştırması

|Özellik|Karışık (/ clr)|Saf (/ clr: pure)|Güvenli (/ CLR: safe)|İlgili bilgiler|
|-------------|---------------------|-------------------------|-------------------------|-------------------------|
|CRT kitaplığı|Desteklenen|deprecated||[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)|
|MFC/ATL|Desteklenen|||[MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md) &#124; [sınıfı genel bakış](../atl/atl-class-overview.md)|
|Yönetilmeyen İşlevler|Desteklenen|||[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)|
|Yönetilmeyen veri|Desteklenen|deprecated||[Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)|
|Yönetilmeyen İşlevler'den çağrılabilir|Desteklenen||||
|Yönetilmeyen işlevleri çağırma destekler|Desteklenen|deprecated|deprecated|[C++ Birlikte Çalışabilirliği Kullanma (Örtük PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)|
|Yansıma destekler|Yalnızca DLL'leri|deprecated|deprecated|[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)|

## <a name="see-also"></a>Ayrıca bkz.

- [Saf ve Doğrulanabilen Kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)