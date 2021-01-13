---
description: 'Daha fazla bilgi edinin: &lt; cstdalıgn&gt;'
title: '&lt;cstdalign eklendi&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 7727f75ad0627c2a22b856631a776a2ee5426271
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126617"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign eklendi&gt;

Bazı C++ standart kitaplık uygulamalarında, bu üst bilgi C standart kitaplık üst bilgisini içerir \<stdalign.h> ve ilişkili adları `std` ad alanına ekler. Bu üst bilgi MSVC içinde uygulanmadığından, \<cstdalign> üst bilgi uyumluluk makrolarını ve ' ı tanımlar `__alignas_is_defined` `__alignof_is_defined` .

> [!NOTE]
> \<stdalign.h>Üst bilgi C++ ' ta anahtar sözcük olan makroları tanımladığından, bunun da bir etkisi yoktur. \<stdalign.h>Üst bilgi C++ ' da kullanımdan kaldırılmıştır. \<cstdalign>Üst bilgi c++ 17 ' de kullanımdan kaldırılmıştır ve taslak c++ 20 standardına göre kaldırılır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<cstdalign>

**Ad alanı:** std

## <a name="macros"></a>Makrolar

| Makroya | Description |
| - | - |
| `__alignas_is_defined` | Tamsayı sabiti 1 ' i genişleten C uyumluluk makrosu. |
| `__alignof_is_defined` | Tamsayı sabiti 1 ' i genişleten C uyumluluk makrosu. |

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[C++ standart kitaplığına genel bakış](cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)
