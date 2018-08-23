---
title: Yazılım özel durumlarını oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b4469d7d53a7374f62e0ec232a7836e80ab75d8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606421"
---
# <a name="raising-software-exceptions"></a>Yazılım Özel Durumlarını Oluşturma
Sistem tarafından program hataların en yaygın kaynaklardan bazılarını özel durumlar olarak işaretlenmeyen. Örneğin, bir bellek bloğunu ayırmaya çalışır, ancak yeterli bellek çalışma zamanı veya API işlevi bir özel durum oluşturmaz ancak bir hata kodu döndürür.  
  
 Herhangi bir koşul bir özel kodunuzda bu koşulu algılayarak ve çağırarak raporlama ancak davranabileceğiniz [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) işlevi. Bu şekilde hataları işaretlemesini tarafından yapılandırılmış özel durum işleme herhangi bir türden çalışma zamanı hatası avantajları getirebilirsiniz.  
  
 Yapılandırılmış özel durum işleme hatalarla kullanmak için:  
  
-   Olay için kendi özel kodunuzu tanımlayın.  
  
-   Çağrı `RaiseException` algılamak ne zaman bir sorun.  
  
-   Tanımladığınız özel durum kodunu test etmek için özel durum işleme filtrelerini kullanın.  
  
 \<Wınerror > özel durum kodları için biçim dosyasını gösterir. Çakışan bir kod mevcut bir özel durum kodu ile tanımlamazsanız emin olmak için üçüncü en anlamlı biti 1 olarak ayarlayın. Aşağıdaki tabloda gösterildiği gibi dört en önemli bitleri ayarlanması gerekir.  
  
|Bits|Önerilen ikili ayarı|Açıklama|  
|----------|--------------------------------|-----------------|  
|31-30|11|Bu iki bit kod temel durumunu açıklayan: 11 hatası, 00 = = başarılı, 01 = bilgilendirici, 10 = uyarı.|  
|29|1.|İstemci bit. Kullanıcı tanımlı kodları için 1 olarak ayarlayın.|  
|28|0|Ayrılmış bit. (0 olarak ayarlanmış olarak bırakın.)|  
  
 İsterseniz, "error" ayarı çoğu özel durumlar için uygun olsa da, ilk iki bit 11 dışındaki bir ayar için ikili ayarlayabilirsiniz. Anımsanması gereken önemli şey BITS 29 ile 28 önceki tabloda gösterilen şekilde ayarlamaktır.  
  
 Ortaya çıkan hata kodu, bu nedenle en yüksek dört onaltılık E'ye bitler olmalıdır Örneğin, şu tanımlamalardan herhangi bir Windows özel durum kodları ile çakışmayan özel durum kodları tanımlayın. (Ancak kodlara üçüncü parti DLL'ler tarafından kullanılan denetlemek ihtiyacınız olabilir.)  
  
```cpp 
#define STATUS_INSUFFICIENT_MEM       0xE0000001  
#define STATUS_FILE_BAD_FORMAT        0xE0000002  
```  
  
 Bir özel durum kodu tanımladıktan sonra bir özel durum oluşturmak için kullanabilirsiniz. Örneğin, aşağıdaki harekete geçirirse kod `STATUS_INSUFFICIENT_MEM` yanıt olarak bir bellek ayırma sorun özel durum:  
  
```cpp 
lpstr = _malloc( nBufferSize );  
if (lpstr == NULL)  
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);  
```  
  
 Yalnızca bir özel durum yükseltmek istiyorsanız, en son üç parametre 0 olarak ayarlayabilirsiniz. Son üç parametre ek bilgi geçirmek için kullanışlıdır ve bayrak ayarı işleyicileri yürütme devam etmesini engeller. Bkz: [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) daha fazla bilgi için Windows SDK'sında işlev.  
  
 Özel durum işleme filtrelerinizi tanımladınız kodlarını sonra test edebilirsiniz. Örneğin:  
  
```cpp 
__try {  
    ...  
}  
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||  
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)