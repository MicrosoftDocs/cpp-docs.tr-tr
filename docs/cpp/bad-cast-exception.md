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
ms.openlocfilehash: b50995ff1d5eb730bf6593679194d32d5300b9d7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37947996"
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
  
```cpp 
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Aşağıdaki kod, `dynamic_cast` özel durumunu oluşturan başarısız bir `bad_cast` örneğini içerir.  
  
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
  
 Özel durum, atanan nesne (bir Şekil) belirtilen atama türünden (Daire) türetilmediği için oluşturulur. Özel durumdan kaçınmak için bu bildirimi ekleyin. **ana**:  
  
```cpp 
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Ardından algılama atama yönünü ters **deneyin** bloğunu şu şekilde:  
  
```cpp 
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dynamic_cast işleci](../cpp/dynamic-cast-operator.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)