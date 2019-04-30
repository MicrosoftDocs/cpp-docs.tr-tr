---
title: Derleyici Hatası C3554
ms.date: 11/04/2016
f1_keywords:
- C3554
helpviewer_keywords:
- C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
ms.openlocfilehash: 8bc9c465d16aea4714916fa6aa2942eb81c19015
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344563"
---
# <a name="compiler-error-c3554"></a>Derleyici Hatası C3554

'decltype' herhangi başka bir tür tanımlayıcısı ile birleştirilemez

Uygun olamaz `decltype()` herhangi bir tür tanımlayıcısı ile anahtar sözcüğü. Örneğin, aşağıdaki kod parçası hatası C3554 verir.

```
int x;
unsigned decltype(x); // C3554
```