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
ms.openlocfilehash: ed5daf503024b2c3f843faeeaedbd9ec9bf64b7c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="constcast-operator"></a>const_cast İşleci
Kaldırır **const**, `volatile`, ve **__unaligned** sınıfından öznitelikleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
const_cast <   
type-id  
 > (   
expression  
 )  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir nesne türü için bir işaretçi veya veri üyesi için bir işaretçi açıkça dışında aynı olan bir türe dönüştürülebilir **const**, `volatile`, ve **__unaligned** niteleyicileri. İşaretçiler ve başvurular için sonuç orijinal nesneye başvuracaktır. Veri üyelerinin işaretçileri için sonuç, veri üyesinin orijinal (atanmamış) işaretçisiyle aynı üyeye başvuracaktır. Başvurulan nesnenin türüne bağlı olarak, elde edilen işaretçi, başvuru veya üye verisinin işaretçisi kullanılarak yapılan yazma işlemi tanımlanmamış davranış oluşturabilir.  
  
 Sabit değişkenin sabit durumunu doğrudan geçersiz kılmak için `const_cast` işlecini kullanamazsınız.  
  
 `const_cast` İşleci hedef türü null işaretçinin değeri boş işaretçi değeri dönüştürür.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
 `const_cast` içeren satırda, `this` işaretçisinin veri türü `const CCTest *` şeklindedir. `const_cast` işleci, `this` işaretçisinin veri türünü `CCTest *` olarak değiştirir ve böylece `number` üyesinin değiştirilmesini sağlar. Atama, yalnızca deyimin geri kalanında göründüğü kadar sürer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Atama İşleçleri](../cpp/casting-operators.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)