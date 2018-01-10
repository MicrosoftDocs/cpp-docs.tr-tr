---
title: setjmp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords: setjmp
dev_langs: C++
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 845c4eaac5c9aa0c4878016061eb07e6740f12f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setjmp"></a>setjmp
Program geçerli durumunu kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int setjmp(  
   jmp_buf env   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `env`  
 Ortam depolandığı değişken.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yığın ortamını kaydetme sonra 0 döndürür. Varsa `setjmp` sonucu olarak döndürür bir `longjmp` çağrısı, döndürdüğü `value` bağımsız değişkeni `longjmp`, veya `value` bağımsız değişkeni `longjmp` 0 ' dır `setjmp` 1 döndürür. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 `setjmp` İşlevi kaydeder, daha sonra kullanarak geri yükleyebilirsiniz bir yığın ortamı `longjmp`. Birlikte kullanıldığında `setjmp` ve `longjmp` yerel olmayan yürütmek için bir yol sağlamak `goto`. Bunlar genellikle normal arama kullanmadan önce çağrılan bir yordam hata işleme veya kurtarma kodunda yürütme denetimi geçirmek için kullanılan veya kuralları döndürür.  
  
 Çağrı `setjmp` geçerli yığın ortamda kaydeder `env`. Sonraki çağrı `longjmp` kaydedilmiş ortamı geri yükler ve döndürür denetim noktası yalnızca karşılık gelen sonra `setjmp` çağırın. Denetim alma yordamı erişilebilir tüm değişkenleri (dışında yazmaç değişkenleri) sahip oldukları zaman değerlerini içeren `longjmp` çağrıldı.  
  
 Kullanmak mümkün değil `setjmp` yönetilen kod Yerelden atlamak için.  
  
 **Not** `setjmp` ve `longjmp` C++ nesne semantiği desteklemez. C++ programlarında C++ özel durum işleme mekanizması kullanın.  
  
 Daha fazla bilgi için bkz: [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`setjmp`|\<setjmp.h'ı >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_fpreset](../../c-runtime-library/reference/fpreset.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [longjmp](../../c-runtime-library/reference/longjmp.md)   
 [_setjmp3](../../c-runtime-library/setjmp3.md)