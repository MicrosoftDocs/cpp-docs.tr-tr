---
title: Derleyici Uyarısı (düzey 4) C4212
ms.date: 11/04/2016
f1_keywords:
- C4212
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
ms.openlocfilehash: d33e5c60bac657060ffef2a43686a5f737eb11cc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161314"
---
# <a name="compiler-warning-level-4-c4212"></a>Derleyici Uyarısı (düzey 4) C4212

Standart olmayan uzantı kullanıldı: işlev bildirimi kullanılan üç nokta

İşlev prototipi değişken sayıda bağımsız değişkene sahiptir. İşlev tanımı değil.

Aşağıdaki örnek C4212 oluşturur:

```c
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```
