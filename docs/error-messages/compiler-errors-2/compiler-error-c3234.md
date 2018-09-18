---
title: Derleyici Hatası C3234 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3234
dev_langs:
- C++
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f701eb20743925913bf0eab754f2788e8bd3a9b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017058"
---
# <a name="compiler-error-c3234"></a>Derleyici Hatası C3234

Genel sınıf bir genel tür parametresinden türetilemez

Genel sınıf bir genel tür parametresinden devralamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3234 oluşturur.

```
// C3234.cpp
// compile with: /clr /c
generic <class T>
public ref class C : T {};   // C3234
// try the following line instead
// public ref class C {};
```