---
title: NMAKE Makrosu Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
ms.openlocfilehash: b163c3dcbfb079a532bd1babca4ee881407bafc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272236"
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

[Makrolardaki özel karakterler](special-characters-in-macros.md)

[Boş ve tanımlanmamış makrolar](null-and-undefined-macros.md)

[Makroları nerede tanımlamalı](where-to-define-macros.md)

[Makro tanımlarında öncelik](precedence-in-macro-definitions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve NMAKE](macros-and-nmake.md)
