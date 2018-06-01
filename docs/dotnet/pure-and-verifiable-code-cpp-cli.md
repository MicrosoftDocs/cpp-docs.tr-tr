---
title: Saf ve doğrulanabilen kod (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 453bb40e94c1d345adbe22f8792b59d1e584499a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704834"
---
# <a name="pure-and-verifiable-code-ccli"></a>Saf ve doğrulanabilen kod (C + +/ CLI)

.NET programlama için Visual Studio 2017'de Visual C++ oluşturulmasını karışık derlemeler kullanarak destekleyen [/CLR (ortak dil çalışma zamanı derlemesi)](../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği. **/CLR: pure** ve **CLR: safe** seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor. Ardından kodunuzu güvenli veya doğrulanabilen olması gerekiyorsa, bu C# bağlantı noktasının öneririz.

## <a name="mixed-clr"></a>Karma (/ clr)

Karışık derlemeler (ile derlenmiş **/CLR**), hem de yönetilmeyen içerir ve yönetilen bölümleri, bunlar için .NET özellikleri kullanmak olası hale getirerek, ancak yine yerel kod içerir. Bu, tüm proje yazılması gerekmeden .NET özellikleri kullanmak uygulamaları ve bileşenleri güncelleştirilmesini sağlar. Visual C++ yönetilen ve yerel kodu bu şekilde karıştırmak kullanmayı C++ birlikte çalışabilirliği adı verilir. Daha fazla bilgi için bkz: [karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md) ve [yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md).

Yönetilen derlemelerden Yerel DLL'leri P/Invoke aracılığıyla yapılan çağrılar derlenir ancak güvenlik ayarlarına bağlı olarak çalışma zamanında başarısız olabilir.

Derleyiciyi geçecek ancak doğrulanamayan bir derlemede sonuçlanacak bir kodlama senaryo vardır: kapsam çözümü işleci kullanarak bir nesne örneği aracılığıyla sanal bir işlevi çağırmak.  Örneğin: `MyObj -> A::VirtualFunction();`.

## <a name="see-also"></a>Ayrıca bkz.

- [C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

