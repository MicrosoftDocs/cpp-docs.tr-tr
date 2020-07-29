---
title: reinterpret_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- reinterpret_cast_cpp
helpviewer_keywords:
- reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
ms.openlocfilehash: 33da7427adeb0a0cade2a369664d7fbd34790681
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233606"
---
# <a name="reinterpret_cast-operator"></a>reinterpret_cast İşleci

Herhangi bir işaretçinin diğer işaretçi türlerine dönüştürülmesine izin verir. Ayrıca tüm integral türlerinin herhangi bir işaretçi türüne dönüştürülmesini sağlar ve tam tersi de geçerlidir.

## <a name="syntax"></a>Sözdizimi

```
reinterpret_cast < type-id > ( expression )
```

## <a name="remarks"></a>Açıklamalar

İşlecin kötüye kullanılması **`reinterpret_cast`** kolayca güvenli bir şekilde yapılabilir. İstenen dönüştürme doğal olarak alt düzey değilse, diğer atama işleçlerinden birini kullanmalısınız.

**`reinterpret_cast`** İşleci, **`char*`** doğal olarak **`int*`** `One_class*` güvenli olmayan, veya için gibi dönüştürmeler için kullanılabilir `Unrelated_class*` .

Bir öğesinin sonucu, **`reinterpret_cast`** özgün türüne dönüştürülmesinden başka hiçbir şey için güvenli bir şekilde kullanılamaz. Diğer kullanımlar, en iyi, taşınabilir olmayan.

**`reinterpret_cast`** İşleç **`const`** , **`volatile`** , veya **`__unaligned`** özniteliklerini alamaz. Bu öznitelikleri kaldırma hakkında bilgi için bkz. [Const_cast işleci](../cpp/const-cast-operator.md) .

**`reinterpret_cast`** İşleç, null işaretçi değerini hedef türün null işaretçi değerine dönüştürür.

' Nin pratik kullanımı, bir **`reinterpret_cast`** değeri bir dizinle eşleştiren, iki farklı değerin aynı dizinle nadiren bir şekilde bir arada bulunduğu bir şekilde bir dizin ile eşlendiği bir karma işlevdir.

```cpp
#include <iostream>
using namespace std;

// Returns a hash code based on an address
unsigned short Hash( void *p ) {
   unsigned int val = reinterpret_cast<unsigned int>( p );
   return ( unsigned short )( val ^ (val >> 16));
}

using namespace std;
int main() {
   int a[20];
   for ( int i = 0; i < 20; i++ )
      cout << Hash( a + i ) << endl;
}

Output:
64641
64645
64889
64893
64881
64885
64873
64877
64865
64869
64857
64861
64849
64853
64841
64845
64833
64837
64825
64829
```

, **`reinterpret_cast`** İşaretçinin bir integral türü olarak işlenmesine izin verir. Sonuç daha sonra, benzersiz bir dizin (yüksek oranda olasılığa göre benzersiz) oluşturmak için bit kaydırılacağı ve kendisi ile XORed. Sonra bu dizin, işlevin dönüş türüne standart bir C stili atama ile kesilir.

## <a name="see-also"></a>Ayrıca bkz.

[Atama Işleçleri](../cpp/casting-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
