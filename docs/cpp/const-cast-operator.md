---
title: const_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: d2711142e4aa73cc0119949876e7e593067cd45d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180348"
---
# <a name="const_cast-operator"></a>const_cast İşleci

**Const**, **volatile**ve **__unaligned** özniteliklerini bir sınıftan kaldırır.

## <a name="syntax"></a>Sözdizimi

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Açıklamalar

Herhangi bir nesne türü işaretçisi veya veri üyesine yönelik bir işaretçi, **const**, **volatile**ve **__unaligned** niteleyicileri dışında özdeş olan bir türe açıkça dönüştürülebilir. İşaretçiler ve başvurular için sonuç orijinal nesneye başvuracaktır. Veri üyelerinin işaretçileri için sonuç, veri üyesinin orijinal (atanmamış) işaretçisiyle aynı üyeye başvuracaktır. Başvurulan nesnenin türüne bağlı olarak, elde edilen işaretçi, başvuru veya üye verisinin işaretçisi kullanılarak yapılan yazma işlemi tanımlanmamış davranış oluşturabilir.

Sabit bir değişkenin sabit durumunu doğrudan geçersiz kılmak için **const_cast** işlecini kullanamazsınız.

**Const_cast** işleci, null işaretçi değerini hedef türün null işaretçi değerine dönüştürür.

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

**Const_cast**içeren satırda, **Bu** işaretçinin veri türü `const CCTest *`. **Const_cast** işleci, Bu işaretçinin veri türünü `CCTest *`olarak değiştirir, **bu** da üye `number` değiştirilmesine izin verir. Atama, yalnızca deyimin geri kalanında göründüğü kadar sürer.

## <a name="see-also"></a>Ayrıca bkz.

[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
