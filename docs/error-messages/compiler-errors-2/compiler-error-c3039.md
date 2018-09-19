---
title: Derleyici Hatası C3039 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3039
dev_langs:
- C++
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b225103cf45331688a65d4528cadb39e730c75c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098101"
---
# <a name="compiler-error-c3039"></a>Derleyici Hatası C3039

'var': OpenMP 'for' deyimindeki dizin değişkeni bir azaltma değişkeni olamaz

Değişken kullanılamaz örtük olarak özel bir dizin değişkeni olduğundan bir [azaltma](../../parallel/openmp/reference/reduction.md) kapsayan içinde yan tümcesi [paralel](../../parallel/openmp/reference/parallel.md) yönergesi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3039 oluşturur:

```
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```