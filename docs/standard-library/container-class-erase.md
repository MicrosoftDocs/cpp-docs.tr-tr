---
title: Kapsayıcı sınıfı::ERASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 368b722f03a68445ddd016705aa8bebc6f33e6f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842618"
---
# <a name="container-classerase"></a>Kapsayıcı Sınıfı::erase

> [!NOTE]
> Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

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

İlk üye işlevi gösterdiği denetimli sırasının öğeyi kaldırır *_Where*. İkinci üye işlevi denetlenen sıradaki aralığında kaldırır [`first`, `last`). Her ikisi de kaldırıldı, herhangi bir öğenin dışında kalan ilk öğe atayan bir yineleyici dönün veya [son](../standard-library/container-class-end.md) böyle bir öğe varsa.

Yalnızca bir kopyalama işlemi bir özel durum oluşturursa üye işlevleri bir özel durum.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)<br/>
