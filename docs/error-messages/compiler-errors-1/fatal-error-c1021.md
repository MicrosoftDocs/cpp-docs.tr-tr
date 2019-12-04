---
title: Önemli hata c1021
ms.date: 11/04/2016
f1_keywords:
- C1021
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
ms.openlocfilehash: 861e768563cf737d6925d5753d80cd9269eff4fe
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756896"
---
# <a name="fatal-error-c1021"></a>Önemli hata c1021

geçersiz önişlemci komutu ' String '

`string` geçerli bir [Önişlemci yönergesi](../../preprocessor/preprocessor-directives.md)değil. Hatayı gidermek için, `string`için geçerli bir Önişlemci adı kullanın.

Aşağıdaki örnek c1021 oluşturur:

```cpp
// C1021.cpp
#BadPreProcName    // C1021 delete line
```
