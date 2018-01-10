---
title: "Yazılım özel durumlarını oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
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
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98601b9d4293417d03dcdcc96b2ae0bb54defdc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="raising-software-exceptions"></a>Yazılım Özel Durumlarını Oluşturma
Bazı program hataların en yaygın kaynakları özel durumlar olarak sistem tarafından işaretlenmeyen. Örneğin, bir bellek bloğu ayırma girişimi, ancak yeterli bellek yok, çalışma zamanı veya API işlevi bir özel durum oluşturmaz ancak bir hata kodu döndürür.  
  
 Herhangi bir koşul özel durum kodunuzda bu koşul algılama ve çağırarak raporlama tarafından ancak davranabilirsiniz [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) işlevi. Bu şekilde hataları işaretlemesini tarafından yapılandırılmış özel durum işleme her türlü çalışma zamanı hatası avantajları kullanıma sunabilirsiniz.  
  
 Yapılandırılmış özel durum işleme hataları olan kullanmak için:  
  
-   Olayı için kendi özel durum kodu tanımlayın.  
  
-   Çağrı **RaiseException** algılamak ne zaman bir sorun.  
  
-   Tanımladığınız özel durum kodu için test etmek için özel durum işleme filtreleri kullanın.  
  
 WINERROR. H dosyasını özel durum kodları biçimi gösterir. Çakışan bir kod var olan bir özel durum kodu belirtmiyor emin olmak için üçüncü en önemli biti 1 olarak ayarlayın. Aşağıdaki tabloda gösterildiği gibi dört en önemli BITS ayarlanması gerekir.  
  
|Bits|Önerilen ikili ayarı|Açıklama|  
|----------|--------------------------------|-----------------|  
|31-30|11|Bu iki bit kodu temel durumunu açıklar: 11 = hata, 00 = success, 01 = bilgilendirme, 10 uyarı =.|  
|29|1.|İstemci bit. Kullanıcı tanımlı kodları için 1 olarak ayarlayın.|  
|28|0|Ayrılmış bit. (0 olarak ayarlanmış olarak bırakın.)|  
  
 İsterseniz, "error" ayarı çoğu özel durumlar için uygun olsa da, ilk iki BITS 11 dışında bir ayarı için ikili ayarlayabilirsiniz. Anımsaması önemli şey BITS 29 ve 28 önceki tabloda gösterilen ayarlamaktır.  
  
 Sonuçta elde edilen hata kodu dolayısıyla en yüksek dört onaltılık E'ye bitler olması gerekir Örneğin, aşağıdaki tanımları çakışmasını özel durum kodları tüm Windows özel durum kodları ile tanımlayın. (Ancak, kodlara üçüncü taraf DLL'leri tarafından kullanılan denetlemek ihtiyacınız olabilir.)  
  
```  
#define STATUS_INSUFFICIENT_MEM       0xE0000001  
#define STATUS_FILE_BAD_FORMAT        0xE0000002  
```  
  
 Bir özel durum kodu tanımladıktan sonra bir özel durum oluşturmak için kullanabilirsiniz. Örneğin, aşağıdaki kod yanıt olarak bir bellek ayırma sorunu STATUS_INSUFFICIENT_MEM özel durum oluşturur:  
  
```  
lpstr = _malloc( nBufferSize );  
if (lpstr == NULL)  
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);  
```  
  
 Yalnızca bir özel durum yükseltmek istiyorsanız, en son üç parametre 0 olarak ayarlayın. Üç son parametre ek bilgi geçirmek için kullanışlı olan ve işleyicileri yürütme devam etmesini engelleyen bir bayrak ayarı. Bkz: [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) işlevi [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] daha fazla bilgi için.  
  
 Özel durum işleme filtrelerinizi tanımladığınız kodlarını sonra test edebilirsiniz. Örneğin:  
  
```  
__try {  
    ...  
}  
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||  
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir özel durum işleyicisi yazma](../cpp/writing-an-exception-handler.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)