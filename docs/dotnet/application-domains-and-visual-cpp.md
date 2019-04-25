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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223039"
---
# <a name="application-domains-and-visual-c"></a>Uygulama etki alanları ve Visual C++

Varsa bir `__clrcall` sanal işlev vtable uygulama etki alanı (appdomain) başına olacaktır. Bir appdomain içinde bir nesne oluşturursanız, yalnızca sanal işleve, appdomain içinde çağırabilirsiniz. Karma modda (**/CLR**) türünüz Hayır, işlem içi vtable varsa `__clrcall` sanal işlevler. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Daha fazla bilgi için bkz.:

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)