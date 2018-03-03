---
title: "CRT nesnelerini DLL sınırlarından geçirirken olası hatalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0355b1c6a2731c9ca82e7ced37ad28f30a881eca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>CRT Nesnelerini DLL Sınırlarından Geçirirken Olası Hatalar
C geçirdiğinizde çalışma zamanı (CRT) dosya tanıtıcısı, yerel ve ortam değişkenleri gibi giriş / çıkış (işlev çağrıları DLL sınır arasında), DLL beklenmeyen davranışları DLL'e çağırma dosyaların yanı sıra, DLL farklı kopyalarını kullanırsanız oluşabilir nesneleri CRT kitaplık.  
  
 Bellek ayırma ilgili bir sorun ortaya çıkabilir (açıkça biriyle `new` veya `malloc`, ya da örtük olarak ile `strdup`, `strstreambuf::str`, vb.) ve ardından boşaltılacak DLL sınır arasında bir işaretçi geçirin. DLL ve kullanıcılarına CRT kitaplıkları farklı kopyalarını kullanıyorsanız bu bellek erişim ihlali veya yığın bozulması neden olabilir.  
  
 Bu sorunun başka bir belirti gibi hata ayıklama sırasında çıktı penceresinde bir hata olabilir:  
  
 YIĞIN []: RtlValidateHeap(#,#) için belirtilen geçersiz adres  
  
## <a name="causes"></a>Nedenler  
 CRT kitaplık her kopyası iş parçacığı yerel depolaması, uygulama ya da DLL tarafından tutulan ayrı ve farklı bir durum vardır. Bu nedenle, ortam değişkenleri, dosya tanıtıcıları gibi CRT nesnelerini ve yerel ayarlar yalnızca uygulama CRT ya da bu nesneler, ayrılmış veya ayarlama DLL kopyası için geçerlidir. DLL ve uygulama istemcilerine CRT kitaplık farklı kopyalarını kullandığınızda, bu CRT nesnelerini DLL sınırından geçirmek ve bunları diğer tarafta doğru çekilmesi için bekler. Bu, özellikle Visual Studio 2015 ve sonraki sürümlerinde Evrensel CRT önce CRT sürümlerinin geçerlidir. Visual C++ 2013 veya daha önce oluşturulmuş Visual Studio her sürümü için sürüme özgü CRT kitaplık vardı. Örneğin, kendi veri yapılarını ve adlandırma kuralları CRT iç uygulama ayrıntılarını her sürümünde farklı. CRT DLL farklı bir sürümü için CRT bir sürümü için derlenmiş kod dinamik olarak bağlama hiçbir zaman desteklenen, ancak bazen, daha tasarıma göre Şanslar tarafından çalışır.  
  
 Ayrıca, her kopyası CRT kitaplık kendi yığın Yöneticisi olduğundan, bir CRT kitaplık bellek ayırma ve işaretçiyi CRT kitaplık farklı bir kopyasını boşaltılacak DLL sınır arasında geçirme yığın bozulması olası bir nedeni vardır. Böylece, CRT nesnelerini sınırından geçirmeden veya bellek ayırır ve DLL dışında boşaltılması bekler, DLL tasarlarken, uygulama istemcileri CRT Kitaplık'ın aynı kopyasını DLL olarak kullanmak için dll kısıtlayın. Normalde yalnızca her ikisi de aynı sürüme CRT DLL yükleme zamanında bağlıysa DLL ve istemcilerine CRT Kitaplık'ın aynı kopyasını kullanın. Visual Studio 2015 ve daha sonra Windows 10 tarafından kullanılan Evrensel CRT kitaplık DLL sürümü artık merkezi olarak dağıtılan bir Windows bileşeni olduğundan ucrtbase.dll, onu aynıdır Visual Studio 2015 ve sonraki sürümler ile oluşturulmuş uygulamalara ait. Ancak, hatta CRT kodu aynı olduğunda, bir yığın farklı yığın kullanan bir bileşen için ayrılan bellek kapalı el olamaz.  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu örnek, bir dosya tanıtıcısı DLL sınırından geçirir.  
  
 DLL ve .exe dosyası CRT tek bir kopyasını paylaştıkları şekilde /MD ile yerleşiktir.  
  
 CRT ayrı bir kopyasını kullanmak için / MT ile yeniden oluşturursanız, sonuçta elde edilen test1Main.exe sonuçları bir erişim ihlali çalışıyor.  
  
```cpp  
// test1Dll.cpp  
// compile with: cl /EHsc /W4 /MD /LD test1Dll.cpp  
#include <stdio.h>  
__declspec(dllexport) void writeFile(FILE *stream)  
{  
   char   s[] = "this is a string\n";  
   fprintf( stream, "%s", s );  
   fclose( stream );  
}  
```  
  
```cpp  
// test1Main.cpp  
// compile with: cl /EHsc /W4 /MD test1Main.cpp test1Dll.lib  
#include <stdio.h>  
#include <process.h>  
void writeFile(FILE *stream);  
  
int main(void)  
{  
   FILE  * stream;  
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );  
   writeFile(stream);  
   system( "type fprintf.out" );  
}  
```  
  
```Output  
this is a string  
```  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu örnekte, ortam değişkenleri DLL sınırından geçirir.  
  
```cpp  
// test2Dll.cpp  
// compile with: cl /EHsc /W4 /MT /LD test2Dll.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
__declspec(dllexport) void readEnv()  
{  
   char *libvar;  
   size_t libvarsize;  
  
   /* Get the value of the MYLIB environment variable. */   
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );  
  
   if( libvar != NULL )  
      printf( "New MYLIB variable is: %s\n", libvar);  
   else  
      printf( "MYLIB has not been set.\n");  
   free( libvar );  
}  
```   
  
```cpp  
// test2Main.cpp  
// compile with: cl /EHsc /W4 /MT test2Main.cpp test2dll.lib   
#include <stdlib.h>  
#include <stdio.h>  
  
void readEnv();  
  
int main( void )  
{  
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );  
   readEnv();  
}  
```  
  
```Output  
MYLIB has not been set.  
```  
  
 CRT yalnızca bir kopyasını kullanılmasını sağlamak amacıyla DLL ve .exe dosyası ile /MD oluşturulmuştur, programın başarıyla çalıştırır ve şu çıkışı üretir:  
  
```  
New MYLIB variable is: c:\mylib;c:\yourlib  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)