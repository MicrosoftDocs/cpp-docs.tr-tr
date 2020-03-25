---
title: İfade Değerlendirici Hatası CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: f763754299ed9257fb909b49a7a19c6f3ad58681
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184469"
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
