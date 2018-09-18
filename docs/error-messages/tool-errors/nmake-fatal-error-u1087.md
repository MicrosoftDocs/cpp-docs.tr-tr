---
title: NMAKE önemli hatası U1087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1087
dev_langs:
- C++
helpviewer_keywords:
- U1087
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2f0e094c720222990ee90af7de900d8cf6ba4051
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036806"
---
# <a name="nmake-fatal-error-u1087"></a>NMAKE Önemli Hatası U1087

sahip olamaz: ve:: aynı hedef için bağımlılıklar

Bir hedef hem tek-iki nokta belirtilemez (**:**) ve bir çift iki nokta (`::`) bağımlılık.

Bir hedef içinde birden çok açıklama blokları belirtmek için kullanın `::` her bağımlılık satırda.