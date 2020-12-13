---
description: 'Daha fazla bilgi edinin: const ve volatile işaretçileri'
title: const ve volatile işaretçiler
ms.date: 11/19/2019
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
ms.openlocfilehash: 142c6b83c242af969c5f6e1494a56e9598cf537d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344685"
---
# <a name="const-and-volatile-pointers"></a>const ve volatile işaretçiler

[Const](const-cpp.md) ve [volatile](volatile-cpp.md) anahtar sözcükleri işaretçilerin nasıl ele alınacağını değiştirir. **`const`** Anahtar sözcüğü, işaretçinin başlangıçtan sonra değiştirilemeyeceğini belirtir; işaretçi bundan sonra değişiklikten korunur.

**`volatile`** Anahtar sözcüğü, izleyen adla ilişkili değerin Kullanıcı uygulamasındaki eylemlerle farklı eylemler tarafından değiştirilebileceğini belirtir. Bu nedenle **`volatile`** anahtar sözcüğü, birden fazla işlem veya kesme hizmeti yordamlarına iletişim için kullanılan genel veri alanı tarafından erişilebilen paylaşılan bellekteki nesneleri bildirmek için yararlıdır.

Bir ad olarak bildirildiği zaman **`volatile`** derleyici, program tarafından her erişildiğinde değeri bellekten yeniden yükler. Bu, olası iyileştirmeleri önemli ölçüde azaltır. Ancak, bir nesnenin durumu beklenmedik bir şekilde değiştiğinde, yalnızca bu şekilde tahmin edilebilir program performansı sağlanabilir.

İşaretçi tarafından işaret edilen nesneyi veya olarak bildirmek için şu **`const`** **`volatile`** biçimde bir bildirim kullanın:

```cpp
const char *cpch;
volatile char *vpch;
```

İşaretçinin değerini (yani, İşaretçisinde depolanan gerçek adresi, veya gibi) bildirmek için **`const`** **`volatile`** formun bir bildirimini kullanın:

```cpp
char * const pchc;
char * volatile pchv;
```

C++ dili, olarak belirtilen bir nesne veya işaretçinin değiştirilmesine izin veren atamaları engeller **`const`** . Bu tür atamalar, nesne veya işaretçinin birlikte bildirildiği bilgileri kaldırarak orijinal bildirimin amacını ihlal eder. Aşağıdaki bildirimleri dikkate alın:

```cpp
const char cch = 'A';
char ch = 'B';
```

İki nesnenin önceki bildirimleri ( `cch` **const char** türünde ve `ch` **char türünde)** verildiğinde, aşağıdaki bildirim/başlatmalar geçerlidir:

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

`pch2` bildirimi, sabit bir nesnenin değiştirilebileceği ve bu nedenle izin verilmeyen bir işaretçiyi bildirir. Bildirimi, `pch3` işaretçinin nesne değil, sabit olduğunu belirtir; bildirime izin verilmeyen bir nedenden dolayı bildirime izin verilmez `pch2` .

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

**`volatile`** Veya karışımı olarak belirtilen işaretçiler, **`const`** **`volatile`** aynı kurallara uyar.

Nesne işaretçileri **`const`** , genellikle işlev bildirimlerinde aşağıdaki gibi kullanılır:

```cpp
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );
```

Yukarıdaki ifade, üç bağımsız değişkenin ikisi de işaretçisiyse [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)bir işlev bildirir **`char`** . Bağımsız değişkenler değere göre değil, başvuruya göre geçirildiğinden ve `strDestination` `strSource` olarak bildirilmemiş ise, işlev her ikisini de değiştirmek ücretsizdir `strSource` **`const`** . Bildirimi, `strSource` **`const`** `strSource` çağrılan işlev tarafından değiştirilemeyen çağıranı sağlar.

> [!NOTE]
> *TypeName* 'ten TypeName 'e standart bir dönüştürme olduğundan <strong>\*</strong> **`const`**  <strong>\*</strong> , strcpy_s türünde bir bağımsız değişken geçirmek geçerlidir `char *` . [](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) Ancak, tersi doğru değildir; **`const`** bir nesne veya işaretçiden özniteliği kaldırmak için örtük dönüştürme yok.

**`const`** Verilen türdeki bir işaretçiye aynı türdeki bir işaretçiye atama uygulanabilir. Ancak, işaretçi olmayan bir işaretçi **`const`** bir **`const`** işaretçiye atanamaz. Aşağıdaki kod, doğru ve hatalı atamaları gösterir:

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
 [Ham işaretçiler](raw-pointers.md)
