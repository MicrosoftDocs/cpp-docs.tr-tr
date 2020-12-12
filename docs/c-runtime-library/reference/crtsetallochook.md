---
description: 'Hakkında daha fazla bilgi edinin: _CrtSetAllocHook'
title: _CrtSetAllocHook
ms.date: 11/04/2016
api_name:
- _CrtSetAllocHook
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtSetAllocHook
- CrtSetAllocHook
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: a60024eff510f457cfc16f4afa3035efef37cca4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319670"
---
# <a name="_crtsetallochook"></a>_CrtSetAllocHook

, C çalışma zamanı hata ayıklama belleği ayırma işlemine (yalnızca hata ayıklama sürümü) bağlanarak istemci tanımlı bir ayırma işlevi kurar.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>Parametreler

*allocHook*<br/>
C çalışma zamanı hata ayıklama belleği ayırma işlemine bağlamak için yeni istemci tanımlı ayırma işlevi.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış ayırma kanca işlevini veya *Allowchook* **null** ise **null** değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtSetAllocHook** , bir uygulamanın kendi ayırma işlevini C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemine erişmesini sağlar. Sonuç olarak, bir bellek bloğunu ayırmak, yeniden ayırmak veya serbest bırakmak için bir hata ayıklama ayırma işlevine yapılan her çağrı, uygulamanın kanca işlevine yönelik bir çağrı tetikler. **_CrtSetAllocHook** , uygulamanın yetersiz bellek durumlarını nasıl işlediğini, ayırma düzenlerini İnceleme yeteneğini ve daha sonra analiz için ayırma bilgilerini günlüğe kaydetme fırsatını test etmek için kolay bir yöntem sağlar. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtSetAllocHook** çağrıları ön işleme sırasında kaldırılır.

**_CrtSetAllocHook** Işlevi, *allocHook* içinde belirtilen yeni istemci tanımlı ayırma işlevini yüklüyor ve önceden tanımlanmış kanca işlevini döndürüyor. Aşağıdaki örnek, istemci tanımlı bir ayırma kancasını prototip olarak yazmanız gerektiğini göstermektedir:

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

**AllocType** bağımsız değişkeni, ayırmanın kanca işlevine çağrıyı tetikleyen ayırma işleminin türünü (**_HOOK_ALLOC**, **_HOOK_REALLOC** ve **_HOOK_FREE**) belirtir. Tetikleme ayırma türü **_HOOK_FREE** olduğunda, *UserData* , bellek bloğunun serbest olması için Kullanıcı verileri bölümünün bir işaretçisidir. Ancak, tetikleme ayırma türü **_HOOK_ALLOC** veya **_HOOK_REALLOC** olduğunda, bellek bloğu henüz ayrılmadığından *UserData* **null** olur.

*Boyut* , bellek bloğunun boyutunu bayt cinsinden belirtir, *blok türü* bellek bloğunun türünü, *requestNumber* , bellek bloğunun nesne ayırma sırası numarasını gösterir ve varsa, *Dosya* adı ve **linumarası** , tetikleme ayırma işleminin başlatıldığı kaynak dosya adını ve satır numarasını belirtir.

Kanca işlevinin işlemeyi tamamladıktan sonra, ana C çalışma zamanı ayırma işlemini nasıl devam edebileceğinizi belirten bir Boole değeri döndürmelidir. Kanca işlevi, kanca işlevi hiç çağrılmadıysa, ana ayırma işleminin devam etmesini istediğinde, kanca işlevi **true** döndürmelidir. Bu, özgün tetikleme ayırma işleminin yürütülmesini sağlar. Bu uygulamayı kullanarak, kanca işlevi, geçerli ayırma işlemini veya hata ayıklama yığınının durumunu etkilemeden, daha sonra analiz için ayırma bilgilerini toplayıp kaydedebilir.

Kanca işlevi, tetikleme ayırma işlemi çağrılıp başarısız olduğu gibi ana ayırma işleminin devam etmesini istediğinde, kanca işlevi **false** döndürmelidir. Bu uygulamayı kullanarak, kanca işlevi, uygulamanın her durumu nasıl işlediğini sınamak için çok çeşitli bellek koşullarını ve hata ayıklama yığın durumlarını taklit edebilir.

Kanca işlevini temizlemek için **_CrtSetAllocHook** **null** geçirin.

**_CrtSetAllocHook** diğer bellek yönetimi işlevleri ile nasıl kullanılabileceği veya kendi istemci tanımlı kanca işlevlerinizi nasıl yazacağınız hakkında daha fazla bilgi için bkz. [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> **_CrtSetAllocHook** **/clr: Pure** altında desteklenmez. **/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de kaldırılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_CrtSetAllocHook** kullanmanın bir örneği için bkz. [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>
