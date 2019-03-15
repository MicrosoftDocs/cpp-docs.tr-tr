---
title: Komut Makroları ve Seçenek Makroları
ms.date: 11/04/2016
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
ms.openlocfilehash: c6dad7b50d265a1460a98747665d48051078163a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824099"
---
# <a name="command-macros-and-options-macros"></a>Komut Makroları ve Seçenek Makroları

Komut makroları, Microsoft ürünleri için önceden tanımlanmıştır. Seçenekler makroları, bu ürünler için seçenekleri temsil eder ve varsayılan olarak tanımlanmamış. Hem önceden tanımlanmış Çıkarsama kurallarında kullanılan ve açıklama blokları veya kullanıcı tanımlı çıkarım kuralları içinde kullanılabilir. Komut makroları kısmını veya tamamını seçenekleri dahil olmak üzere bir komut satırı temsil etmek için tanımlanabilir. Seçenekler makroları tanımsız boş bir dize oluşturur.

|Microsoft Ürün|Komut makrosu|Olarak tanımlanmış|Seçenekleri makrosu|
|-----------------------|-------------------|----------------|-------------------|
|Macro derleyicisi|**FARKLI**|ml|**AFLAGS**|
|Temel derleyici|**BC**|bc|**BFLAGS**|
|C derleyicisi|**CC**|cl|**CFLAGS**|
|C++ Derleyicisi|**CPP**|cl|**CPPFLAGS**|
|C++ Derleyicisi|**CXX**|cl|**CXXFLAGS**|
|Kaynak Derleyicisi|**RC**|RC|**RFLAGS**|

## <a name="see-also"></a>Ayrıca bkz.

[Özel NMAKE Makroları](special-nmake-macros.md)
