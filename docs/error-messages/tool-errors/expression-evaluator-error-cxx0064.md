---
title: İfade değerlendirici hatası CXX0064 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b16133484af5a2225f79c5d293a2c8edd948bdb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025899"
---
# <a name="expression-evaluator-error-cxx0064"></a>İfade Değerlendirici Hatası CXX0064

bağlı sanal üye işlev üzerinde kesme noktası ayarlanamıyor

Bir kesme noktası üzerinde bir sanal üye işlevi bir nesneye bir işaretçi aracılığıyla gibi ayarlandı:

```
pClass->vfunc( int );
```

Bir kesme noktası sınıf girerek bir sanal işlev üzerinde ayarlanabilir:

```
Class::vfunc( int );
```

Bu hata için CAN0064 aynıdır.