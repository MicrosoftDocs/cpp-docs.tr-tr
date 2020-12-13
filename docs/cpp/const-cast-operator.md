---
description: Const_cast Işleci hakkında daha fazla bilgi edinin
title: const_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: c0c08402450773368914facb719c4ddf97b7503d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344672"
---
# <a name="const_cast-operator"></a>const_cast İşleci

**`const`** **`volatile`** Sınıfından, ve özniteliklerini kaldırır **`__unaligned`** .

## <a name="syntax"></a>Syntax

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Açıklamalar

Herhangi bir nesne türü işaretçisi veya veri üyesine yönelik bir işaretçi **`const`** ,,, ve niteleyicileri dışında özdeş olan bir türe açıkça dönüştürülebilir **`volatile`** **`__unaligned`** . İşaretçiler ve başvurular için sonuç orijinal nesneye başvuracaktır. Veri üyelerinin işaretçileri için sonuç, veri üyesinin orijinal (atanmamış) işaretçisiyle aynı üyeye başvuracaktır. Başvurulan nesnenin türüne bağlı olarak, elde edilen işaretçi, başvuru veya üye verisinin işaretçisi kullanılarak yapılan yazma işlemi tanımlanmamış davranış oluşturabilir.

**`const_cast`** Sabit bir değişkenin sabit durumunu doğrudan geçersiz kılmak için işlecini kullanamazsınız.

**`const_cast`** İşleç, null işaretçi değerini hedef türün null işaretçi değerine dönüştürür.

## <a name="example"></a>Örnek

```cpp
// expre_const_cast_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CCTest {
public:
   void setNumber( int );
   void printNumber() const;
private:
   int number;
};

void CCTest::setNumber( int num ) { number = num; }

void CCTest::printNumber() const {
   cout << "\nBefore: " << number;
   const_cast< CCTest * >( this )->number--;
   cout << "\nAfter: " << number;
}

int main() {
   CCTest X;
   X.setNumber( 8 );
   X.printNumber();
}
```

İçeren satırda, **`const_cast`** işaretçinin veri türü **`this`** olur `const CCTest *` . **`const_cast`** İşleci, işaretçisinin veri türünü olarak değiştirir ve **`this`** `CCTest *` üyenin değiştirilmesine izin verir `number` . Atama, yalnızca deyimin geri kalanında göründüğü kadar sürer.

## <a name="see-also"></a>Ayrıca bkz.

[Atama Işleçleri](../cpp/casting-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
