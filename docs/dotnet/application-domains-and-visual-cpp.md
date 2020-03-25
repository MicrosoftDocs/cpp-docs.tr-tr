---
title: Uygulama Etki Alanları ve Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 16c02bb58681ecb241d3552f57e0b05f2d6711b4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208815"
---
# <a name="application-domains-and-visual-c"></a>Uygulama etki alanları ve Visual C++

`__clrcall` sanal işleviniz varsa, vtable uygulama etki alanı (AppDomain) başına olur. Bir uygulama etki alanında bir nesne oluşturursanız, sanal işlevi yalnızca bu AppDomain içinden çağırabilirsiniz. Karma modda ( **/clr**), türü `__clrcall` sanal işlevler yoksa işlem başına vtables ' a sahip olursunuz. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz.

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
