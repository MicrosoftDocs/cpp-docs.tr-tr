---
title: Atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6343d7be23e633fe383343bd7f154d5cc9bb234
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407617"
---
# <a name="assignment"></a>Atama
Atama işleci (**=**), NET olarak söylemek gerekirse, ikili bir işleçtir. Aşağıdaki istisnalar herhangi diğer ikili işlecine bildiriminden aynıdır:  
  
-   Statik olmayan üye işlevi olmalıdır. Hayır **işleç =** değiştiricilere işlevi olarak bildirilebilir.  
  
-   Türetilmiş sınıflar tarafından alınmadı.  
  
-   Varsayılan **işleç =** işlevi oluşturulabilir sınıf türleri için derleyici tarafından yoksa.  
  
 Aşağıdaki örnek, bir atama işleci bildirmek verilmektedir:  
  
```cpp 
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 Sağlanan bağımsız değişken ifadesinin sağ tarafı olduğunu unutmayın. İşleci atama işlemi tamamlandıktan sonra sol tarafındaki değerini döndüren bir atama işleci davranışı korumak için nesneyi döndürür. Bu ifadeler gibi yazma sağlar:  
  
```cpp 
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)