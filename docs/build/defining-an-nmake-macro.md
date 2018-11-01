---
title: NMAKE Makrosu Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: 860a5766e0d766f7426cb6c1a7eaf5db02686aa4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499037"
---
# <a name="defining-an-nmake-macro"></a>NMAKE Makrosu Tanımlama

## <a name="syntax"></a>Sözdizimi

```

macroname=string
```

## <a name="remarks"></a>Açıklamalar

*Makroadı* bir harf, rakam ve alt çizgi (_) en fazla 1024 karakter birleşimi ve çalışması büyük/küçük harfe duyarlıdır. *Makroadı* çağrılan bir makro içerebilir. Varsa *makroadı* oluşur tamamen bir çağrılan makro, çağrılan makrosu, null veya tanımsız olamaz.

`string` Dizi sıfır veya daha fazla karakter olabilir. Boş bir dize sıfır karakter veya yalnızca boşluk veya sekme içerir. `string` Makro çağrısı içerebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Makrolardaki özel karakterler](../build/special-characters-in-macros.md)

[Boş ve tanımlanmamış makrolar](../build/null-and-undefined-macros.md)

[Makroları nerede tanımlamalı](../build/where-to-define-macros.md)

[Makro tanımlarında öncelik](../build/precedence-in-macro-definitions.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Makrolar ve NMAKE](../build/macros-and-nmake.md)