---
title: Çağırma Kuralları, Parametreler ve Dönüş Türü
ms.date: 02/13/2019
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: a85825eb49b1f8faab7862e902b226c1c1fb6d58
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812973"
---
# <a name="calling-conventions-parameters-and-return-type"></a>Çağırma Kuralları, Parametreler ve Dönüş Türü

Yardımcısı yordam 's prototip aşağıdaki gibidir:

```
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>Parametreler

*pidd*<br/>
A `const` işaretçi bir `ImgDelayDescr` uzaklıklarını içeri aktarma ile ilgili çeşitli veri bağlama bilgileri için bir zaman damgası ve tanımlayıcı içerik hakkında daha fazla bilgi sağlayan öznitelikler kümesi içerir. Şu anda yalnızca bir öznitelik yoktur `dlattrRva`, adresleri tanımlayıcısındaki göreli sanal adreslerine olduğunu gösterir. Daha fazla bilgi için bkz: bildirimlerinde *delayimp.h*.

Tanımını `PCImgDelayDescr` yapısı için bkz: [yapı ve sabit tanımları](structure-and-constant-definitions.md).

*ppfnIATEntry*<br/>
İçeri aktarılan bir işlevin adresini ile güncelleştirilen gecikme yük içeri aktarma adres tablosunda (IAT) yuva için bir işaretçi. Bu konuma döndürdüğü değerin depolanacağı Yardımcısı yordamı gerekir.

## <a name="expected-return-values"></a>Beklenen dönüş değerleri

İşlev başarılı olursa, içeri aktarılan bir işlevin adresini döndürür.

İşlev başarısız olursa bir özel durum oluşturur ve 0 döndürür. Üç tür özel durumlar yükseltilebilir:

- Olur geçersiz bir parametre öznitelikleri `pidd` doğru belirtildiğinden değildir.

- `LoadLibrary` belirtilen DLL üzerinde başarısız oldu.

- Hata `GetProcAddress`.

Bu özel durumları işlemek için sizin sorumluluğunuzdur.

## <a name="remarks"></a>Açıklamalar

Yardımcı işlevini çağırma kuralının olduğunu `__stdcall`. Bu nedenle FARPROC kullanılır dönüş değeri türünü ilgili değildir. Bu işlev, C bağlantısına sahip.

Bir bildirim kancası kullanılan yardımcı alışkanlık istemediğiniz sürece gecikme yük yardımcı dönüş değerini geçirilen işlev işaretçisi konumda depolanması gerekir. Bu durumda, geri dönmek için uygun bir işlev işaretçisi bulmak için kodunuzu sorumludur. Ardından bağlayıcı oluşturur dönüştürücü kod gerçek içeri aktarma hedefi olarak, dönüş değeri alır ve ona doğrudan atlar.

## <a name="sample"></a>Örnek

Aşağıdaki kod, bir basit kanca işlevini uygulamak gösterilmektedir.

```C
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
const PfnDliHook __pfnDliNotifyHook2 = delayHook;
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[Yardımcı İşlevini Anlama](understanding-the-helper-function.md)