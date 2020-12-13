---
description: 'Hakkında daha fazla bilgi edinin: çıplak Işlevler için kurallar ve sınırlamalar'
title: Naked İşlevleri için Kurallar ve Sınırlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
ms.openlocfilehash: d5dd1b0b115132b4986e9090537fc94eb2aadc0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340456"
---
# <a name="rules-and-limitations-for-naked-functions"></a>Naked İşlevleri için Kurallar ve Sınırlamalar

**Microsoft'a Özgü**

Aşağıdaki kurallar ve sınırlamalar, çıplak işlevler için geçerlidir:

- **`return`** Deyime izin verilmiyor.

- Yapılandırılmış özel durum Işleme ve C++ özel durum Işleme yapılarına yığın çerçevesinin üzerinde gezinmeleri gerektiğinden izin verilmez.

- Aynı nedenle, herhangi bir biçimi `setjmp` yasaktır.

- `_alloca`İşlevin kullanımı yasaktır.

- Yerel değişkenler için başlatma kodunun Giriş sırasından önce göründüğünden emin olmak için, işlev kapsamında başlatılmış yerel değişkenlere izin verilmez. Özellikle, C++ nesnelerinin bildirimine işlev kapsamında izin verilmez. Ancak, iç içe bir kapsamda başlatılan veriler olabilir.

- Çerçeve işaretçisi iyileştirmesi (/oy derleyicisi seçeneği) önerilmez, ancak çıplak bir işlev için otomatik olarak bastırılır.

- C++ sınıf nesnelerini işlev sözcük temelli kapsamda bildiremezsiniz. Ancak, nesneleri iç içe geçmiş bir blokta bildirebilirsiniz.

- **`naked`** [/Clr](../build/reference/clr-common-language-runtime-compilation.md)ile derlerken anahtar sözcük yok sayılır.

- [__Fastcall](../cpp/fastcall.md) Naked işlevleri için, YAZMAÇ bağımsız değişkenlerinden birine C/C++ kodunda bir başvuru olduğunda, giriş kodu söz konusu değişkenin yığın konumuna kaydın değerlerini depolamalıdır. Örneğin:

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

[Naked Işlev çağrıları](../cpp/naked-function-calls.md)
