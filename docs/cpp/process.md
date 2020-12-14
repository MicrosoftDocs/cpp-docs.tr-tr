---
description: 'Hakkında daha fazla bilgi edinin: `process`'
title: process
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: ea5baee65b3375e062939f49bc30f3780c312852
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198605"
---
# `process`

Yönetilen uygulama işleminizde, belirli genel değişkenin, statik üye değişkeninin veya işlemde tüm uygulama etki alanlarında paylaşılan statik yerel değişkenin tek bir kopyasının olması gerektiğini belirtir. Bu **`/clr:pure`** , özellikle Visual studio 2015 ' de kullanımdan kaldırılmıştır ve Visual studio 2017 ' de desteklenmeyen ve ile derlerken kullanılmak üzere tasarlanmıştır. İle derlerken **`/clr`** , genel ve statik değişkenler varsayılan olarak işlem başına yapılır ve kullanması gerekmez **`__declspec(process)`** .

Yalnızca genel bir değişken, bir statik üye değişkeni veya yerel türdeki statik yerel değişken ile işaretlenebilir **`__declspec(process)`** .

**`process`** yalnızca ile derlenirken geçerlidir [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) .

Her uygulama etki alanının kendi genel değişken kopyasının olmasını istiyorsanız [AppDomain](../cpp/appdomain.md)kullanın.

Daha fazla bilgi için bkz. [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[`__declspec`](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
