---
title: Naked İşlevleri için Kurallar ve Sınırlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
ms.openlocfilehash: c813b97b85469165aae892b0a4cce888112e3dc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267385"
---
# <a name="rules-and-limitations-for-naked-functions"></a>Naked İşlevleri için Kurallar ve Sınırlamalar

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Naked işlevleri için aşağıdaki kurallar ve sınırlamalar uygulanır:

- **Dönüş** deyimi izin verilmez.

- Yığın çerçevesi geriye doğru olduğundan yapılandırılmış özel durum işleme ve C++ özel durum işleme yapılarına izin verilmez.

- Aynı nedenle, herhangi bir biçimde `setjmp` yasaktır.

- Kullanım `_alloca` işlevi kullanılamaz.

- Yerel değişkenler için başlatma kodu yok önce giriş dizisinde görünmesini sağlamak için başlatılmamış yerel değişkenleri işlev kapsamında izin verilmez. Özellikle, C++ nesnelerin bildirimi işlev kapsamında izin verilmiyor. Ancak olabilir başlatılmış veriler iç içe bir kapsam içinde.

- Çerçeve işaretçisi iyileştirme (/Oy derleyici seçeneği) önerilmez, ancak otomatik olarak çıplak bir işlev için engellenir.

- C++ sınıfı nesne işlevi sözlü kapsamda bildiremezsiniz. Ancak, iç içe geçmiş bir bloğu içindeki nesneleri bildirebilirsiniz.

- **Naked** ile derleme yaparken anahtar sözcüğünü sayılır [/CLR](../build/reference/clr-common-language-runtime-compilation.md).

- İçin [__fastcall](../cpp/fastcall.md) çıplak İşlevler, C'de başvuru olduğunda /C++ kod yazmaç bağımsız değişkenlerden biri için giriş kodu, bu değişken için yığın konumunu yazmacına değerlerini depolamanız gerekir. Örneğin:

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)