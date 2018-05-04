---
title: bad_cast özel durumu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c09754e44b2cf1d7bda4bde35b8d76335d96711
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="badcast-exception"></a>bad_cast Özel Durumu
`bad_cast` özel durumu, başvuru türüne yapılan başarısız atamanın sonucu olarak `dynamic_cast` işleci tarafından oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `bad_cast` arabirimi şöyledir:  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Aşağıdaki kod, `dynamic_cast` özel durumunu oluşturan başarısız bir `bad_cast` örneğini içerir.  
  
```  
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 Özel durum, atanan nesne (bir Şekil) belirtilen atama türünden (Daire) türetilmediği için oluşturulur. Özel durumdan kaçınmak için bu bildirimleri `main` öğesine ekleyin:  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Ardından `try` bloğunda atama yönünü aşağıdaki gibi ters çevirin:  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dynamic_cast işleci](../cpp/dynamic-cast-operator.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)