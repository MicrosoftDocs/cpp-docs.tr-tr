---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2379'
title: Derleyici hatası C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 4b278040107a026ffd5f7bee79e709519647cb54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174721"
---
# <a name="compiler-error-c2379"></a>Derleyici hatası C2379

biçimsel parametre numarası yükseltildiğinde farklı türe sahip

Belirtilen parametrenin türü, önceki bir bildirimde bulunan türü olan varsayılan yükseltmeler aracılığıyla uyumlu değil. Bu, ANSI C 'de ([/za](../../build/reference/za-ze-disable-language-extensions.md)) bir hata ve Microsoft uzantıları (**/ze**) ile ilgili bir uyarıdır.

Aşağıdaki örnek C2379 oluşturur:

```c
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
