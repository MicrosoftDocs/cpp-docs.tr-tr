---
title: OMP_DYNAMIC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a2a4d660057ab83da39add7fd32bcff3e6d90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392144"
---
# <a name="ompdynamic"></a>OMP_DYNAMIC

Çalışma zamanı OpenMP bir paralel bölgenin içinde iş parçacığı sayısını ayarlayıp ayarlayamayacağını belirler.

## <a name="syntax"></a>Sözdizimi

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

## <a name="remarks"></a>Açıklamalar

`OMP_DYNAMIC` Ortam değişkeni tarafından kılınabilir [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) işlevi.

Varsayılan değer OpenMP standart Visual C++ uygulamasında `OMP_DYNAMIC=FALSE`.

Daha fazla bilgi için [4.3 omp_dynamıc](../../../parallel/openmp/4-3-omp-dynamic.md).

## <a name="example"></a>Örnek

Aşağıdaki komut kümelerini `OMP_DYNAMIC` ortam değişkenini TRUE:

```
set OMP_DYNAMIC=TRUE
```

Aşağıdaki komut, geçerli ayarı görüntüler `OMP_DYNAMIC` ortam değişkeni:

```
set OMP_DYNAMIC
```

## <a name="see-also"></a>Ayrıca Bkz.

[Ortam Değişkenleri](../../../parallel/openmp/reference/openmp-environment-variables.md)