---
title: OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_NESTED
dev_langs:
- C++
helpviewer_keywords:
- OMP_NESTED OpenMP environment variable
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c90878ce96cf1639c983be899ba13eccf1f040e8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376554"
---
# <a name="ompnested"></a>OMP_NESTED

İç içe geçmiş paralellik etkin veya ile devre dışı sürece iç içe geçmiş paralellik, etkin olup olmadığını belirten `omp_set_nested`.

## <a name="syntax"></a>Sözdizimi

```
set OMP_NESTED[=TRUE | =FALSE]
```

## <a name="remarks"></a>Açıklamalar

`OMP_NESTED` Ortam değişkeni tarafından kılınabilir [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) işlevi.

Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

## <a name="example"></a>Örnek

Aşağıdaki komut kümelerini `OMP_NESTED` ortam değişkenini TRUE:

```
set OMP_NESTED=TRUE
```

Aşağıdaki komut, geçerli ayarı görüntüler `OMP_NESTED` ortam değişkeni:

```
set OMP_NESTED
```

## <a name="see-also"></a>Ayrıca Bkz.

[Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)