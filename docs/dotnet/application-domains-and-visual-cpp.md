---
description: 'Daha fazla bilgi edinin: uygulama etki alanları ve Visual C++'
title: Uygulama Etki Alanları ve Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 55f02aec7b3b2d23f10ae9142dba7c61ff60683f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282828"
---
# <a name="application-domains-and-visual-c"></a>Uygulama etki alanları ve Visual C++

`__clrcall`Sanal işleviniz varsa, vtable uygulama etki alanı (AppDomain) başına olur. Bir uygulama etki alanında bir nesne oluşturursanız, sanal işlevi yalnızca bu AppDomain içinden çağırabilirsiniz. Karma modda (**/clr**), türü sanal işlevler yoksa işlem başına vtables ' a sahip olursunuz `__clrcall` . **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [işle](../cpp/process.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
