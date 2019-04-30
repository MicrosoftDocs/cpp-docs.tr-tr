---
title: process
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: 049360dddff2b9ca2ea460b96e027e86899f1ecb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344989"
---
# <a name="process"></a>process

Yönetilen uygulama işleminizde, belirli genel değişkenin, statik üye değişkeninin veya işlemde tüm uygulama etki alanlarında paylaşılan statik yerel değişkenin tek bir kopyasının olması gerektiğini belirtir. Bu temelde ile derleme yaparken kullanılmak üzere tasarlanmıştır **/CLR: pure**, hangi Visual Studio 2017'de kullanım dışı ve Visual Studio 2017'de desteklenmiyor. İle derlerken **/CLR**, genel ve statik değişkenler işlemi başına varsayılan olarak ve kullanmanıza gerek yoktur **__declspec(process)**.

Genel bir değişkenin, statik üye değişkeni veya özgün türün statik bir yerel değişkeni ile işaretlenebilir **__declspec(process)**.

**işlem** yalnızca ile derlerken geçerlidir [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

Her uygulama etki alanı kendi genel değişken kopyasına sahip olmasını istiyorsanız, kullanın [appdomain](../cpp/appdomain.md).

Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
