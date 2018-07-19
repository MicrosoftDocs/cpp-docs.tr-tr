---
title: Tabanlı işaretçiler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __based
- __based_cpp
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f24c2ad56f91be3ed413f6967e6e40749693fe1b
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948040"
---
# <a name="based-pointers-c"></a>Tabanlı İşaretçiler (C++)
**Microsoft'a özgü**  
  
 **__Based** anahtar sözcüğü, işaretçileri (varolan işaretçilerin gelen uzaklıkları olan işaretçiler) göre işaretçileri bildirmek olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
type __based( base ) declarator   
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşaretçi adreslerine göre işaretçiler, yalnızca kuralar **__based** 32 bit veya 64 bit derlemelerde geçerli anahtar sözcüğü. Microsoft 32 bit C/C++ derleyicisi için temel alınan bir işaretçi, 32 bit işaretçi temeline göre 32 bit uzaklıktadır. Benzer bir kısıtlama, temel alınan bir işaretçinin 64 bit temelden 64 bit uzaklıkta olduğu 64 bit ortamlar için de geçerlidir.  
  
 İşaretçilere göre işaretçilerin bir kullanımı da, işaretçiler içeren kalıcı tanımlayıcılara yöneliktir. İşaretçiye göre işaretçilerden oluşan bağlantılı bir liste diske kaydedilebilir ve daha sonra işaretçiler geçerli kalacak şekilde bellekte başka bir yere yeniden yüklenebilir. Örneğin:  
  
```cpp 
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 `vpBuffer` işaretçisine, programda daha sonra ayrılan belleğin adresi atanır. Bağlantılı liste, `vpBuffer` değerine göre yeniden konumlandırılır.  
  
> [!NOTE]
>  İşaretçiler içeren kalıcı tanımlayıcılar da elde edilebilir kullanarak [bellek eşlemeli dosyalar](http://msdn.microsoft.com/library/windows/desktop/aa366556).  
  
 Temel alınan işaretçinin başvurusu kaldırılırken, temel açıkça belirtilmeli veya bildirim aracılığıyla örtük olarak bilinmelidir.  
  
 Önceki sürümlerle uyumluluk için **_based** eşanlamlıdır **__based**.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda, temel alınan bir işaretçinin temeli değiştirilerek değiştirilmesi gösterilmektedir.  
  
```cpp 
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
```Output  
1  
2  
10  
11  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [alloc_text](../preprocessor/alloc-text.md)