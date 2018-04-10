---
title: Bağlantıyı belirtmek için extern kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- extern
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C++], linkage to non-C++ functions
- declarations, external
- external linkage, extern modifier
ms.assetid: 1e2f0ae3-ae98-4410-85b5-222d6abc865a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db93feb8c8fad13cf8de082858e68b89f93b5323
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-extern-to-specify-linkage"></a>Bağlantıyı Belirtmek için extern Kullanma
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      extern string-literal { declaration-list }  
extern string-literal declaration  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `extern` anahtar sözcüğü, bir değişken veya işlev bildirir ve dış bağlantısının (adı, tanımlandığı dosya dışındaki dosyalardan görünür) olduğunu belirtir. Bir değişken değiştirilirken, `extern` değişkenin statik süreye sahip olduğunu belirtir (programı başlatıldığında ayrılır ve program sona erdiğinde serbest bırakılır). Değişken veya işlev başka bir kaynak dosyada veya daha sonra aynı dosyada tanımlanabilir. Dosya kapsamındaki değişkenlerin ve işlevlerin bildirimleri varsayılan olarak dıştır.  
  
## <a name="example"></a>Örnek  
  
```  
// specifying_linkage1.cpp  
int i = 1;  
void other();  
  
int main() {  
   // Reference to i, defined above:  
   extern int i;  
}  
  
void other() {  
   // Address of global i assigned to pointer variable:  
   static int *external_i = &i;  
  
   // i will be redefined; global i no longer visible:  
   // int i = 16;  
}  
```  
  
 C++'da `extern` bir dizeyle kullanıldığında, bildirimciler için başka bir dilin bağlantı kurallarının kullanıldığını belirtir. C işlevlerine ve verilerine, yalnızca daha önce C bağlantısına sahip oldukları bildirilmişse erişilebilir. Ancak, ayrı olarak derlenmiş bir çeviri biriminde tanımlanmalıdır.  
  
 Microsoft C++ dizeleri destekler **"C"** ve **"C++"** içinde *değişmez dize değeri* alan. Tüm standart içerme dosyaları, çalışma zamanı kitaplık işlevlerinin C++ programlarında kullanılmasını sağlamak için `extern` "C" sözdizimini kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, C bağlantısına sahip adları bildirmek için alternatif yöntemler gösterilmektedir:  
  
```  
// specifying_linkage2.cpp  
// compile with: /c  
// Declare printf with C linkage.  
extern "C" int printf( const char *fmt, ... );  
  
//  Cause everything in the specified header files  
//   to have C linkage.  
extern "C" {  
   // add your #include statements here  
   #include <stdio.h>  
}  
  
//  Declare the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" {  
   char ShowChar( char ch );  
   char GetChar( void );  
}  
  
//  Define the two functions ShowChar and GetChar  
//   with C linkage.  
extern "C" char ShowChar( char ch ) {  
   putchar( ch );  
   return ch;  
}  
  
extern "C" char GetChar( void ) {  
   char ch;  
  
   ch = getchar();  
   return ch;  
}  
  
// Declare a global variable, errno, with C linkage.  
extern "C" int errno;  
```  
  
 Kullanıcının kabul etmesi gerekir birden fazla bağlantı belirtimi, bir işlev varsa, C ve C++ bağlantı sahip olarak işlevleri bildirmek için bir hata var. Ayrıca, bir işlev için iki bildirimleri bir programda gerçekleşmesi durumunda — bir bağlantı belirtimi ve biri olmadan biriyle — bağlantı belirtimi bildirimiyle ilk olması gerekir. Tüm gereksiz bildirimleri bağlantı belirtimi zaten işlevlerin ilk bildiriminde belirtilen bağlantı verilir. Örneğin:  
  
```  
extern "C" int CFunc1();  
...  
int CFunc1();            // Redeclaration is benign; C linkage is  
                         //  retained.  
  
int CFunc2();  
...  
extern "C" int CFunc2(); // Error: not the first declaration of  
                         //  CFunc2;  cannot contain linkage  
                         //  specifier.  
```  
  
 İşlevler ve nesneler açıkça bildirilen **statik** bileşik bağlantı belirleyici gövdesi içinde (**{}**) statik işlevler veya nesneler; davranılır bağlantı belirleyici göz ardı edilir. Diğer işlevler ve nesneler kullanılarak bildirilen gibi davranmasını `extern` anahtar sözcüğü. (Bkz [bağlantıyı belirtmek için extern kullanma](../cpp/using-extern-to-specify-linkage.md) hakkındaki ayrıntılar için `extern` anahtar sözcüğü.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [extern depolama sınıfı tanımlayıcısı](../c-language/extern-storage-class-specifier.md)   
 [Tanımlayıcıların davranışı](../c-language/behavior-of-identifiers.md)   
 [Bağlantı](../c-language/linkage.md)