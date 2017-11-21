---
title: "Belirteç yapıştıran işleç (#) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '##'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5573107688968026bf98eda4b18223e35b7b3ef2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="token-pasting-operator-"></a>Belirteç Yapıştıran İşleç (##)
Çift sayı işareti ya da "belirteç yapıştıran" işleci (**##**), bazen "birleştirme" işleci çağırıldığı nesnenin benzeri hem işlevi benzeri makrolarındaki kullanılır. Ayrı belirteçlerin tek bir belirteç olarak birleştirilmesini sağlar ve bu nedenle makro tanımında ilk veya son belirteç olamaz.  
  
 Makro tanımında biçimsel bir parametrenin öncesinde veya sonrasında belirteci yapıştırma işleci gelirse, biçimsel parametre hemen genişletilmeyen gerçek bağımsız değişken ile değiştirilir. Makro genişletme, değiştirme işleminden önce bağımsız değişken üzerinde gerçekleştirilmez.  
  
 Sonra belirteç yapıştıran işleç her oluşumu *belirteci dize* kaldırılır ve önceki ve bunu izleyen belirteçleri birleşir. Elde edilen belirtecin geçerli bir belirteç olması gerekir. Geçerliyse, belirteç makro adını temsil ettiği takdirde olası bir değiştirmeye karşı taranır. Tanımlayıcı, bitiştirilmiş belirteçlerin değiştirme işleminden önce programda bilineceği adı temsil eder. Her belirteç, program içerisinde veya derleyici komut satırında tanımlanan bir belirteci temsil eder. İşlecin öncesinden veya arkasından gelen boşluk isteğe bağlıdır.  
  
 Bu örnekte, program çıktısı belirtilirken hem dize haline getirme hem de belirteci yapıştırma işleçlerinin kullanımı gösterilmektedir:  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 Şunun gibi bir sayısal bağımsız değişkenle bir makro çağrılırsa:  
  
```  
paster( 9 );  
```  
  
 makro şunu oluşturur:  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 bu, daha sonra şuna dönüşür:  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## <a name="example"></a>Örnek  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön İşlemci işleçleri](../preprocessor/preprocessor-operators.md)