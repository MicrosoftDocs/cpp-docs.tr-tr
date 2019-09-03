---
title: '##error yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: bfb5c18f20319e6e6d345f28d3e1850714334b71
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216115"
---
# <a name="error-directive-cc"></a>#error yönergesi (C/C++)

**#Error** yönergesi, derleme zamanında Kullanıcı tarafından belirtilen bir hata iletisini yayar ve sonra derlemeyi sonlandırır.

## <a name="syntax"></a>Sözdizimi

> **#error** *belirteç-dize*

## <a name="remarks"></a>Açıklamalar

Bu yönergenin yaydığı hata iletisinde, *token-string* parametresi bulunur. *Belirteç dize* parametresi makro genişletmeye tabi değildir. Bu yönerge, bir program tutarsızlığına veya bir kısıtlamanın ihlaline neden olan ön işleme sırasında en yararlı seçenektir. Aşağıdaki örnek, ön işleme sırasında hatanın işleyişini gösterir:

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci yönergeleri](../preprocessor/preprocessor-directives.md)
