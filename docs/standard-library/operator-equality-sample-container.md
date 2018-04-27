---
title: operator == (&lt;örnek kapsayıcı&gt;) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
dev_langs:
- C++
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57847dfd58ae18704c6bdade34712d925cfae2ed
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="operator-ltsample-containergt"></a>operator == (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Overloads `operator==` iki nesne şablonu sınıfının Karşılaştırılacak [kapsayıcı](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `left.` [boyutu](../standard-library/container-class-size.md) ` == right.size && equal(left.` [başlamak](../standard-library/container-class-begin.md)`, left.`[son](../standard-library/container-class-end.md)`, right.begin)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
