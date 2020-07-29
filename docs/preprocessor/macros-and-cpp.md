---
title: Makrolar ve C++
ms.date: 08/29/2019
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: 3b8721644e49a8bd289939d216c233da3286fd0a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219410"
---
# <a name="macros-and-c"></a>Makrolar ve C++

C++, bazıları ANSI C Önişlemci tarafından sunulan yeni özellikleri sunar. Bu yeni işlevler tür güvenliğini ve dilin öngörülebilirliğini geliştirir:

- C++ ' da, olarak belirtilen nesneler **`const`** sabit ifadelerde kullanılabilir. Programların tür ve değer bilgisine sahip sabitleri bildirmesine izin verir. Hata ayıklayıcı ile simgelenebilir görüntülenebilen numaralandırmalar bildirebilirler. `#define`Sabitleri tanımlamak için Önişlemci yönergesini kullandığınızda, kesin değildir ve tür kullanımı güvenli değildir. **`const`** Program, adresini alan bir ifade içermiyorsa bir nesne için hiçbir depolama alanı ayrılmaz.

- C++ satır içi işlev özelliği, işlev türündeki makroların yerini alır. Makrolara göre satır içi işlevleri kullanmanın yararları şunlardır:

  - Tür güvenliği. Satır içi işlevler normal işlevlerle aynı tür denetimine tâbidir. Makrolar tür açısından güvenli değildir.

  - Yan etkisi olan bağımsız değişkenlerin doğru işlenmesi. Satır içi işlevler, işlev gövdesi girilmeden önce bağımsız değişken olarak sağlanan ifadeleri değerlendirir. Bu nedenle, yan etkileri olan bir ifadenin güvensiz olacağı bir şansınız yoktur.

Satır içi işlevler hakkında daha fazla bilgi için bkz. [inline, __inline, \_ _forceinline](../cpp/inline-functions-cpp.md).

Geriye dönük uyumluluk için, ANSI C ve önceki C++'ta varolan tüm önişlemci özellikleri Microsoft C++ için korunur.

## <a name="see-also"></a>Ayrıca bkz.

[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)
