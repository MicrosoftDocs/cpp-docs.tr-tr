---
title: Kapsayıcı sınıfı::ERASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d5a817ed259f5bd264d82fc948afa4cdcd70be2e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
