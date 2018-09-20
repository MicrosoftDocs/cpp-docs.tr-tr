---
title: firstprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- firstprivate
dev_langs:
- C++
helpviewer_keywords:
- firstprivate OpenMP clause
ms.assetid: db479766-6d3b-4bbd-b28e-b192d826788c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d070b8de3cf0382447c3b8e756140892dcd85edc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387126"
---
# <a name="firstprivate"></a>firstprivate

Paralel yapı önce mevcut olduğundan, her iş parçacığı bir değişkenin kendi örneği olmalıdır ve değişken değişkenin değerini ile başlatılmalıdır belirtir.

## <a name="syntax"></a>Sözdizimi

```
firstprivate(var)
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`var`|Paralel yapı önce mevcut olduğundan ve her bir iş parçacığı Örneğiniz için değişkeni değişkenin değeriyle başlatılır. Birden fazla değişken belirtilirse, değişken adları virgül ile ayırın.|

## <a name="remarks"></a>Açıklamalar

## <a name="remarks"></a>Açıklamalar

`firstprivate` Aşağıdaki yönergeleri için geçerlidir:

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)

- [single](../../../parallel/openmp/reference/single.md)

Daha fazla bilgi için [2.7.2.2 firstprivate](../../../parallel/openmp/2-7-2-2-firstprivate.md).

## <a name="example"></a>Örnek

Kullanma örneği için `firstprivate`, örneğe bakın [özel](../../../parallel/openmp/reference/private-openmp.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)