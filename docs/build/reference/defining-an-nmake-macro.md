---
description: 'Hakkında daha fazla bilgi edinin: NMAKE makrosu tanımlama'
title: NMAKE Makrosu Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: 133e05cac2a236a38f6b2d1e719f1b66fd73760d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201644"
---
# <a name="defining-an-nmake-macro"></a>NMAKE Makrosu Tanımlama

## <a name="syntax"></a>Syntax

```

macroname=string
```

## <a name="remarks"></a>Açıklamalar

*Makroadı* , 1.024 karakterlik harflerin, rakamların ve alt çizgilerin (_) bir birleşimidir ve büyük/küçük harfe duyarlıdır. *Makroadı* çağrılan bir makro içerebilir. *Makroadı* tamamen çağrılan bir makrodan oluşuyorsa, çağrılan makro null veya tanımsız olamaz.

`string`Sıfır veya daha fazla karakterden oluşan herhangi bir dizi olabilir. Null dize, sıfır karakter veya yalnızca boşluk veya sekme içeriyor. `string`Makro çağırma içerebilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

[Makrolardaki özel karakterler](special-characters-in-macros.md)

[Boş ve tanımlanmamış makrolar](null-and-undefined-macros.md)

[Makroları nerede tanımlamalı](where-to-define-macros.md)

[Makro tanımlarında öncelik](precedence-in-macro-definitions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve NMAKE](macros-and-nmake.md)
