---
title: const_cast işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- const_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- const_cast keyword [C++]
ms.assetid: 4d8bb203-ef33-4a10-9f9f-c64d4fbc1687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 314e8363fafa4f2a6649055f2c608cd5b7edd18c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070086"
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