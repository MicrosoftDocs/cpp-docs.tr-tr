---
title: '&lt;cstdalign eklendi&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- cstdalign
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 603a590190c50495aa80f1b41a574149eb8f760a
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68342250"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign eklendi&gt;

Bazı C++ standart kitaplık uygulamalarında bu üst bilgi, stdalıgn. h > C \<standart kitaplığı başlığını içerir ve `std` ilişkili adları ad alanına ekler. Bu üst bilgi MSVC içinde uygulanmadığından, \<cstdalıgn > üst bilgisi uyumluluk makrolarını `__alignas_is_defined` ve `__alignof_is_defined`tanımlar.

> [!NOTE]
> Stdalıgn. h > üst bilgisi, içinde C++anahtar sözcük olan makroları tanımladığından, bunun da bir etkisi yoktur. \< Stdalıgn. h > başlığı ' de C++kullanım dışıdır. \< \<Cstdalıgn > üst bilgisi c++ 17 ' de kullanımdan kaldırılmıştır ve taslak c++ 20 standardında kaldırılmıştır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<cstdalign >

**Ad alanı:** std

## <a name="macros"></a>Makrolar

| Makrosu | Açıklama |
| - | - |
| `__alignas_is_defined` | Tamsayı sabiti 1 ' i genişleten C uyumluluk makrosu. |
| `__alignof_is_defined` | Tamsayı sabiti 1 ' i genişleten C uyumluluk makrosu. |

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)\
[C++Standart kitaplığa genel bakış](cpp-standard-library-overview.md)\
[C++ Standart kitaplıkta iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)
