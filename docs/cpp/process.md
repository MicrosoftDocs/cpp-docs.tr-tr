---
title: işlem | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- process_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b36ec42447aa076d0623707951f82b7b9c95d563
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704912"
---
# <a name="process"></a>process

Yönetilen uygulama işleminizde, belirli genel değişkenin, statik üye değişkeninin veya işlemde tüm uygulama etki alanlarında paylaşılan statik yerel değişkenin tek bir kopyasının olması gerektiğini belirtir. Bu öncelikle ile derleme yapılırken kullanılmak üzere tasarlanmıştır **/CLR: pure**, Visual Studio 2017 içinde kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor. İle derleme yapılırken **/CLR**, genel ve statik değişkenler işlemi başına varsayılan olarak ve kullanmasına gerek kalmamasını `__declspec(process)`.

Yalnızca bir genel değişken, bir statik üye değişkeni veya özgün türün statik bir yerel değişkeni `__declspec(process)` ile işaretlenebilir.

`process` ile derleme yapılırken yalnızca geçerlidir [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

Her uygulama etki genel değişkeni kendi kopyasına sahip olmasını istiyorsanız, kullanmak [appdomain](../cpp/appdomain.md).

Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

- [__declspec](../cpp/declspec.md)
- [Anahtar Sözcükler](../cpp/keywords-cpp.md)
