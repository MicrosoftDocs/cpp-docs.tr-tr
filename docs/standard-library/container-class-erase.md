---
title: Kapsayıcı Sınıfı::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 11e13fc74de779076b40ba338a21a6736eb04e06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62211062"
---
# <a name="container-classerase"></a>Kapsayıcı Sınıfı::erase

> [!NOTE]
> Bu konuda C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsiz bir örnek olarak Visual C++ belgelerinin bulunduğu. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Bir öğeyi siler.

## <a name="syntax"></a>Sözdizimi

```

    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Açıklamalar

İlk üye işlevi tarafından denetlenen dizinin öğeyi kaldırır *_Where*. İkinci üye işlevi öğeleri denetlenen dizinin aralıktaki kaldırır. [`first`, `last`). Hem kaldırılan tüm öğelerin ötesindeki ilk öğeyi belirleyen bir yineleyici döndürür veya [son](../standard-library/container-class-end.md) böyle bir öğe varsa.

Yalnızca bir kopyalama işlemi bir özel durum oluşturursa, üye işlevleri bir özel durum.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)<br/>
