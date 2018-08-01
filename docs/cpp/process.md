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
ms.openlocfilehash: fdad177231c02d2e6f6fad171ae1811ecb9ccc6c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407188"
---
# <a name="process"></a>process

Yönetilen uygulama işleminizde, belirli genel değişkenin, statik üye değişkeninin veya işlemde tüm uygulama etki alanlarında paylaşılan statik yerel değişkenin tek bir kopyasının olması gerektiğini belirtir. Bu temelde ile derleme yaparken kullanılmak üzere tasarlanmıştır **/CLR: pure**, hangi Visual Studio 2017'de kullanım dışı ve Visual Studio 2017'de desteklenmiyor. İle derlerken **/CLR**, genel ve statik değişkenler işlemi başına varsayılan olarak ve kullanmanıza gerek yoktur **__declspec(process)**.

Genel bir değişkenin, statik üye değişkeni veya özgün türün statik bir yerel değişkeni ile işaretlenebilir **__declspec(process)**.

**işlem** yalnızca ile derlerken geçerlidir [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

Her uygulama etki alanı kendi genel değişken kopyasına sahip olmasını istiyorsanız, kullanın [appdomain](../cpp/appdomain.md).

Bkz: [uygulama etki alanları ve Visual C++](../dotnet/application-domains-and-visual-cpp.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.
 [__declspec](../cpp/declspec.md)  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)
