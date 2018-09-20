---
title: Varsayılan (OpenMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ea32f473d96c8f48c6628d8f71212269bd6d345
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392624"
---
# <a name="default-openmp"></a>default (OpenMP)

Bir paralel bölgenin içinde kapsamsız değişkenleri davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

```
default(shared | none)
```

## <a name="remarks"></a>Açıklamalar

`shared`, etkin olduğu, `default` yan tümcesi belirtilmediyse, sanki ile belirtilmiş bir paralel bölgenin içinde herhangi bir değişken değerlendirilir anlamına gelir [paylaşılan](../../../parallel/openmp/reference/shared-openmp.md) yan tümcesi. `none` ile kapsamlı olmayan bir paralel bölgenin içinde kullanılan tüm değişkenler anlamına [özel](../../../parallel/openmp/reference/private-openmp.md), [paylaşılan](../../../parallel/openmp/reference/shared-openmp.md), [azaltma](../../../parallel/openmp/reference/reduction.md), [firstprivate](../../../parallel/openmp/reference/firstprivate.md), veya [lastprivate](../../../parallel/openmp/reference/lastprivate.md) yan tümcesi, bir derleyici hatasına neden olur.

`default` Aşağıdaki yönergeleri için geçerlidir:

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)

Daha fazla bilgi için [2.7.2.5 varsayılan](../../../parallel/openmp/2-7-2-5-default.md).

## <a name="example"></a>Örnek

Bkz: [özel](../../../parallel/openmp/reference/private-openmp.md) kullanma örneği için `default`.

## <a name="see-also"></a>Ayrıca Bkz.

[Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)