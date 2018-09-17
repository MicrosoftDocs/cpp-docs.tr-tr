---
title: NMAKE makrosu tanımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c266a0be1c5ff16b719e9055f79b377d13ffbf3c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715721"
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