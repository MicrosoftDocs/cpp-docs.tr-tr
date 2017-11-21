---
title: "Address-of işleci: &amp; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '&'
dev_langs: C++
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d542c508b84da14d4f628796ae5fd42983db0114
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="address-of-operator-amp"></a>Address-of işleci:&amp;
## <a name="syntax"></a>Sözdizimi  
  
```  
& cast-expression  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Address-of birli işleci (**&**), işlenen adresini alır. Address-of işleci işleneni işlevi Belirleyicisi ya da bir bit alanı değildir ve ile bildirilmemiş bir nesne atayan bir l-değeri olabilir **kaydetmek** depolama sınıfı tanımlayıcısı.  
  
 Address-of işleci yalnızca temel, yapısı, sınıf, değişkenlerle uygulanabilir veya dizi başvuruları dosya kapsam düzeyinde veya çok bildirilen birleşim türlerini alt indisli bir dizi. Bu ifadelerde address-of işleci içermeyen bir sabit ifadesine eklenecek veya adres, ifadesinden çıkarılır.  
  
 Uygulandığında işlevler veya l değerleri, ifadenin sonucu için bir işaretçi türü (r) işleneni türünden türetilir. Örneğin, işlenen türü ise `char`, ifade türü işaretçinin sonucudur `char`. Uygulanan address-of işleci, **const** veya `volatile` nesneleri, değerlendiren **const** `type`  **\***  veya `volatile` `type`  **\*** , burada `type` özgün nesne türüdür.  
  
 Ne zaman address-of işleci uygulanan bir [tam adı](http://msdn.microsoft.com/en-us/3fefb16d-8120-4627-8b3f-3d90fbdcd1df), sonuç bağlıdır *tam adının* statik bir üyenin belirtir. Bu durumda, üye bildiriminde belirtilen tür için bir işaretçi sonucudur. Üye statik değilse sonucu gösteren bir işaretçidir üye *adı* tarafından gösterilen sınıfının *tam-sınıfı-adının*. (Bkz [birincil ifadeler](../cpp/primary-expressions.md) hakkında daha fazla bilgi için *tam-sınıfı-adının*.) Aşağıdaki kod parçası, nasıl sonucu, üye statik olmasına bağlı olarak farklılık gösterir:  
  
```  
// expre_Address_Of_Operator.cpp  
// C2440 expected  
class PTM {  
public:  
           int   iValue;  
    static float fValue;  
};  
  
int main() {  
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static  
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static  
   float *spfValue     = &PTM::fValue;  // OK  
}  
```  
  
 Bu örnekte, ifade `&PTM::fValue` verir türü `float *` türü yerine `float PTM::*` çünkü `fValue` statik bir üyesidir.  
  
 Yalnızca işlevi'nın hangi sürümü başvurulan açık olduğunda, aşırı yüklenen bir işlevin adresini alınabilir. Bkz: [işlev aşırı yüklemesi](function-overloading.md) belirli bir adresi elde etme hakkında bilgi için işlev aşırı yüklendi.  
  
 Address-of işleci için bir başvuru türü uygulama işleç başvurusu bağlandığı nesnesine uygulama aynı sonucu verir. Örneğin:  
  
## <a name="example"></a>Örnek  
  
```  
// expre_Address_Of_Operator2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   double d;        // Define an object of type double.  
   double& rd = d;  // Define a reference to the object.  
  
   // Obtain and compare their addresses  
   if( &d == &rd )  
      cout << "&d equals &rd" << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
&d equals &rd  
```  
  
 Aşağıdaki örnek, bir işlev işaretçisi bağımsız değişken geçirmek için address-of işleci kullanır:  
  
```  
// expre_Address_Of_Operator3.cpp  
// compile with: /EHsc  
// Demonstrate address-of operator &  
  
#include <iostream>  
using namespace std;  
  
// Function argument is pointer to type int  
int square( int *n ) {  
   return (*n) * (*n);  
}  
  
int main() {  
   int mynum = 5;  
   cout << square( &mynum ) << endl;   // pass address of int  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
25  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birli işleçli ifadeler](../cpp/expressions-with-unary-operators.md)   
 [C++ yerleşik işleçleri, öncelik ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Yöneltmesi ve adresi-of işleçleri](../c-language/indirection-and-address-of-operators.md)
