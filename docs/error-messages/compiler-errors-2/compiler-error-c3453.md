---
title: Derleyici Hatası C3453 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3453
dev_langs:
- C++
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c35c039727cba004db879aea02c086cea4ddcec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068816"
---
# <a name="compiler-error-c3453"></a>Derleyici Hatası C3453

'attribute': öznitelik 'assembly' niteleyicisi eşleşmediğinden uygulanmadı

Derleme veya modül düzeyinde öznitelikleri yalnızca tek başına yönergeler belirtilebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3453 oluşturur.

```
// C3453.cpp
// compile with: /clr /c
[assembly:System::CLSCompliant(true)]   // C3453
// try the following line instead
// [assembly:System::CLSCompliant(true)];
ref class X {};
```