---
title: Belirteç yapıştıran işleç (##) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '##'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dee802a09fd3ade03ac18cac8556d8073b19eb94
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465417"
---
# <a name="token-pasting-operator-"></a>Belirteç Yapıştıran İşleç (##)
Çift sayı işareti ya da "belirteci yapıştırma" işleci (**##**), bazen "birleştirme" işleci de çağrıldığı hem nesne benzeri hem de işlev benzeri makrolarda kullanılır. Ayrı belirteçlerin tek bir belirteç olarak birleştirilmesini sağlar ve bu nedenle makro tanımında ilk veya son belirteç olamaz.  
  
Makro tanımında biçimsel bir parametrenin öncesinde veya sonrasında belirteci yapıştırma işleci gelirse, biçimsel parametre hemen genişletilmeyen gerçek bağımsız değişken ile değiştirilir. Makro genişletme, değiştirme işleminden önce bağımsız değişken üzerinde gerçekleştirilmez.  
  
Ardından, belirteç yapıştırma işlecinin her örneği *belirteç dizesinde* kaldırılır ve önceki ve onu takip eden belirteçler bitiştirilir. Elde edilen belirtecin geçerli bir belirteç olması gerekir. Geçerliyse, belirteç makro adını temsil ettiği takdirde olası bir değiştirmeye karşı taranır. Tanımlayıcı, bitiştirilmiş belirteçlerin değiştirme işleminden önce programda bilineceği adı temsil eder. Her belirteç, program içerisinde veya derleyici komut satırında tanımlanan bir belirteci temsil eder. İşlecin öncesinden veya arkasından gelen boşluk isteğe bağlıdır.  
  
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
  
```cpp  
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
 
[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)