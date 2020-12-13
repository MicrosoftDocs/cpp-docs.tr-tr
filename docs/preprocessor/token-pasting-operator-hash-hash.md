---
description: 'Hakkında daha fazla bilgi edinin: belirteç yapıştırma işleci (# #)'
title: Belirteç yapıştıran işleç (##)
ms.date: 08/29/2019
f1_keywords:
- '##'
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
ms.openlocfilehash: 3bad0a615fdf7c0b3e1e54d16c25e37bf495072c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149675"
---
# <a name="token-pasting-operator-"></a>Belirteç yapıştıran işleç (##)

Bazen birleştirme veya birleştirme operatörü olarak adlandırılan çift sayı işareti veya *belirteç yapıştırma* işleci ( **##** ), nesne benzeri  ve işlev  benzeri makrolarda kullanılır. Ayrı belirteçlerin tek bir belirtece katılmasını sağlar ve bu nedenle makro tanımındaki ilk veya son belirteç olamaz.

Makro tanımında biçimsel bir parametrenin öncesinde veya sonrasında belirteci yapıştırma işleci gelirse, biçimsel parametre hemen genişletilmeyen gerçek bağımsız değişken ile değiştirilir. Makro genişletme, değiştirme işleminden önce bağımsız değişken üzerinde gerçekleştirilmez.

Ardından, *belirteç dizesindeki* belirteç yapıştırma işlecinin her bir oluşumu kaldırılır ve önceki ve sonraki belirteçler birleştirilir. Elde edilen belirtecin geçerli bir belirteç olması gerekir. Geçerliyse, belirteç makro adını temsil ettiği takdirde olası bir değiştirmeye karşı taranır. Tanımlayıcı, bitiştirilmiş belirteçlerin değiştirme işleminden önce programda bilineceği adı temsil eder. Her belirteç, program içerisinde veya derleyici komut satırında tanımlanan bir belirteci temsil eder. İşlecin öncesinden veya arkasından gelen boşluk isteğe bağlıdır.

Bu örnekte, program çıktısı belirtilirken hem dize haline getirme hem de belirteci yapıştırma işleçlerinin kullanımı gösterilmektedir:

```cpp
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;
```

Şunun gibi bir sayısal bağımsız değişkenle bir makro çağrılırsa:

```cpp
paster( 9 );
```

makro şunu oluşturur:

```cpp
printf_s( "token" "9" " = %d", token9 );
```

bu, daha sonra şuna dönüşür:

```cpp
printf_s( "token9 = %d", token9 );
```

## <a name="example"></a>Örnek

```cpp
// preprocessor_token_pasting.cpp
#include <stdio.h>
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;

int main()
{
   paster(9);
}
```

```Output
token9 = 9
```

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci işleçleri](../preprocessor/preprocessor-operators.md)
