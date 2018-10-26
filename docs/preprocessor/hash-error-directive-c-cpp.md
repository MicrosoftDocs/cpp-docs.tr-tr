---
title: '#hata yönergesi (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 143733af9003442996d9f649825f45f93643f536
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078810"
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