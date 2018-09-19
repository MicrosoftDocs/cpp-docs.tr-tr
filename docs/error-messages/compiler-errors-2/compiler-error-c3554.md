---
title: Derleyici Hatası C3554 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3554
dev_langs:
- C++
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b1760607a335d4dd56ec711eef76f5a68550d64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089508"
---
# <a name="compiler-error-c3554"></a>Derleyici Hatası C3554

'decltype' herhangi başka bir tür tanımlayıcısı ile birleştirilemez

Uygun olamaz `decltype()` herhangi bir tür tanımlayıcısı ile anahtar sözcüğü. Örneğin, aşağıdaki kod parçası hatası C3554 verir.

```
int x;
unsigned decltype(x); // C3554
```