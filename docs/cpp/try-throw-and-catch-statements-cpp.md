---
title: try, throw ve catch deyimleri (C++) | Microsoft Docs
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
ms.openlocfilehash: dc5480b461a06d84647b7f139b2bd0ccce550dcd
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462150"
---
# <a name="try-throw-and-catch-statements-c"></a>try, throw ve catch Deyimleri (C++)
Özel durum işlemeyi C++ içinde uygulamak için kullandığınız **deneyin**, **throw**, ve **catch** ifadeler.  
  
 İlk olarak, bir **deneyin** bir özel durum oluşturabilecek bir veya daha fazla deyimi içermek için blok.  
  
 A **throw** ifadesi olağanüstü bir koşul — genellikle bir hata — oluştuğunun bir **deneyin** blok. Herhangi bir türde bir nesne işleneni olarak kullanabileceğiniz bir **throw** ifade. Genellikle, bu nesne, hata hakkında bilgi iletmek için kullanılır. Çoğu durumda, biz kullanmanızı öneririz. [std::exception](../standard-library/exception-class.md) sınıfını veya standart kitaplıkta tanımlanan türetilmiş sınıflardan biri. Bunlardan biri uygun değilse, kendi özel durum sınıfından türetilen öneririz `std::exception`.  
  
 Oluşabilecek özel durumları işlemek için bir veya daha fazla uygulama **catch** bloğunun ardından hemen bir **deneyin** blok. Her **catch** bloğu işleyebileceği özel durumun türünü belirtir.  
  
 Bu örnek gösterir bir **deneyin** bloğunu ve ona ait işleyiciyi. Varsayımında `GetNetworkResource()` verileri bir ağ bağlantısı ve iki özel durum türleri öğesinden türetilen kullanıcı tanımlı sınıflar olduklarını edinme `std::exception`. Tarafından yakalanan özel durumların bildirimi **const** başvuru **catch** deyimi. Özel durumları değere göre oluşturmanız ve sabit başvuruya göre yakalamanız önerilir.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
 Koddan sonra **deneyin** yan tümcesi ise korunan bölümün kod. **Throw** ifade *oluşturur*— diğer bir deyişle, oluşturur — bir özel durum. Sonraki kod bloğu **catch** yan tümcesi özel durum işleyicisidir. Bu işleyici, *yakalar* , oluşturulan özel durum türlerini **throw** ve **catch** ifadeleri uyumludur. Eşleşen türü yöneten kuralların listesi için **catch** blokları bkz [How Catch Blocks değerlendirilir](../cpp/how-catch-blocks-are-evaluated-cpp.md). Varsa **catch** deyimi belirtir bir tür yerine üç nokta (...) **catch** bloğu tüm özel durum türlerini işler. Derleme yaptığınızda [/eha](../build/reference/eh-exception-handling-model.md) seçeneği, bunlar C yapısal özel durumlarını ve sistem tarafından oluşturulan veya uygulama tarafından oluşturulan zaman uyumsuz özel durumları bellek koruması, sıfırla bölme ve kayan nokta ihlalleri gibi içerebilir . Çünkü **catch** blokları eşleşen bir tür bulmak için program sırayla işlenir, üç nokta işleyicisi ilişkili son işleyicisi olmalıdır **deneyin** blok. Kullanım `catch(...)` dikkatli olun; bir programın yakalama bloğu Yakalanan özel duruma ne yapılacağını bilmediği sürece devam etmesine izin verme. Genellikle, bir `catch(...)` bloğu hataları günlüğe kaydetmek ve programın yürütülmesi durdurulmadan önce özel bir temizleme işlemi gerçekleştirmek için kullanılır.  
  
 A **throw** işleneni olmayan bir ifade, işlenmekte olan özel durumu yeniden oluşturur. Bu, özgün özel durumun polimorfik türü bilgilerini koruduğundan, özel durum yeniden oluşturulduğunda bu biçim önerilir. Böyle bir ifade yalnızca kullanılması gereken bir **catch** işleyicisi tarafından çağrılan bir işlevde veya bir **catch** işleyici. Yeniden oluşturulmuş özel durum nesnesi bir kopya değil, özgün özel durum nesnesidir.  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ özel durum işleme](../cpp/cpp-exception-handling.md)   
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [İşlenilmeyen C++ özel durumları](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)