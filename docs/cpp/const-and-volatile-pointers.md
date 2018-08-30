---
title: const ve volatile işaretçileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52550df1ca89ec1252fc2910bf27598d51302495
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212267"
---
# <a name="const-and-volatile-pointers"></a>const ve volatile İşaretçiler
[Const](../cpp/const-cpp.md) ve [geçici](../cpp/volatile-cpp.md) anahtar sözcükleri, işaretçilerin nasıl değerlendirildiğini değiştirin. **Const** anahtar sözcüğü, işaretçinin başlatma değiştirilemez belirtir; işaretçi bundan sonra değişikliklere karşı korunur.  
  
 **Geçici** anahtar sözcüğünü izleyen adıyla ilişkilendirilen değeri kullanıcı uygulamasındakilerin dışındaki eylemler tarafından değiştirilebileceğini belirtir. Bu nedenle, **geçici** sözcüktür birden fazla işlem veya kesme hizmet yordamlarıyla iletişim için kullanılan genel veri alanları tarafından erişilebilen paylaşılan bellekte nesnelerin bildirilmesinde yararlı olur.  
  
 Ne zaman bir adı bildirilmiş olarak **geçici**, derleyici değeri program tarafından erişildiğinde her zaman yeniden yükler. Bu, olası iyileştirmeleri önemli ölçüde azaltır. Ancak, bir nesnenin durumu beklenmedik bir şekilde değiştiğinde, yalnızca bu şekilde tahmin edilebilir program performansı sağlanabilir.  
  
 İşaretçi tarafından işaret edilen nesneyi bildirmek için **const** veya **geçici**, biçimde bir bildirim kullanın:  
  
```cpp 
const char *cpch;  
volatile char *vpch;  
```  
  
 İşaretçinin değeri bildirmek için — yani işaretçide depolanan gerçek adresi — olarak **const** veya **geçici**, biçimde bir bildirim kullanın:  
  
```cpp 
char * const pchc;  
char * volatile pchv;  
```  
  
 C++ dili, bir nesnenin değiştirilmesine izin atamaları engeller veya işaretçi olarak bildirilen **const**. Bu tür atamalar, nesne veya işaretçinin birlikte bildirildiği bilgileri kaldırarak orijinal bildirimin amacını ihlal eder. Aşağıdaki bildirimleri dikkate alın:  
  
```cpp 
const char cch = 'A';  
char ch = 'B';  
```  
  
 İki nesnenin önceki bildirimleri verildiğinde (`cch`, türü **const char**, ve `ch`, türü **char)**, aşağıdaki bildirim/başlatmalar geçerli olur:  
  
```cpp 
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Aşağıdaki bildirim/başlatmalar hatalıdır.  
  
```cpp 
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 `pch2` bildirimi, sabit bir nesnenin değiştirilebileceği ve bu nedenle izin verilmeyen bir işaretçiyi bildirir. Bildirimi `pch3` işaretçi sabit olduğunu belirtir nesnenin değil; bildirimi aynı nedenden ötürü `pch2` bildirimi izin verilmiyor.  
  
 Aşağıdaki sekiz atama, işaretçiyle atama ve önceki bildirimler için işaretçi değerinin değiştirilmesini göstermektedir; şimdilik başlatmanın `pch1` ile `pch8` arasında doğru olduğunu varsayın.  
  
```cpp 
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 İşaretçileri olarak bildirilen **geçici**, veya bir karışımını olarak **const** ve **geçici**, aynı kurallara uyan.  
  
 İşaretçileri **const** nesneler genellikle kullanılan işlev bildirimlerinde gibi:  
  
```cpp 
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Önceki deyim, bir işlev bildirir [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), burada üç bağımsız değişken işaretçi türüne ikisidir **char**. Bağımsız değişkenleri başvuruya göre geçirilen değere göre işlevi her ikisini birden değiştirmek ücretsiz değil çünkü ve `strDestination` ve `strSource` varsa `strSource` olarak bildirilen değil **const**. Bildirimi `strSource` olarak **const** arayan, garantiler `strSource` çağrılan işlev tarafından değiştirilemez.  
  
> [!NOTE]
> Standart dönüştürme olmadığından *typename* <strong>\*</strong> için **const** *typename* <strong>\*</strong>, türünde bir bağımsız değişken geçmek için yasal `char *` için [strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Ancak tersi doğru değildir; kaldırmak için örtük dönüştürme var **const** özniteliği bir nesne veya işaretçi.  
  
 A **const** belirli bir türden işaretçi aynı türden bir işaretçiye atanabilir. Ancak, bir işaretçi olmayan **const** atanamaz bir **const** işaretçi. Aşağıdaki kod, doğru ve hatalı atamaları gösterir:  
  
```cpp 
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 Aşağıdaki örnekte, bir nesnenin işaretçisinin işaretçisi varsa bir nesnenin nasıl const olarak bildirileceği gösterilmektedir.  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İşaretçiler](../cpp/pointers-cpp.md)