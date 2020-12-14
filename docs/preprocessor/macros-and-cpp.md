---
description: 'Daha fazla bilgi edinin: makrolar ve C++'
title: Makrolar ve C++
ms.date: 08/29/2019
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: 2ec4db1e36bf18c23567c8c513bdc5e15ec613a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333432"
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
