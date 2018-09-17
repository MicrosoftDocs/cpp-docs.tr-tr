---
title: Komut makroları ve seçenek makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c66295a42fff6a2e6dde5205fb5d9139e6eceb6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705542"
---
# <a name="command-macros-and-options-macros"></a>Komut Makroları ve Seçenek Makroları

Komut makroları, Microsoft ürünleri için önceden tanımlanmıştır. Seçenekler makroları, bu ürünler için seçenekleri temsil eder ve varsayılan olarak tanımlanmamış. Hem önceden tanımlanmış Çıkarsama kurallarında kullanılan ve açıklama blokları veya kullanıcı tanımlı çıkarım kuralları içinde kullanılabilir. Komut makroları kısmını veya tamamını seçenekleri dahil olmak üzere bir komut satırı temsil etmek için tanımlanabilir. Seçenekler makroları tanımsız boş bir dize oluşturur.

|Microsoft Ürün|Komut makrosu|Olarak tanımlanmış|Seçenekleri makrosu|
|-----------------------|-------------------|----------------|-------------------|
|Macro derleyicisi|**FARKLI**|ml|**AFLAGS**|
|Temel derleyici|**BC**|BC|**BFLAGS**|
|C derleyicisi|**CC**|cl|**CFLAGS**|
|C++ Derleyicisi|**CPP**|cl|**CPPFLAGS**|
|C++ Derleyicisi|**CXX**|cl|**CXXFLAGS**|
|Kaynak Derleyicisi|**RC**|RC|**RFLAGS**|

## <a name="see-also"></a>Ayrıca Bkz.

[Özel NMAKE Makroları](../build/special-nmake-macros.md)