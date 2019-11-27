---
title: try, throw ve catch Deyimleri (C++)
ms.date: 11/04/2016
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
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
ms.openlocfilehash: 31ed5f7a17b9b45dbbecf5ccb29d2b51a7635eaa
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245137"
---
# <a name="try-throw-and-catch-statements-c"></a>try, throw ve catch Deyimleri (C++)

' C++De özel durum işlemeyi uygulamak için, **TRY**, **throw**ve **catch** ifadelerini kullanırsınız.

İlk olarak, bir özel durum oluşturabilecek bir veya daha fazla deyimi kapsamak için bir **TRY** bloğu kullanın.

Bir **throw** ifadesi, bir **TRY** bloğunda olağanüstü bir koşulun (genellikle bir hata) oluştuğunu bildirir. Bir **throw** ifadesinin işleneni olarak herhangi bir türdeki bir nesneyi kullanabilirsiniz. Genellikle, bu nesne, hata hakkında bilgi iletmek için kullanılır. Çoğu durumda, [std:: Exception](../standard-library/exception-class.md) sınıfını veya standart kitaplıkta tanımlı türetilmiş sınıflardan birini kullanmanızı öneririz. Bunlardan biri uygun değilse, kendi özel durum sınıfınızı `std::exception`türetmenizi öneririz.

Oluşturulan özel durumları işlemek için bir **TRY** bloğunun hemen sonrasında bir veya daha fazla **catch** bloğu uygulayın. Her **catch** bloğu işleyebileceği özel durum türünü belirtir.

Bu örnekte bir **TRY** bloğu ve işleyicileri gösterilmektedir. `GetNetworkResource()` bir ağ bağlantısı üzerinden veri edindiğini ve iki özel durum türünün `std::exception`türetilen Kullanıcı tanımlı sınıflar olduğunu varsayalım. Özel durumların **catch** deyimindeki **const** başvurusuyla yakalandığına dikkat edin. Özel durumları değere göre oluşturmanız ve sabit başvuruya göre yakalamanız önerilir.

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

**TRY** yan tümcesinden sonraki kod, kodun korunan bölümüdür. **Throw** ifadesi (yani, bir özel durum *) oluşturur.* **Catch** yan tümcesinden sonraki kod bloğu özel durum işleyicisidir. Bu, **throw** ve **catch** ifadelerindeki türler uyumluysa oluşturulan özel durumu *yakalayan* işleyicidir. **Catch** bloklarındaki tür eşlemeyi yöneten kuralların listesi için bkz. [catch blokları nasıl değerlendirilir](../cpp/how-catch-blocks-are-evaluated-cpp.md). **Catch** ifadesinde bir tür yerine bir üç nokta (...) belirtilmemişse, **catch** bloğu her bir özel durum türünü işler. [/EHa](../build/reference/eh-exception-handling-model.md) seçeneğiyle derlerken, bunlar C yapısal özel durumlar ve sistem tarafından oluşturulan ya da bellek koruma, sıfıra bölme ve kayan nokta ihlalleri gibi zaman uyumsuz özel durumlar içerebilir. **Catch** blokları eşleşen bir tür bulmak için Program sırasıyla işlendiği için, üç nokta işleyicisi ilişkili **TRY** bloğunun son işleyicisi olmalıdır. `catch(...)` dikkatle kullanın; catch bloğu yakalanan özel özel durumu nasıl işleyeceğinizi bilmediği takdirde bir programın devam etmesine izin vermeyin. Genellikle, bir `catch(...)` bloğu hataları günlüğe kaydetmek ve program yürütme durdurulmadan önce özel temizleme gerçekleştirmek için kullanılır.

İşleneni olmayan bir **throw** ifadesi, işlenmekte olan özel durumu yeniden oluşturur. Bu, özgün özel durumun polimorfik türü bilgilerini koruduğundan, özel durum yeniden oluşturulduğunda bu biçim önerilir. Böyle bir ifade yalnızca bir **catch** işleyicisinde veya bir **catch** işleyicisinden çağrılan bir işlevde kullanılmalıdır. Yeniden oluşturulmuş özel durum nesnesi bir kopya değil, özgün özel durum nesnesidir.

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

[Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[İşlenilmeyen C++ Özel Durumları](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)