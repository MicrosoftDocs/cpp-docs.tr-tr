---
title: Saf ve Doğrulanabilen Kod (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
ms.openlocfilehash: 11cccc082d5b9e467f5fafce6f2128aa50d33879
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512829"
---
# <a name="pure-and-verifiable-code-ccli"></a>Saf ve doğrulanabilen kod (C + +/ CLI)

.NET programlama için Visual C++ Visual Studio 2017'de karışık derlemeler oluşturma kullanarak destekler [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. **/CLR: pure** ve **CLR: safe** seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor. Kodunuzu güvenli veya doğrulanabilir olması gerekir ve ardından ona bağlantı öneririz, C#.

## <a name="mixed-clr"></a>Karışık (/ clr)

Karışık derlemeler (ile derlenmiş **/CLR**), hem yönetilmeyen hem de içerir ve yönetilen bölümleri .NET özelliklerini kullanmayı mümkün hale getirme, ancak yine de yerel kod içerir. Bu, uygulamaları ve bileşenleri güncelleştirilmesi tüm proje yazılması gerekmeden .NET özelliklerini kullanmayı sağlar. Bu şekilde yönetilen ve yerel kodda karıştırmak için Visual C++ kullanarak C++ birlikte çalışabilirliği çağırılır. Daha fazla bilgi için [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [Native ve .NET ile birlikte çalışabilirlik](../dotnet/native-and-dotnet-interoperability.md).

Yönetilen derlemelerden P/Invoke aracılığıyla yerel DLL'lere yapılan çağrıları derlenir, ancak güvenlik ayarlarına bağlı olarak çalışma zamanında başarısız olabilir.

Derleyici geçecek ancak doğrulanamayan bir derlemede sonuçlanacak bir kodlama senaryosu vardır: kapsam çözünürlük işlecini kullanarak bir nesne örneği üzerinden sanal bir işlev çağırma.  Örneğin: `MyObj -> A::VirtualFunction();`

## <a name="see-also"></a>Ayrıca bkz.

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

