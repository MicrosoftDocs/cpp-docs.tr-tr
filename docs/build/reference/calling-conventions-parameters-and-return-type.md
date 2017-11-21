---
title: "Çağırma kuralları, parametreler ve dönüş türü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bdaf30655808d5a43f6866039cc93a3833896921
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="calling-conventions-parameters-and-return-type"></a>Çağırma Kuralları, Parametreler ve Dönüş Türü
Yardımcı yordamı 's prototip aşağıdaki gibidir:  
  
```  
FARPROC WINAPI __delayLoadHelper2(   
   PCImgDelayDescr pidd,  
   FARPROC * ppfnIATEntry  
);  
```  
  
 burada:  
  
 `pidd`  
 A `const` işaretçi bir `ImgDelayDescr` (delayimp.h bakın) içeren çeşitli alma ile ilgili veriler, bağlama bilgileri için bir zaman damgası ve tanımlayıcısı içerik hakkında daha fazla bilgi sağlayan öznitelikler setinin bir uzaklık. Şu anda yalnızca tek bir özniteliği var. `dlattrRva`, tanımlayıcısındaki adreslerinin göreli sanal adresleri (aksine sanal adresler) olduğunu gösterir.  
  
 Tanımı için `PCImgDelayDescr` yapısı için bkz: [yapı ve sabit tanımları](../../build/reference/structure-and-constant-definitions.md).  
  
 `ppfnIATEntry`  
 Gecikme yükü yuvasında gösteren bir işaretçi adres tablosunu içeri aktarılan işlevi adresi ile güncelleştirilmesi (IAT) içeri aktarın. Bu konuma dönmeye edeceksiniz aynı değeri depolamak yardımcı yordamı gerekir.  
  
## <a name="expected-return-values"></a>Beklenen dönüş değerleri  
 İşlev başarılı olursa, içeri aktarılan işlevin adresini döndürür.  
  
 İşlev başarısız olursa, bir özel durum oluşturur ve 0 döndürür. Üç tür özel durumlar yükseltilebilir:  
  
-   Olur geçersiz bir parametre öznitelikleri `pidd` doğru belirtildiğinden değil.  
  
-   `LoadLibrary`belirtilen DLL üzerinde başarısız oldu.  
  
-   Hata `GetProcAddress`.  
  
 Bu özel durumları işlemek için sizin sorumluluğunuzdadır değil.  
  
## <a name="remarks"></a>Açıklamalar  
 Yardımcı işlevi için arama kuralı `__stdcall`. Döndürülen değerin türü ilgili, olmadığından FARPROC kullanılır. Bu işlev C bağlantı sahiptir.  
  
 Bir bildirim kancası kullanılacak Yardımcısı alışkanlık istemediğiniz sürece Gecikmeli Yükleme Yardımcısı dönüş değerini geçirilen işlev işaretçisi konumda depolanması gerekir. Bu durumda, kodunuzu döndürmek için uygun işlev işaretçisi bulmak için sorumludur. Bağlayıcı sonra oluşturur dönüştürücü kod alma gerçek hedef olarak bu dönüş değerini alır ve doğrudan atlar.  
  
## <a name="sample"></a>Örnek  
 Aşağıdaki kod basit kanca işlevinin nasıl uygulandığını gösterir.  
  
```  
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)  
{  
    switch (dliNotify) {  
        case dliStartProcessing :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return a pointer to a FARPROC helper function  
            // that will be used instead, thereby bypassing the rest   
            // of the helper.  
  
            break;  
  
        case dliNotePreLoadLibrary :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return your own HMODULE to be used by the   
            // helper instead of having it call LoadLibrary itself.  
  
            break;  
  
        case dliNotePreGetProcAddress :  
  
            // If you want to return control to the helper, return 0.  
            // If you choose you may supply your own FARPROC function   
            // address and bypass the helper's call to GetProcAddress.  
  
            break;  
  
        case dliFailLoadLib :   
  
            // LoadLibrary failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_MOD_NOT_FOUND) and exit.  
            // If you want to handle the failure by loading an alternate   
            // DLL (for example), then return the HMODULE for   
            // the alternate DLL. The helper will continue execution with   
            // this alternate DLL and attempt to find the  
            // requested entrypoint via GetProcAddress.  
  
            break;  
  
        case dliFailGetProc :  
  
            // GetProcAddress failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_PROC_NOT_FOUND) and exit.  
            // If you choose you may handle the failure by returning   
            // an alternate FARPROC function address.  
  
            break;  
  
        case dliNoteEndProcessing :   
  
            // This notification is called after all processing is done.   
            // There is no opportunity for modifying the helper's behavior  
            // at this point except by longjmp()/throw()/RaiseException.   
            // No return value is processed.  
  
            break;  
  
        default :  
  
            return NULL;  
    }  
  
    return NULL;  
}  
  
/*   
and then at global scope somewhere  
PfnDliHook __pfnDliNotifyHook2 = delayHook;  
*/  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yardımcı işlevini anlama](../../build/reference/understanding-the-helper-function.md)