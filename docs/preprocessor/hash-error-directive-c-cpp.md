---
title: '#hata yönergesi (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: c83fc7ef8135ee0cba37a956df47bcab0f796007
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447820"
---
# <a name="error-directive-cc"></a>#error Yönergesi (C/C++)
**#Error** yönergesi, bir kullanıcı tarafından belirtilen hata iletisini derleme zamanında yayar ve derlemeyi sona erdirir.

## <a name="syntax"></a>Sözdizimi

```
#errortoken-string
```

## <a name="remarks"></a>Açıklamalar

Bu yönergenin yaydığı hata iletisi içerir *belirteç dizesinde* parametresi. *Belirteç dizesinde* parametresi makro genişletme uygulanmaz değil. Bu yönerge, programdaki tutarsızlıkları ya da bir kısıtlamanın ihlalini geliştiriciye bildirmek için ön işleme sırasında en çok yararlı yönergedir. Aşağıdaki örnek, ön işleme sırasında hatanın işleyişini gösterir:

```
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>Ayrıca Bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)