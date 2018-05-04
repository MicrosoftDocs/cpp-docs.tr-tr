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
ms.openlocfilehash: 66fd08215c3849bf487578b28b1824afbec14c52
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="assignment"></a>Atama
Atama işleci (**=**) kesinlikle olarak bakıldığında, ikili işleç değil. Bildiriminden herhangi diğer ikili işleç için aşağıdaki istisnalar benzerdir:  
  
-   Statik olmayan üye işlevi olmalıdır. Hayır `operator=` dahil olmayan işlev olarak bildirilebilir.  
  
-   Türetilmiş sınıflar tarafından alınmadı.  
  
-   Varsayılan `operator=` işlevi tarafından oluşturulabilir sınıf türleri derleyici hiçbiri yoksa. (Varsayılan hakkında daha fazla bilgi için `operator=` İşlevler, bkz: [Memberwise atama ve başlatma](http://msdn.microsoft.com/en-us/94048213-8b49-4416-8069-b1b7a6f271f9).)  
  
 Aşağıdaki örnek, bir atama işleci bildirmeyi gösterilmektedir:  
  
```  
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
  
 Sağlanan bağımsız değişken ifadesinin sağ tarafında olduğunu unutmayın. İşleç ataması tamamlandıktan sonra sol tarafındaki değerini döndüren atama işleci davranışını korumak için nesne döndürür. Bu ifadeler gibi yazma sağlar:  
  
```  
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)