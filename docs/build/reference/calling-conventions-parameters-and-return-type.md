---
title: Çağırma Kuralları, Parametreler ve Dönüş Türü
ms.date: 02/13/2019
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
ms.openlocfilehash: 8813bab0cb55aa57792d0031433d96eefb095da4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223921"
---
# <a name="calling-conventions-parameters-and-return-type"></a>Çağırma Kuralları, Parametreler ve Dönüş Türü

Yardımcı yordamın prototipi şunlardır:

```
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

### <a name="parameters"></a>Parametreler

*pidd*<br/>
**`const`** `ImgDelayDescr` İçeri aktarma ile ilgili çeşitli verileri, bağlama bilgileri için zaman damgasını ve tanımlayıcı içeriği hakkında daha fazla bilgi sağlayan bir öznitelik kümesini içeren bir işaretçisi. Şu anda, `dlattrRva` Tanımlayıcıdaki adreslerin göreli sanal adresler olduğunu gösteren yalnızca bir öznitelik vardır. Daha fazla bilgi için, *delayimp. h*içindeki bildirimlere bakın.

Yapının tanımı için `PCImgDelayDescr` bkz. [Yapı ve sabit tanımlar](structure-and-constant-definitions.md).

*ppfnIATEntry*<br/>
Alınan işlevin adresiyle güncelleştirilmiş gecikmeli yük içeri aktarma adres tablosunda (ıAT) yuva işaretçisi. Yardımcı yordamının bu konuma döndürdüğü değeri aynı şekilde depolaması gerekir.

## <a name="expected-return-values"></a>Beklenen dönüş değerleri

İşlev başarılı olursa, içeri aktarılan işlevin adresini döndürür.

İşlev başarısız olursa, bir özel durum oluşturur ve 0 döndürür. Üç tür özel durum oluşturulabilir:

- ' Deki öznitelikler doğru belirtilmediyse, geçersiz parametre `pidd` .

- `LoadLibrary`Belirtilen DLL 'de başarısız oldu.

- Hata `GetProcAddress` .

Bu özel durumları işlemek sizin sorumluluğunuzdadır.

## <a name="remarks"></a>Açıklamalar

Yardımcı işlevi için çağırma kuralı **`__stdcall`** . Dönüş değerinin türü ilgili değildir, bu nedenle FARPROC kullanılır. Bu işlevin C bağlantısı vardır.

Yardım yordamınızın bildirim kancası olarak kullanılmasını istemediğiniz sürece, gecikme yükü Yardımcısı 'nın dönüş değeri, geçirilen işlev işaretçisi konumunda depolanmalıdır. Bu durumda, döndürülecek uygun işlev işaretçisini bulmaktan kodunuz sorumludur. Bağlayıcının oluşturduğu dönüştürücü kodu, bu dönüş değerini içeri aktarmanın gerçek hedefi olarak alır ve doğrudan ona atlar.

## <a name="sample"></a>Örnek

Aşağıdaki kod, bir basit kanca işlevinin nasıl uygulanacağını gösterir.

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

[Yardımcı Işlevini anlama](understanding-the-helper-function.md)
