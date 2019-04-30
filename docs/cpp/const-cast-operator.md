---
title: const_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- const_cast_cpp
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
ms.openlocfilehash: 389ef84149031fd602ff9ded15d34869258ffd52
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399115"
---
# <a name="constcast-operator"></a>const_cast İşleci

Kaldırır **const**, **geçici**, ve **__unaligned** bir sınıftan öznitelikleri.

## <a name="syntax"></a>Sözdizimi

```
const_cast <type-id> (expression)
```

## <a name="remarks"></a>Açıklamalar

Herhangi bir nesne türünün işaretçisi veya bir veri üyesine bir işaretçi açıkça dışında aynı olan bir türe dönüştürülebilir **const**, **geçici**, ve **__unaligned** niteleyiciler. İşaretçiler ve başvurular için sonuç orijinal nesneye başvuracaktır. Veri üyelerinin işaretçileri için sonuç, veri üyesinin orijinal (atanmamış) işaretçisiyle aynı üyeye başvuracaktır. Başvurulan nesnenin türüne bağlı olarak, elde edilen işaretçi, başvuru veya üye verisinin işaretçisi kullanılarak yapılan yazma işlemi tanımlanmamış davranış oluşturabilir.

Kullanamazsınız **const_cast** sabit değişkenin sabit durumunu doğrudan geçersiz kılmak için işleci.

**Const_cast** işlecini bir null işaretçi değeri hedef türünün boş işaretçi değerine dönüştürür.

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

İçeren satırda **const_cast**, veri türü **bu** işaretçisi `const CCTest *`. **Const_cast** işleci veri türünü değiştirir **bu** işaretçisine `CCTest *`, üyesinin değiştirilmesini `number` değiştirilecek. Atama, yalnızca deyimin geri kalanında göründüğü kadar sürer.

## <a name="see-also"></a>Ayrıca bkz.

[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)