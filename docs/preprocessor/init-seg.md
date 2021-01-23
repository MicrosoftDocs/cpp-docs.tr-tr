---
description: pragmaMicrosoft C/C++ ' da init_seg yönergesi hakkında daha fazla bilgi edinin
title: init_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragma, init_seg
- init_seg pragma
- data segment initializing [C++]
no-loc:
- pragma
ms.openlocfilehash: 77ca6f2454ad18c8adcefcddc4cf1f9c0d4f4532
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713590"
---
# <a name="init_seg-no-locpragma"></a>`init_seg` pragma

**C++ özel**

Başlangıç kodunun yürütüldüğü sırayı etkileyen bir anahtar sözcük veya kod bölümü belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma init_seg(`** { **`compiler`** | **`lib`** | **`user`** | "*bölüm-adı*" [ **`,`** *Func-Name* ]} **`)`**

## <a name="remarks"></a>Açıklamalar

Koşullar *segmenti* ve *bölümü* Bu makalede aynı anlama sahiptir.

Genel statik nesneleri başlatmak için kod bazen gerekli olduğundan, nesneleri ne zaman oluþturabileceğinize belirtmeniz gerekir. Özellikle, **`init_seg`** pragma dinamik bağlantı kitaplıkları (dll 'ler) veya başlatma gerektiren kitaplıklarda kullanılması önemlidir.

Seçenekleri **`init_seg`** pragma şunlardır:

**`compiler`**\
Microsoft C çalışma zamanı kitaplığı başlatması için ayrılmıştır. Bu gruptaki nesneler önce oluşturulur.

**`lib`**\
Üçüncü taraf sınıf kitaplığı satıcılarının başlatmaları için kullanılabilir. Bu gruptaki nesneler, hariç işaretlendiklerden sonra **`compiler`** , ancak başkalarından sonra oluşturulur.

**`user`**\
Herhangi bir kullanıcı tarafından kullanılabilir. Bu gruptaki nesneler son olarak oluşturulur.

*Bölüm-adı*\
Başlatma bölümünün açık belirtimine izin verir. Kullanıcı tarafından belirtilen *bölüm adı* içindeki nesneler örtülü olarak oluşturulmamış. Ancak, adresleri *bölüm adı* tarafından adlandırılan bölümüne yerleştirilir.

Verdiğiniz *bölüm adı* , bu modüldeki öğesinden sonra bildirildiği genel nesneleri oluşturacak yardımcı işlevlere işaretçiler içerir pragma .

Bölüm oluştururken kullanmamanız gerekadların bir listesi için, bkz [`/SECTION`](../build/reference/section-specify-section-attributes.md) ..

*Func-adı*\
Program çıktığında yerine çağrılacak işlevi belirtir `atexit` . Bu yardımcı işlev ayrıca [`atexit`](../c-runtime-library/reference/atexit.md) genel nesne için yıkıcıya yönelik bir işaretçi ile çağırır. Formunda bir işlev tanımlayıcısı belirtirseniz pragma ,

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

ardından işleviniz C çalışma zamanı kitaplığı 'nın yerine çağırılır `atexit` . Nesneleri yok etmeye hazırsanız çağrılacak yıkıcılarının bir listesini oluşturmanızı sağlar.

Başlatma işlemini erteetmeniz gerekiyorsa (örneğin, bir DLL 'de), Bölüm adını açık olarak belirtmeyi tercih edebilirsiniz. Kodunuzun ardından her statik nesne için oluşturucuları çağırması gerekir.

Değiştirme için tanımlayıcı etrafında hiç teklif yok `atexit` .

Nesneleriniz, diğer yönergeler tarafından tanımlanan bölümlere yerleştirilmeye devam edecektir `XXX_seg` pragma .

Modülde belirtilen nesneler C çalışma zamanı tarafından otomatik olarak başlatılmaz. Kodunuzun başlatmayı yapması gerekmez.

Varsayılan olarak, `init_seg` bölümler salt okunurdur. Bölüm adı ise `.CRT` , derleyici, okuma, yazma olarak işaretlenmiş olsa bile özniteliği sessizce salt yazılır olarak değiştirir.

**`init_seg`** Bir çeviri biriminde birden çok kez belirtemezsiniz.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
