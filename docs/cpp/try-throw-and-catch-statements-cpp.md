---
title: deneyin, throw ve catch deyimleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
dev_langs:
- C++
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fac31e9a31ab560973e986e37b4cf56f5d7e4621
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="try-throw-and-catch-statements-c"></a>try, throw ve catch Deyimleri (C++)
Özel durum işlemeyi C++ içinde uygulamak için kullandığınız `try`, `throw`, ve `catch` ifadeler.  
  
 İlk olarak, kullanın bir `try` bloğu bir özel durum bir veya daha fazla deyimleri alın.  
  
 A `throw` ifade sinyalleri bir olağanüstü durum — genellikle, bir hata — oluştu bir `try` bloğu. Herhangi bir türde bir nesne işleneni kullanabileceğiniz bir `throw` ifade. Genellikle, bu nesne, hata hakkında bilgi iletmek için kullanılır. Çoğu durumda, biz kullanmanız önerilir. [std::exception](../standard-library/exception-class.md) sınıf veya standart Kitaplığı'nda tanımlanan türetilmiş sınıflarından biri. Bunlardan birini uygun değilse, kendi özel durum sınıfından türetilen öneririz `std::exception`.  
  
 Durum oluşturulabilir özel durumları işlemek için bir veya daha fazla uygulama `catch` hemen ardından blokları bir `try` bloğu. Her `catch` bloğu, işleyebilir özel durum türünü belirtir.  
  
 Bu örnek gösteren bir `try` bloğu ve onun işleyicileri. Varsayımında `GetNetworkResource()` bir ağ bağlantısı üzerinden verileri ve iki özel durum türleri öğesinden türetilen kullanıcı tanımlı sınıflar olduklarını edinir `std::exception`. Özel durumlar tarafından yakalanan bildirimi `const` başvuru `catch` deyimi. Özel durumları değere göre oluşturmanız ve sabit başvuruya göre yakalamanız önerilir.  
  
## <a name="example"></a>Örnek  
  
```  
  
MyData md;  
try {  
   // Code that could throw an exception  
   md = GetNetworkResource();  
}  
catch (const networkIOException& e) {  
   // Code that executes when an exception of type  
   // networkIOException is thrown in the try block  
   // ...  
   // Log error message in the exception object  
   cerr << e.what();  
}  
catch (const myDataFormatException& e) {  
   // Code that handles another exception type  
   // ...  
   cerr << e.what();  
}  
  
// The following syntax shows a throw expression  
MyData GetNetworkResource()  
{  
   // ...  
   if (IOSuccess == false)  
      throw networkIOException("Unable to connect");  
   // ...  
   if (readError)  
      throw myDataFormatException("Format error");   
   // ...  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kodun hemen ardından `try` yan tümcesi olan kodun korunmuş bölümü. `throw` İfade *oluşturur*— diğer bir deyişle, başlatır — bir özel durum. Kod bloğu sonra `catch` yan tümcesi olan özel durum işleyici. İşleyici budur, *yakalar* , oluşturulan özel durum türlerini `throw` ve `catch` ifadeleri uyumludur. İçinde türüyle eşleşen yöneten kuralları listesi `catch` blokları, bkz: [nasıl Catch blokları değerlendirilir](../cpp/how-catch-blocks-are-evaluated-cpp.md). Varsa `catch` deyim üç nokta (...) bir türü yerine belirtir `catch` bloğu her türdeki özel durumu işler. İle derleme zaman [/EHa](../build/reference/eh-exception-handling-model.md) seçeneği, bunlar C yapılandırılmış özel durumlar ve bellek koruması sıfırla bölme ve kayan nokta ihlalleri gibi sistem tarafından oluşturulan veya uygulama tarafından üretilen zaman uyumsuz özel içerebilir . Çünkü `catch` blokları eşleşen bir türü bulmak için program sırayla işlenir, bir üç nokta işleyicisi son işleyici ile ilişkili olmalıdır `try` bloğu. Kullanım `catch(...)` dikkatli olun; Yakalanan özel durum işleme catch bloğu bilmediği sürece devam etmek bir programın izin vermeyin. Genellikle, bir `catch(...)` blok hataları günlüğe kaydetmek ve program yürütme durdurulmadan önce özel temizleme gerçekleştirmek için kullanılır.  
  
 A `throw` hiçbir işleneni sahip ifade yeniden şu anda işlenmekte olan özel durum oluşturur. Bu, özgün özel durumun polimorfik türü bilgilerini koruduğundan, özel durum yeniden oluşturulduğunda bu biçim önerilir. Bu tür bir ifade yalnızca kullanılmalıdır bir `catch` işleyici veya çağrılır bir işlevdeki bir `catch` işleyicisi. Yeniden oluşturulmuş özel durum nesnesi bir kopya değil, özgün özel durum nesnesidir.  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions - dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ özel durum işleme](../cpp/cpp-exception-handling.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [İşlenilmeyen C++ ifadeleri](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)