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
ms.openlocfilehash: dc229a8eae6938cba32787ecbec6a5aa6a17ab47
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383993"
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

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)