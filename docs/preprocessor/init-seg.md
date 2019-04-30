---
title: init_seg
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
ms.openlocfilehash: 801496739fd9bd2b8a14e699ca4da9fe79f3a28d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383717"
---
# <a name="initseg"></a>init_seg

**C++ özgü**

Başlangıç kodu yürütülür sırası etkiler anahtar sözcük veya kod bölümüne belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )
```

## <a name="remarks"></a>Açıklamalar

Koşulları anlamını *segment* ve *bölümü* bu konudaki birbirinin yerine kullanılabilir.

Genel statik nesnelerin başlatılması kodu yürüten içerebildiğinden, nesnelerin oluşturulması olduğunda tanımlayan bir anahtar belirtmeniz gerekir. Kullanmak özellikle önemlidir **init_seg** pragma dinamik bağlantı kitaplıklarında (DLL'ler) veya başlatma gerektiren bir kitaplık.

Seçenekleri **init_seg** Pragma:

*Derleyici*<br/>
Microsoft C çalışma zamanı kitaplığı başlatma için ayrılmış. Bu gruptaki nesnelere önce oluşturulur.

*lib*<br/>
Sınıf kitaplığı üçüncü taraf satıcıların başlatmalar için kullanılabilir. Bu gruptaki nesnelere olarak işaretlenenler sonra özniteliklerden *derleyici* ancak diğerleri önce.

*Kullanıcı*<br/>
Herhangi bir kullanıcı için kullanılabilir. Bu gruptaki nesnelere son oluşturulur.

*Bölüm adı* başlatma bölümünün açık belirtilmesine izin verir. Kullanıcı tanımlı nesneler *bölüm adı* örtük olarak oluşturulan değildir; ancak, adresleri tarafından adlandırılmış bölüm yerleştirilir *bölüm adı*.

Bölüm adı size bu modülde pragmadan sonraki bildirilen genel nesneler oluşturmak yardımcı işlev işaretçileri içerir.

Kullanmamanız bölüm oluştururken adlarının bir listesi için bkz. [/SECTION](../build/reference/section-specify-section-attributes.md).

*işlev adı* yerine çağrılacak bir işlevi belirtir `atexit` zaman programdan çıkılır. Bu yardımcı işlevi de çağırır [atexit](../c-runtime-library/reference/atexit.md) yok Edicisi genel nesne işaretçisi ile. Bir işlev tanımlayıcı formun pragması yerleştirebilirsiniz belirtirseniz,

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

C çalışma zamanı kitaplığının yerine, işlev çağrılmaz sonra `atexit`. Bu nesneler yok etmek hazır olduğunuzda çağrılması gereken Yıkıcılar listesini oluşturmanıza olanak sağlar.

(Örneğin, bir DLL) başlatma erteleneceği gerekiyorsa bölüm adı açıkça belirtmek tercih edebilirsiniz. Ardından, her bir statik nesne için oluşturucular çağırmanız gerekir.

İçin olan tanımlayıcıyla etrafında vardır `atexit` değiştirme.

Nesnelerinizi hala bir XXX_seg pragmaları tarafından tanımlanan bölümlerde yer alır.

Modülde tanımlanmış nesneler, C çalışma zamanı tarafından otomatik olarak başlatılmayacak. Bu kendiniz yapmak gerekir.

Varsayılan olarak, `init_seg` bölümleri salt okunur. Bölüm adı ise. CRT, derleyici sessiz bir şekilde değiştirir öznitelik salt okunur işaretlenmiş olsa bile yazma.

Belirtemezsiniz **init_seg** bir çeviri birimi içinde birden fazla.

Nesneniz, kod içinde açıkça tanımlanmış bir oluşturucu bir kullanıcı tanımlı oluşturucusu yok olsa bile derleyici birini (örneğin v-table işaretçileri bağlamak) oluşturabilir. Bu nedenle, kodunuz, derleyici tarafından oluşturulan oluşturucuyu çağırmak olacaktır.

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

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)