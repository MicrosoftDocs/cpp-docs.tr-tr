---
title: Naked İşlevleri için Kurallar ve Sınırlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
ms.openlocfilehash: ec5c7d635dbbb63af7177395c5ad08356e1a26f0
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857313"
---
# <a name="rules-and-limitations-for-naked-functions"></a>Naked İşlevleri için Kurallar ve Sınırlamalar

**Microsoft 'a özgü**

Aşağıdaki kurallar ve sınırlamalar, çıplak işlevler için geçerlidir:

- **Return** ifadesine izin verilmiyor.

- Yapılandırılmış özel durum Işleme C++ ve özel durum işleme yapılarına yığın çerçevesinin üzerinde gezinmeleri gerektiğinden izin verilmez.

- Aynı nedenle, herhangi bir `setjmp` biçimi yasaktır.

- `_alloca` işlevinin kullanımı yasaktır.

- Yerel değişkenler için başlatma kodunun Giriş sırasından önce göründüğünden emin olmak için, işlev kapsamında başlatılmış yerel değişkenlere izin verilmez. Özellikle, C++ nesne bildirimine işlev kapsamında izin verilmez. Ancak, iç içe bir kapsamda başlatılan veriler olabilir.

- Çerçeve işaretçisi iyileştirmesi (/oy derleyicisi seçeneği) önerilmez, ancak çıplak bir işlev için otomatik olarak bastırılır.

- Sınıf nesnelerini işlev C++ sözcük temelli kapsamda bildiremezsiniz. Ancak, nesneleri iç içe geçmiş bir blokta bildirebilirsiniz.

- [/Clr](../build/reference/clr-common-language-runtime-compilation.md)ile derlerken **Naked** anahtar sözcüğü yok sayılır.

- [__Fastcall](../cpp/fastcall.md) Naked işlevleri için, YAZMAÇ bağımsız değişkenlerinden birine göre C/C++ Code ' da bir başvuru olduğunda, giriş kodu söz konusu değişkenin yığın konumuna kaydın değerlerini depolamalıdır. Örneğin:

```cpp
// nkdfastcl.cpp
// compile with: /c
// processor: x86
__declspec(naked) int __fastcall  power(int i, int j) {
   // calculates i^j, assumes that j >= 0

   // prolog
   __asm {
      push ebp
      mov ebp, esp
      sub esp, __LOCAL_SIZE
     // store ECX and EDX into stack locations allocated for i and j
     mov i, ecx
     mov j, edx
   }

   {
      int k = 1;   // return value
      while (j-- > 0)
         k *= i;
      __asm {
         mov eax, k
      };
   }

   // epilog
   __asm {
      mov esp, ebp
      pop ebp
      ret
   }
}
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)