---
title: Komut makroları ve seçenek makroları
description: Derleme araçları ve bunların seçenekleri için önceden tanımlanmış NMAKE makrolarını açıklar.
ms.date: 11/20/2019
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
no-loc:
- AS
- AFLAGS
- CC
- CFLAGS
- CPP
- CPPFLAGS
- CXX
- CXXFLAGS
- RC
- RFLAGS
- ias
- ml
- ml64
- cl
- rc
ms.openlocfilehash: d5c4477fd97e2a6c48dbac4d0ce83f7fd5f12ad6
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303175"
---
# <a name="command-macros-and-options-macros"></a>Komut makroları ve seçenek makroları

Komut makroları, Microsoft ürünleri için önceden tanımlanmıştır. Seçenekler makroları bu ürünlerin seçeneklerini temsil eder ve varsayılan olarak tanımsız değildir. Her ikisi de önceden tanımlanmış çıkarım kurallarında kullanılır ve açıklama blokları veya Kullanıcı tanımlı çıkarım kurallarında kullanılabilir. Komut makroları, seçenekler de dahil olmak üzere bir komut satırının bir kısmını veya tümünü temsil edecek şekilde yeniden tanımlanabilir. Seçenekler makroları, belirtilmemişse boş bir dize oluşturur.

|Microsoft ürün|Komut makrosu|Farklı tanımlanmış|Seçenekler makrosu|
|-----------------------|-------------------|----------------|-------------------|
|Makro Assembler|**AS**|ml, iasveya ml64|**AFLAGS**|
|C derleyicisi|**CC**|cl|**CFLAGS**|
|C++ Derleyicisi|**CPP**|cl|**CPPFLAGS**|
|C++ Derleyicisi|**CXX**|cl|**CXXFLAGS**|
|Kaynak Derleyicisi|**RC**|RC|**RFLAGS**|

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE Makroları](special-nmake-macros.md)
