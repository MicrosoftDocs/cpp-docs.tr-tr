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
ms.openlocfilehash: 8a37ae011ec2f06a505063678f481e6e41696c86
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401373"
---
# <a name="badcast-exception"></a>bad_cast Özel Durumu
**Bad_cast** tarafından özel durum **dynamic_cast** işleci bir başvuru türüne yapılan başarısız atamanın sonucu olarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirimin **bad_cast** olan:  
  
```cpp 
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Başarısız bir örneği aşağıdaki kodu içeren **dynamic_cast** oluşturan **bad_cast** özel durum.  
  
```cpp 
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
  
```cpp 
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Ardından algılama atama yönünü ters **deneyin** bloğunu şu şekilde:  
  
```cpp 
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [dynamic_cast işleci](../cpp/dynamic-cast-operator.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)