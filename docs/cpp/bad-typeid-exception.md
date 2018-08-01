---
title: bad_typeid özel durumu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55718522bdbf618fb656eedc5c6afd59bfcaca08
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408592"
---
# <a name="badtypeid-exception"></a>bad_typeid Özel Durumu
**Bad_typeid** tarafından özel durum [typeid işleci](../cpp/typeid-operator.md) zaman için işlenen **TypeID** bir NULL işaretçidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirimin **bad_typeid** olan:  
  
```cpp 
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 Aşağıdaki örnekte gösterildiği **TypeID** atma işleci bir **bad_typeid** özel durum.  
  
```cpp 
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```Output 
Object is NULL  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)