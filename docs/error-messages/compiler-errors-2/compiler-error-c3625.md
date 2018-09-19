---
title: Derleyici Hatası C3625 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3625
dev_langs:
- C++
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ebb7a94e807dbd8bbb9e5614f15d03e9b577858
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022617"
---
# <a name="compiler-error-c3625"></a>Derleyici Hatası C3625

'native_type': yerel bir tür, yönetilen veya WinRT türetilemez 'type' yazın

Yönetilen veya WinRT yerel bir sınıfı devralamaz sınıfı. Daha fazla bilgi için [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3625 oluşturur:

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
