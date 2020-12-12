---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0064'
title: İfade Değerlendirici Hatası CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 58356a48fc52ee479c92cf5d65494763c3fc4adb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173200"
---
# <a name="expression-evaluator-error-cxx0064"></a>İfade Değerlendirici Hatası CXX0064

bağlı sanal üye işlevinde kesme noktası ayarlanamıyor

Bir sanal üye işlevinde bir nesne işaretçisi aracılığıyla bir kesme noktası ayarlandı, örneğin:

```
pClass->vfunc( int );
```

Bir kesme noktası, sınıfı girilerek bir sanal işlevde ayarlanabilir, örneğin:

```
Class::vfunc( int );
```

Bu hata CAN0064 ile aynıdır.
