---
title: NMAKE Önemli Hatası U1001
ms.date: 11/04/2016
f1_keywords:
- U1001
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
ms.openlocfilehash: bfe2edf9c57eda073826a8c161ae0c358f3a6232
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662247"
---
# <a name="nmake-fatal-error-u1001"></a>NMAKE Önemli Hatası U1001

sözdizimi hatası: makroda ' character' geçersiz bir karakter

Verilen karakterin bir makroda görünür, ancak bir harf, sayı veya alt çizgi değildir.

Bu hatanın nedeni eksik iki nokta makro genişletmesinde:

```
syntax error : illegal character '=' in macro
```