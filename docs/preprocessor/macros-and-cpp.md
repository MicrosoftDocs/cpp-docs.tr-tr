---
title: Makrolar ve C++
ms.date: 08/29/2019
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: 8a86fb81544af91d4e844fb08b7948a589976e04
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220794"
---
# <a name="macros-and-c"></a>Makrolar ve C++

C++, bazıları ANSI C Önişlemci tarafından sunulan yeni özellikleri sunar. Bu yeni işlevler tür güvenliğini ve dilin öngörülebilirliğini geliştirir:

- ' C++De, **const** olarak belirtilen nesneler sabit ifadelerde kullanılabilir. Programların tür ve değer bilgisine sahip sabitleri bildirmesine izin verir. Hata ayıklayıcı ile simgelenebilir görüntülenebilen numaralandırmalar bildirebilirler. Sabitleri tanımlamak için Önişlemci `#define` yönergesini kullandığınızda, kesin değildir ve tür kullanımı güvenli değildir. Program, adresini alan bir ifade içermiyorsa bir **const** nesnesi için hiçbir depolama alanı ayrılmaz.

- C++ satır içi işlev özelliği, işlev türündeki makroların yerini alır. Makrolara göre satır içi işlevleri kullanmanın yararları şunlardır:

  - Tür güvenliği. Satır içi işlevler normal işlevlerle aynı tür denetimine tâbidir. Makrolar tür açısından güvenli değildir.

  - Yan etkisi olan bağımsız değişkenlerin doğru işlenmesi. Satır içi işlevler, işlev gövdesi girilmeden önce bağımsız değişken olarak sağlanan ifadeleri değerlendirir. Bu nedenle, yan etkileri olan bir ifadenin güvensiz olacağı bir şansınız yoktur.

Satır içi işlevler hakkında daha fazla bilgi için bkz. [satır içi, \___inline, _forceinline](../cpp/inline-functions-cpp.md).

Geriye dönük uyumluluk için, ANSI C ve önceki C++'ta varolan tüm önişlemci özellikleri Microsoft C++ için korunur.

## <a name="see-also"></a>Ayrıca bkz.

[Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)\
[Makrolar (C/C++)](../preprocessor/macros-c-cpp.md)
