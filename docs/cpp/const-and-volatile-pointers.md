---
title: "const ve volatile işaretçiler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebf8d12c7c3b0f9578724fe772f24c0bc8c845ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="const-and-volatile-pointers"></a>const ve volatile İşaretçiler
[Const](../cpp/const-cpp.md) ve [volatile](../cpp/volatile-cpp.md) anahtar sözcükleri değiştirme işaretçileri nasıl işlenir. **Const** işaretçinin bundan sonra değiştirilmeye karşı korunan; anahtar sözcüğü belirtir işaretçinin başlatma sonra değiştirilemez.  
  
 `volatile` anahtar sözcüğü, ondan sonra gelen adla ilişkili değerin, kullanıcı uygulamasındakilerin dışındaki eylemler tarafından değiştirilebileceğini belirtir. Bu nedenle, `volatile` anahtar sözcüğü kesme hizmet yordamlarıyla iletişim kurmak için kullanılan birden fazla işlem veya genel veri alanları tarafından erişilebilen paylaşılan bellekte nesnelerin bildirilmesinde yararlı olur.  
  
 Bir ad `volatile` olarak bildirildiğinde, derleyici değeri program tarafından erişildiğinde her zaman yeniden yükler. Bu, olası iyileştirmeleri önemli ölçüde azaltır. Ancak, bir nesnenin durumu beklenmedik bir şekilde değiştiğinde, yalnızca bu şekilde tahmin edilebilir program performansı sağlanabilir.  
  
 İşaretçi olarak gösterdiği nesne bildirmek için **const** veya `volatile`, formun bildirimi kullanın:  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 İşaretçi değeri bildirmek için — diğer bir deyişle, işaretçinin saklanan gerçek adresi — olarak **const** veya `volatile`, formun bildirimi kullanın:  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 C++ dili nesnenin değiştirilmesine izin atamalarını engeller veya işaretçi bildirilen **const**. Bu tür atamalar, nesne veya işaretçinin birlikte bildirildiği bilgileri kaldırarak orijinal bildirimin amacını ihlal eder. Aşağıdaki bildirimleri dikkate alın:  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 İki nesne önceki bildirimlerini verilen (`cch`, türü **const char**, ve `ch`, türü **char)**, aşağıdaki bildirim/başlatmalarına geçerlidir:  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Aşağıdaki bildirim/başlatmalar hatalıdır.  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 `pch2` bildirimi, sabit bir nesnenin değiştirilebileceği ve bu nedenle izin verilmeyen bir işaretçiyi bildirir. `pch3` bildirimi, nesnenin değil `pointer` öğesinin sabit olduğunu belirtir; bildirime, `pch2` bildirimiyle aynı nedenden ötürü izin verilmez.  
  
 Aşağıdaki sekiz atama, işaretçiyle atama ve önceki bildirimler için işaretçi değerinin değiştirilmesini göstermektedir; şimdilik başlatmanın `pch1` ile `pch8` arasında doğru olduğunu varsayın.  
  
```  
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 İşaretçileri bildirilen `volatile`, veya bir karışımını olarak **const** ve `volatile`, aynı kurala uyacak.  
  
 İşaretçiler **const** nesneleri sık kullanılan işlev bildirimleri gibi:  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Bir işlev önceki deyimi bildirir [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), iki üç bağımsız değişken türü işaretçisinin nerede `char`. Bağımsız değişkenleri başvuruya göre geçirilir ve değer ile işlevi her ikisi de değiştirmek ücretsiz olmayacaktır çünkü `strDestination` ve `strSource` varsa `strSource` olarak bildirilmemiş **const**. Bildirimi `strSource` olarak **const** arayan sağlar `strSource` çağrılan işlev tarafından değiştirilemez.  
  
> [!NOTE]
>  Standart dönüştürme olduğundan *typename*  **\***  için **const** *typename*  **\*** , türünde bir bağımsız değişken geçirmek için yasal **char \***  için [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Ancak tersi geçerli değildir; örtük dönüştürme kaldırmak için mevcut **const** nesne veya işaretçi özniteliği.  
  
 A **const** işaretçi belirli bir türde aynı türde bir işaretçi atanabilir. Ancak, bir işaretçi olmayan **const** atanamaz bir **const** işaretçi. Aşağıdaki kod, doğru ve hatalı atamaları gösterir:  
  
```  
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 Aşağıdaki örnekte, bir nesnenin işaretçisinin işaretçisi varsa bir nesnenin nasıl const olarak bildirileceği gösterilmektedir.  
  
```  
// const_pointer2.cpp  
struct X {  
   X(int i) : m_i(i) { }  
   int m_i;  
};  
  
int main() {  
   // correct  
   const X cx(10);  
   const X * pcx = &cx;  
   const X ** ppcx = &pcx;  
  
   // also correct  
   X const cx2(20);  
   X const * pcx2 = &cx2;  
   X const ** ppcx2 = &pcx2;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşaretçiler](../cpp/pointers-cpp.md)