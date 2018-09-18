---
title: Derleyici Hatası C3235 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3235
dev_langs:
- C++
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d156a9c1a6cda2ad8bb15e31034927b39a1a82e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027875"
---
# <a name="compiler-error-c3235"></a>Derleyici Hatası C3235

'özelleştirmesi': bir genel sınıfın açık veya kısmı özelleştirmesine izin verilmez

Genel sınıflar açık ya da kısmi uzmanlıklar için kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3235 oluşturur.

```
// C3235.cpp
// compile with: /clr
generic<class T>
public ref class C {};

generic<>
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.
```