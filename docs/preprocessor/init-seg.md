---
description: 'Daha fazla bilgi edinin: init_seg pragma'
title: init_seg pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
ms.openlocfilehash: cab1c82acd3e06a0ace4d55be3ce82e8fd7aed1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236470"
---
# <a name="init_seg-pragma"></a>init_seg pragması

**C++ özel**

Başlangıç kodunun yürütüldüğü sırayı etkileyen bir anahtar sözcük veya kod bölümü belirtir.

## <a name="syntax"></a>Syntax

> **#pragma init_seg (** { **derleyici**  |  **kitaplığı**  |  **kullanıcısı** | "*bölüm-adı*" [ **,** *Func-Name* ]} **)**

## <a name="remarks"></a>Açıklamalar

Koşullar *segmenti* ve *bölümü* Bu makalede aynı anlama sahiptir.

Genel statik nesneleri başlatmak için kod bazen gerekli olduğundan, nesneleri ne zaman oluþturabileceğinize belirtmeniz gerekir. Özellikle, dinamik bağlantı kitaplıkları (dll 'Ler) veya başlatma gerektiren kitaplıklarda **init_seg** pragma kullanılması önemlidir.

**İnit_seg** pragma seçenekleri şunlardır:

**Derleyici**\
Microsoft C çalışma zamanı kitaplığı başlatması için ayrılmıştır. Bu gruptaki nesneler önce oluşturulur.

**LIB**\
Üçüncü taraf sınıf kitaplığı satıcılarının başlatmaları için kullanılabilir. Bu gruptaki nesneler, **derleyici** olarak işaretlenenler, ancak diğerlerinden önce oluşturulur.

**kullanıcısını**\
Herhangi bir kullanıcı tarafından kullanılabilir. Bu gruptaki nesneler son olarak oluşturulur.

*Bölüm-adı*\
Başlatma bölümünün açık belirtimine izin verir. Kullanıcı tarafından belirtilen *bölüm adı* içindeki nesneler örtülü olarak oluşturulmamış. Ancak, adresleri *bölüm adı* tarafından adlandırılan bölümüne yerleştirilir.

Verdiğiniz *bölüm adı* , bu modüldeki pragma öğesinden sonra belirtilen genel nesneleri oluşturacak yardımcı işlevlere işaretçiler içerir.

Bölüm oluştururken kullanmamanız gerekadların bir listesi için, bkz. [/section](../build/reference/section-specify-section-attributes.md).

*Func-adı*\
Program çıktığında yerine çağrılacak işlevi belirtir `atexit` . Bu yardımcı işlev Ayrıca, genel nesne için yok edicinin işaretçisi ile birlikte [atexit](../c-runtime-library/reference/atexit.md) 'i çağırır. Formun pragma öğesinde bir işlev tanımlayıcısı belirtirseniz,

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

ardından işleviniz C çalışma zamanı kitaplığı 'nın yerine çağırılır `atexit` . Nesneleri yok etmeye hazırsanız çağrılacak yıkıcılarının bir listesini oluşturmanızı sağlar.

Başlatma işlemini erteetmeniz gerekiyorsa (örneğin, bir DLL 'de), Bölüm adını açık olarak belirtmeyi tercih edebilirsiniz. Kodunuzun ardından her statik nesne için oluşturucuları çağırması gerekir.

Değiştirme için tanımlayıcı etrafında hiç teklif yok `atexit` .

Nesneleriniz, diğer pragmalar tarafından tanımlanan bölümlere yerleştirilmeye devam edecektir `XXX_seg` .

Modülde belirtilen nesneler C çalışma zamanı tarafından otomatik olarak başlatılmaz. Kodunuzun başlatmayı yapması gerekmez.

Varsayılan olarak, `init_seg` bölümler salt okunurdur. Bölüm adı ise `.CRT` , derleyici, okuma, yazma olarak işaretlenmiş olsa bile özniteliği sessizce salt yazılır olarak değiştirir.

Çeviri biriminde **init_seg** birden çok kez belirtemezsiniz.

Nesneniz, kodda açıkça tanımlanmış bir Kullanıcı tanımlı oluşturucuya sahip olmasa da, derleyici sizin için bir tane oluşturabilir. Örneğin, sanal tablo işaretçilerini bağlamak için bir tane oluşturabilir. Gerektiğinde, kodunuz derleyici tarafından oluşturulan oluşturucuyu çağırır.

## <a name="example"></a>Örnek

```cpp
// pragma_directive_init_seg.cpp
#include <stdio.h>
#pragma warning(disable : 4075)

typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors we need to call
PF pfx[200];    // pointers to destructors.

int myexit (PF pf) {
   pfx[cxpf++] = pf;
   return 0;
}

struct A {
   A() { puts("A()"); }
   ~A() { puts("~A()"); }
};

// ctor & dtor called by CRT startup code
// because this is before the pragma init_seg
A aaaa;

// The order here is important.
// Section names must be 8 characters or less.
// The sections with the same name before the $
// are merged into one section. The order that
// they are merged is determined by sorting
// the characters after the $.
// InitSegStart and InitSegEnd are used to set
// boundaries so we can find the real functions
// that we need to call for initialization.

#pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;

#pragma section(".mine$z",read)
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;

// The comparison for 0 is important.
// For now, each section is 256 bytes. When they
// are merged, they are padded with zeros. You
// can't depend on the section being 256 bytes, but
// you can depend on it being padded with zeros.

void InitializeObjects () {
   const PF *x = &InitSegStart;
   for (++x ; x < &InitSegEnd ; ++x)
      if (*x) (*x)();
}

void DestroyObjects () {
   while (cxpf>0) {
      --cxpf;
      (pfx[cxpf])();
   }
}

// by default, goes into a read only section
#pragma init_seg(".mine$m", myexit)

A bbbb;
A cccc;

int main () {
   InitializeObjects();
   DestroyObjects();
}
```

```Output
A()
A()
A()
~A()
~A()
~A()
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
