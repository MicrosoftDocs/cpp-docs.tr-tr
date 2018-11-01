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
ms.openlocfilehash: 2296654e6935bc40f301226b184cf34f77cb126d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539275"
---
# <a name="application-domains-and-visual-c"></a>Uygulama etki alanları ve Visual C++

Varsa bir `__clrcall` sanal işlev vtable uygulama etki alanı (appdomain) başına olacaktır. Bir appdomain içinde bir nesne oluşturursanız, yalnızca sanal işleve, appdomain içinde çağırabilirsiniz. Karma modda (**/CLR**) türünüz Hayır, işlem içi vtable varsa `__clrcall` sanal işlevler. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Daha fazla bilgi için bkz.:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)