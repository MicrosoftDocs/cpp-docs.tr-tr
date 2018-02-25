---
title: "Aşırı yükleme &lt; &lt; kendi sınıflarınız için işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eed1ff7819e93236e6baad192887494e6f956ac2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Aşırı yükleme &lt; &lt; kendi sınıflarınız için işleci
Çıkış akışları ekleme kullanın (`<<`) standart türler için işleci. Ayrıca aşırı `<<` kendi sınıflarınız için işleci.  
  
## <a name="example"></a>Örnek  
 `write` İşlevi örnek gösterdi kullanımını bir `Date` yapısı. Veri üyeleri (ay, gün ve yıl) bir görünümden gizli bir C++ sınıf için ideal bir aday tarihidir. Çıkış akışına böyle bir yapı görüntüleme için mantıksal hedefi değil. Bu kod kullanarak bir tarihi görüntüler `cout` nesnesi:  
  
```  
Date dt(1, 2, 92);

cout <<dt;  
```  
  
 Alınacak `cout` kabul etmek için bir `Date` nesne ekleme işleci sonra tanımak için ekleme işleci aşırı bir `ostream` nesneyi soldaki ve `Date` sağdaki. Aşırı yüklenmiş `<<` işleci işlevi bir sınıf arkadaş sonra bildirilmelidir `Date` içindeki özel verilere erişebilmesi için bir `Date` nesnesi.  
  
```  
// overload_date.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Date  
{  
    int mo, da, yr;  
public:  
    Date(int m, int d, int y)  
    {  
        mo = m; da = d; yr = y;  
    }  
    friend ostream& operator<<(ostream& os, const Date& dt);  
};  
  
ostream& operator<<(ostream& os, const Date& dt)  
{  
    os << dt.mo << '/' << dt.da << '/' << dt.yr;  
    return os;  
}  
  
int main()  
{  
    Date dt(5, 6, 92);  
    cout << dt;  
}  
```  
  
```Output  
5/6/92  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Aşırı yüklenmiş işleci özgün bir başvuru döndürür `ostream` eklemeleri birleştirebilirsiniz anlamına gelir nesnesi:  
  
```  
cout <<"The date is" <<dt <<flush;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkış Akışları](../standard-library/output-streams.md)

