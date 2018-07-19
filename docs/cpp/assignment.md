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
ms.openlocfilehash: 27e78f7429c4d2a0f83ff7184460eb2ae69df129
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960992"
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)