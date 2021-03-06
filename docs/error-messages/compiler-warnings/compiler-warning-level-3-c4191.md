---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4191'
title: Derleyici Uyarısı (düzey 3) C4191
ms.date: 11/04/2016
f1_keywords:
- C4191
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
ms.openlocfilehash: 0a34147a8cdba7e21af706711e5aa433939188ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344243"
---
# <a name="compiler-warning-level-3-c4191"></a>Derleyici Uyarısı (düzey 3) C4191

' operator/Operation ': ' expression ' türünden ' Type Required ' öğesine güvenli olmayan dönüştürme

İşlev işaretçileri içeren birkaç işlem güvenli değil olarak kabul edilir:

- Farklı çağırma kurallarına sahip işlev türleri.

- Farklı dönüş kurallarına sahip işlev türleri.

- Farklı boyutlara, tür kategorilerine veya sınıflandırmalara sahip bağımsız değişken veya dönüş türleri.

- Farklı bağımsız değişken listesi uzunlukları (açık **`__cdecl`** , daha kısa bir şekilde vararg olsa bile)

- **`void`** <strong>\*</strong> İşleve yönelik işaretçilere göre (dışındaki) veri işaretçisi.

- Bir hata veya uyarı veren diğer tür farkı **`reinterpret_cast`** .

Bu işlevin sonuç işaretçisi aracılığıyla çağrılması programınızın kilitlenmesine neden olabilir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4191 oluşturur:

```cpp
// C4191.cpp
// compile with: /W3 /clr
#pragma warning(default: 4191)

void __clrcall f1() { }
void __cdecl   f2() { }

typedef void (__clrcall * fnptr1)();
typedef void (__cdecl   * fnptr2)();

int main() {
   fnptr1 fp1 = static_cast<fnptr1>(&f1);
   fnptr2 fp2 = (fnptr2) &f2;

   fnptr1 fp3 = (fnptr1) &f2;   // C4191
   fnptr2 fp4 = (fnptr2) &f1;   // C4191
};
```
