---
title: const ve volatile işaretçiler
ms.date: 11/19/2019
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
ms.openlocfilehash: c0aafde9070275abcb270710e2d4a7a8d9806267
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246624"
---
# <a name="const-and-volatile-pointers"></a>const ve volatile işaretçiler

[Const](const-cpp.md) ve [volatile](volatile-cpp.md) anahtar sözcükleri işaretçilerin nasıl ele alınacağını değiştirir. **Const** anahtar sözcüğü, işaretçinin başlangıçtan sonra değiştirilemeyeceğini belirtir; işaretçi, bundan sonra değişiklikten korunmaktadır.

**Volatile** anahtar sözcüğü, izleyen adla ilişkili değerin Kullanıcı uygulamasındaki eylemlerle farklı eylemler tarafından değiştirilebileceğini belirtir. Bu nedenle, **geçici** anahtar sözcüğü,, kesme hizmeti yordamları ile iletişim için kullanılan birden çok işlem veya küresel veri alanı tarafından erişilebilen paylaşılan bellekteki nesneleri bildirmek için yararlıdır.

Bir ad **geçici**olarak bildirildiği zaman, derleyici, program tarafından her erişildiğinde değeri bellekten yeniden yükler. Bu, olası iyileştirmeleri önemli ölçüde azaltır. Ancak, bir nesnenin durumu beklenmedik bir şekilde değiştiğinde, yalnızca bu şekilde tahmin edilebilir program performansı sağlanabilir.

İşaretçi tarafından işaret edilen nesneyi **const** veya **volatile**olarak bildirmek için şu biçimde bir bildirim kullanın:

```cpp
const char *cpch;
volatile char *vpch;
```

İşaretçinin değerini (yani, İşaretçisinde depolanan gerçek adresi) **const** veya **volatile**olarak bildirmek için şu biçimde bir bildirim kullanın:

```cpp
char * const pchc;
char * volatile pchv;
```

Dil C++ , **const**olarak belirtilen bir nesne veya işaretçinin değiştirilmesine izin veren atamaları engeller. Bu tür atamalar, nesne veya işaretçinin birlikte bildirildiği bilgileri kaldırarak orijinal bildirimin amacını ihlal eder. Aşağıdaki bildirimleri dikkate alın:

```cpp
const char cch = 'A';
char ch = 'B';
```

İki nesnenin önceki bildirimleri ( **const char**türü`cch`, char türünde `ch` **)** verildiğinde, aşağıdaki bildirim/başlatmalar geçerlidir:

```cpp
const char *pch1 = &cch;
const char *const pch4 = &cch;
const char *pch5 = &ch;
char *pch6 = &ch;
char *const pch7 = &ch;
const char *const pch8 = &ch;
```

Aşağıdaki bildirim/başlatmalar hatalıdır.

```cpp
char *pch2 = &cch;   // Error
char *const pch3 = &cch;   // Error
```

`pch2` bildirimi, sabit bir nesnenin değiştirilebileceği ve bu nedenle izin verilmeyen bir işaretçiyi bildirir. `pch3` bildirimi, işaretçinin nesnenin değil, sabit olduğunu belirtir; `pch2` bildirimine izin verilmeyen bir nedenden dolayı bildirime izin verilmez.

Aşağıdaki sekiz atama, işaretçiyle atama ve önceki bildirimler için işaretçi değerinin değiştirilmesini göstermektedir; şimdilik başlatmanın `pch1` ile `pch8` arasında doğru olduğunu varsayın.

```cpp
*pch1 = 'A';  // Error: object declared const
pch1 = &ch;   // OK: pointer not declared const
*pch2 = 'A';  // OK: normal pointer
pch2 = &ch;   // OK: normal pointer
*pch3 = 'A';  // OK: object not declared const
pch3 = &ch;   // Error: pointer declared const
*pch4 = 'A';  // Error: object declared const
pch4 = &ch;   // Error: pointer declared const
```

**Geçici**olarak veya **const** ve **volatile**'nin bir karışımı olarak belirtilen işaretçiler, aynı kurallara uyar.

**Const** nesnelerinin işaretçileri, genellikle işlev bildirimlerinde aşağıdaki gibi kullanılır:

```cpp
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );
```

Yukarıdaki ifade, üç bağımsız değişkenin ikisi de **char**türü işaretçisiyse [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)bir işlev bildirir. Bağımsız değişkenler değere göre değil, başvuruya göre geçirildiğinden ve `strSource` **const**olarak bildirilmemiş ise, işlev hem `strDestination` hem de `strSource` değiştirmek ücretsizdir. **Const** olarak `strSource` bildirimi, `strSource` çağrılan işlev tarafından değiştirilemeyen çağrıyı yapana sağlar.

> [!NOTE]
> *Typename* <strong>\*</strong> **const** *typename* <strong>\*</strong>'e standart bir dönüştürme olduğundan [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)`char *` türünde bir bağımsız değişken geçirmek geçerlidir. Ancak, tersi doğru değildir; bir nesne veya işaretçiden **const** özniteliğini kaldırmak için örtük dönüştürme yok.

Verilen türün **const** işaretçisi aynı türdeki bir işaretçiye atanabilir. Ancak **const** olmayan bir işaretçi bir **const** işaretçisine atanamaz. Aşağıdaki kod, doğru ve hatalı atamaları gösterir:

```cpp
// const_pointer.cpp
int *const cpObject = 0;
int *pObject;

int main() {
pObject = cpObject;
cpObject = pObject;   // C3892
}
```

Aşağıdaki örnekte, bir nesnenin işaretçisinin işaretçisi varsa bir nesnenin nasıl const olarak bildirileceği gösterilmektedir.

```cpp
// const_pointer2.cpp
struct X {
   X(int i) : m_i(i) { }
   int m_i;
};

int main() {
   // correct
   const X cx(10);
   const X * pcx = &cx;
   const X ** ppcx = &pcx;

   // also correct
   X const cx2(20);
   X const * pcx2 = &cx2;
   X const ** ppcx2 = &pcx2;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[İşaretçiler](pointers-cpp.md)
[ham işaretçiler](raw-pointers.md)