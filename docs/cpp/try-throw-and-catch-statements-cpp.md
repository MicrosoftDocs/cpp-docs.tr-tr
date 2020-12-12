---
description: 'Daha fazla bilgi edinin: TRY, throw ve catch deyimleri (C++)'
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
ms.openlocfilehash: 78dc76a9db5a4b1b6b8c23d1807b683d0dbae969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186434"
---
# <a name="try-throw-and-catch-statements-c"></a>try, throw ve catch Deyimleri (C++)

C++ ' da özel durum işlemeyi uygulamak için, **`try`** **`throw`** ve ifadelerini kullanırsınız **`catch`** .

İlk olarak, **`try`** özel durum oluşturabilecek bir veya daha fazla deyimi kapsamak için bir blok kullanın.

Bir **`throw`** ifade, bir blok içinde olağanüstü bir koşulun (genellikle bir hata) oluştuğunu bildirir **`try`** . Bir ifadenin işleneni olarak herhangi bir türdeki bir nesneyi kullanabilirsiniz **`throw`** . Genellikle, bu nesne, hata hakkında bilgi iletmek için kullanılır. Çoğu durumda, [std:: Exception](../standard-library/exception-class.md) sınıfını veya standart kitaplıkta tanımlı türetilmiş sınıflardan birini kullanmanızı öneririz. Bunlardan biri uygun değilse, kendi özel durum sınıfınızı ' den türetmenizi öneririz  `std::exception` .

Oluşturulan özel durumları işlemek için, bir bloğu izleyen bir veya daha fazla **`catch`** blok uygulayın **`try`** . Her **`catch`** blok işleyebileceği özel durum türünü belirtir.

Bu örnekte bir **`try`** blok ve işleyicileri gösterilmektedir. `GetNetworkResource()`Verilerin bir ağ bağlantısı üzerinden elde olduğunu ve iki özel durum türünün ' den türetilen Kullanıcı tanımlı sınıflar olduğunu varsayın `std::exception` . Özel durumların, deyimindeki başvuruya göre yakalandığına dikkat edin **`const`** **`catch`** . Özel durumları değere göre oluşturmanız ve sabit başvuruya göre yakalamanız önerilir.

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

Yan tümcesinden sonraki kod, **`try`** kodun korunan bölümüdür. İfade (yani **`throw`** , bir özel durum) *oluşturur*. Yan tümcesinden sonraki kod bloğu **`catch`** özel durum işleyicisidir. Bu,  **`throw`** ve ifadelerindeki türler uyumluysa oluşturulan özel durumu yakalayan işleyicidir **`catch`** . Bloklardaki tür eşlemeyi yöneten kuralların listesi için **`catch`** bkz. [catch blokları nasıl değerlendirilir](../cpp/how-catch-blocks-are-evaluated-cpp.md). **`catch`** İfade bir tür yerine üç nokta (...) belirtiyorsa, **`catch`** blok her bir özel durum türünü işler. [/EHa](../build/reference/eh-exception-handling-model.md) seçeneğiyle derlerken, bunlar C yapısal özel durumlar ve sistem tarafından oluşturulan ya da bellek koruma, sıfıra bölme ve kayan nokta ihlalleri gibi zaman uyumsuz özel durumlar içerebilir. **`catch`** Blok, eşleşen bir tür bulmak için Program sırasıyla işlendiği için, üç nokta işleyicisi ilişkili blok için son işleyici olmalıdır **`try`** . `catch(...)`Dikkatli kullanın; catch bloğu yakalanan özel özel durumu nasıl işleyeceğinizi bilmediği takdirde bir programın devam etmesine izin vermeyin. Genellikle bir `catch(...)` blok, hataları günlüğe kaydetmek ve program yürütmesi durdurulmadan önce özel temizleme gerçekleştirmek için kullanılır.

İşleneni olmayan bir **`throw`** ifade, işlenmekte olan özel durumu yeniden oluşturur. Bu, özgün özel durumun polimorfik türü bilgilerini koruduğundan, özel durum yeniden oluşturulduğunda bu biçim önerilir. Böyle bir ifade yalnızca bir **`catch`** işleyicide veya bir işleyiciden çağrılan bir işlevde kullanılmalıdır **`catch`** . Yeniden oluşturulmuş özel durum nesnesi bir kopya değil, özgün özel durum nesnesidir.

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

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[İşlenmeyen C++ özel durumları](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
