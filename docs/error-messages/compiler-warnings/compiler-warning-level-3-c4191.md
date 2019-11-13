---
title: Derleyici Uyarısı (düzey 3) C4191
ms.date: 11/04/2016
f1_keywords:
- C4191
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
ms.openlocfilehash: cd0d7dc57c8d3c94a52f72b536657bb3ea1c6b3a
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051874"
---
# <a name="compiler-warning-level-3-c4191"></a>Derleyici Uyarısı (düzey 3) C4191

' operator/Operation ': ' expression ' türünden ' Type Required ' öğesine güvenli olmayan dönüştürme

İşlev işaretçileri içeren birkaç işlem güvenli değil olarak kabul edilir:

- Farklı çağırma kurallarına sahip işlev türleri.

- Farklı dönüş kurallarına sahip işlev türleri.

- Farklı boyutlara, tür kategorilerine veya sınıflandırmalara sahip bağımsız değişken veya dönüş türleri.

- Farklı bağımsız değişken listesi uzunlukları (`__cdecl`' de, daha kısa vararg olsa da, daha kısa bir liste olarak daha kısa listeye dönüştürme üzerinde.

- İşleve yönelik işaretçilere karşı veri işaretçisi ( **void** <strong>\*</strong>dışında).

- `reinterpret_cast`bir hata veya uyarı veren diğer tür farkı.

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