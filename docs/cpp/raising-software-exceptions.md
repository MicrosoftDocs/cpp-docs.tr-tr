---
title: Yazılım özel durumlarını oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- run-time errors, treating as exceptions
- exception handling [C++], errors as exceptions
- exceptions [C++], flagging errors as exceptions
- errors [C++], treating as exceptions
- exception handling [C++], detecting errors
- structured exception handling [C++], errors as exceptions
- exceptions [C++], software
- RaiseException function
- software exceptions [C++]
- formats [C++], exception codes
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
ms.openlocfilehash: 7c58ae2e2b6635345a162d11d2b75a9865d37751
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246401"
---
# <a name="raising-software-exceptions"></a>Yazılım özel durumlarını oluşturma

Program hatalarının en yaygın kaynaklarından bazıları sistem tarafından özel durum olarak işaretlenmez. Örneğin, bellek bloğu ayırmaya çalışırsanız, ancak yeterli bellek yoksa, çalışma zamanı veya API işlevi bir özel durum oluşturmaz, ancak bir hata kodu döndürür.

Ancak, kodunuzda söz konusu koşulu algılayıp ve sonra [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) işlevini çağırarak rapor vererek herhangi bir koşulu özel durum olarak ele alabilirsiniz. Hatalara bu şekilde bayrak koyarak, yapılandırılmış özel durum işlemenin avantajlarının her türlü çalışma zamanı hatasına getirebilirsiniz.

Yapılandırılmış özel durum işlemeyi hatalarla birlikte kullanmak için:

- Olay için kendi özel durum kodunuzu tanımlayın.

- Bir sorunu saptadığınızda `RaiseException` çağırın.

- Tanımladığınız özel durum kodunu test etmek için özel durum işleme filtrelerini kullanın.

\<Winerror. h > dosyası, özel durum kodlarının biçimini gösterir. Mevcut bir özel durum koduyla çakışan bir kod tanımlamadığınızdan emin olmak için, üçüncü en önemli biti 1 olarak ayarlayın. En önemli dört bit, aşağıdaki tabloda gösterildiği gibi ayarlanmalıdır.

|Bits|Önerilen ikili ayar|Açıklama|
|----------|--------------------------------|-----------------|
|31-30|11|Bu iki bit kodun temel durumunu Açıklama: 11 = Error, 00 = Success, 01 = bilgilendirici, 10 = Warning.|
|29|1\.|İstemci bit. Kullanıcı tanımlı kodlar için 1 olarak ayarlayın.|
|28|0|Ayrılmış bit. (0 olarak ayarlı bırakın.)|

"Hata" ayarı çok sayıda özel durum için uygun olsa da, ilk iki biti isterseniz 11 ikili dışında bir ayara ayarlayabilirsiniz. Anımsanması gereken önemli şey, önceki tabloda gösterildiği gibi BITS 29 ve 28 ' i ayarlamanıza olanak sağlar.

Sonuç olarak oluşan hata kodu, en yüksek dört bit onaltılık E olarak ayarlanmalıdır. Örneğin, aşağıdaki tanımlar herhangi bir Windows özel durum koduyla çakışmayan özel durum kodları tanımlar. (Ancak, üçüncü taraf dll 'Ler tarafından hangi kodların kullanıldığını denetlemeniz gerekebilir.)

```cpp
#define STATUS_INSUFFICIENT_MEM       0xE0000001
#define STATUS_FILE_BAD_FORMAT        0xE0000002
```

Bir özel durum kodu tanımladıktan sonra, özel durum yükseltmek için kullanabilirsiniz. Örneğin, aşağıdaki kod, bir bellek ayırma sorununa yanıt olarak `STATUS_INSUFFICIENT_MEM` özel durumunu başlatır:

```cpp
lpstr = _malloc( nBufferSize );
if (lpstr == NULL)
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);
```

Yalnızca bir özel durum yükseltmek istiyorsanız, son üç parametreyi 0 olarak ayarlayabilirsiniz. Son üç parametre ek bilgi iletmek ve işleyicilerin yürütmeye devam etmesini önleyen bir bayrak ayarlamak için faydalıdır. Daha fazla bilgi için Windows SDK [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) işlevine bakın.

Özel durum işleme filtrelerinde, daha sonra tanımladığınız kodları test edebilirsiniz. Örneğin:

```cpp
__try {
    ...
}
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )
```

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış özel durum işleme (CC++/)](../cpp/structured-exception-handling-c-cpp.md)