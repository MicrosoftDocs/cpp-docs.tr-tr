---
description: 'Daha fazla bilgi edinin: #error yönergesi (C/C++)'
title: '##error yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: fd6503de9590893ee0ec53cbbfa59429a0cfdcfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261157"
---
# <a name="error-directive-cc"></a>#error yönergesi (C/C++)

**#Error** yönergesi, derleme zamanında Kullanıcı tarafından belirtilen bir hata iletisini yayar ve sonra derlemeyi sonlandırır.

## <a name="syntax"></a>Syntax

> **#error** *belirteci-dize*

## <a name="remarks"></a>Açıklamalar

Bu yönergenin yaydığı hata iletisinde, *token-string* parametresi bulunur. *Belirteç dize* parametresi makro genişletmeye tabi değildir. Bu yönerge, bir program tutarsızlığına veya bir kısıtlamanın ihlaline neden olan ön işleme sırasında en yararlı seçenektir. Aşağıdaki örnek, ön işleme sırasında hatanın işleyişini gösterir:

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
