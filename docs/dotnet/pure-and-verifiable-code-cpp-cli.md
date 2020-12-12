---
description: 'Daha fazla bilgi edinin: saf ve Doğrulanabilen kod (C++/CLı)'
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
ms.openlocfilehash: 64224f7f462b5e11e522648a5b64ec9d568dc53f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276770"
---
# <a name="pure-and-verifiable-code-ccli"></a>Saf ve Doğrulanabilen kod (C++/CLı)

.NET programlama için, Visual Studio 2017 ' deki Visual C++, [/clr (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği kullanılarak karışık derlemelerin oluşturulmasını destekler. **/Clr: Pure** ve **clr: Safe** seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez. Kodunuzun güvenli veya doğrulanabilir olması gerekiyorsa, bunu C# ' ye bağlantı noktası oluşturmanız önerilir.

## <a name="mixed-clr"></a>Karışık (/CLR)

Karma derlemeler ( **/clr** ile derlenen), hem yönetilmeyen hem de yönetilen parçaları içerir, bu da .NET özelliklerini kullanmasını sağlar, ancak yine de yerel kod içerir. Bu, uygulamaların ve bileşenlerin tüm projenin yeniden yazılması gerekmeden .NET özelliklerini kullanmak üzere güncelleştirilmesini sağlar. Bu biçimde yönetilen ve yerel kodu karıştırmak için Visual C++ kullanmak C++ birlikte çalışabilirliği olarak adlandırılır. Daha fazla bilgi için bkz. [karma (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [yerel ve .net birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md).

Yönetilen derlemelerden P/Invoke aracılığıyla yerel dll 'lere yapılan çağrılar derlenir, ancak güvenlik ayarlarına bağlı olarak çalışma zamanında başarısız olabilir.

Derleyiciyi geçecek ancak doğrulanamayan bir derlemeye neden olacak bir kodlama senaryosu var: kapsam çözümleme işleci kullanılarak bir nesne örneği aracılığıyla bir sanal işlev çağırma.  Örneğin: `MyObj -> A::VirtualFunction();`.

## <a name="see-also"></a>Ayrıca bkz.

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
