---
title: _CrtSetAllocHook
ms.date: 11/04/2016
apiname:
- _CrtSetAllocHook
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
f1_keywords:
- _CrtSetAllocHook
- CrtSetAllocHook
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: cfa466ec4bce6034c15a627ccab4ee4bb0ef8f5b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533685"
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook

Bir istemci tanımlı ayırma işlevi C çalışma zamanı hata ayıklama bellek ayırma işlemine (yalnızca hata ayıklama sürümü) takma tarafından yükler.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>Parametreler

*allocHook*<br/>
C çalışma zamanı hata ayıklama bellek ayırma işlemine yeteneklerinizi yeni istemci tarafından tanımlanan ayırma işlevi.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış ayırma kanca işlevini döndürür veya **NULL** varsa *allocHook* olduğu **NULL**.

## <a name="remarks"></a>Açıklamalar

**_CrtSetAllocHook** kendi ayırma işlevi C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemine bağlama için bir uygulama sağlar. Sonuç olarak, ayırmak için bir hata ayıklama ayırma işlevi yapılan her çağrı, yeniden kullanıma alabilmeniz veya uygulamanın kanca işlevi çağrısı bir bellek bloğu Tetikleyicileri ücretsiz. **_CrtSetAllocHook** uygulamanın uygulama yetersiz bellek durumları nasıl işlediğini test etmek için bir kolayca yönteminiz ayırma desenleri ve yükleme bilgilerini daha sonra oturum fırsatı inceleyin olanağı sağlar. analizi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetAllocHook** ön işleme sırasında kaldırılır.

**_CrtSetAllocHook** işlevi, belirtilen yeni istemci tarafından tanımlanan ayırma işlevi yükler *allocHook* ve önceden tanımlı kanca işlevini döndürür. Aşağıdaki örnek, bir istemci tanımlı atama kanca nasıl prototipli olmalıdır gösterir:

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

**AllocType** bağımsız değişkeni ayırma işlemi türünü belirtir (**_HOOK_ALLOC**, **_HOOK_REALLOC**, ve **_HOOK_FREE**), Ayırma'nın kanca işlevi çağrısı tetiklenir. Tetikleyici ayırma türü olduğunda **_HOOK_FREE**, *userData* serbest bırakılacak Bellek Blok kullanıcı veri bölümünde bir işaretçidir. Ancak, tetikleyici ayırma türü olduğunda **_HOOK_ALLOC** veya **_HOOK_REALLOC**, *userData* olduğu **NULL** bellek engelleme nedeni henüz ayrılmamış.

*boyutu* blok bayt cinsinden bellek boyutu belirtir *blockType* bellek bloğu türünü gösteren *requestNumber* bellek bloğu nesne ayırma sipariş sayısı ve kullanılabilir *filename* ve **lineNumber** tetikleme ayırma işlemi burada başlatıldı kaynak dosyası adı ve satır numarasını belirtin.

Kanca işlevini işleme tamamlandıktan sonra ana C çalışma zamanı ayırma işlemini nasıl devam edileceğini belirten bir Boole değeri döndürmelidir. Kanca işlevini olarak kanca işlevini hiçbir zaman çağırıldıktan sonra kanca işlevini döndürmelidir devam etmek için ana ayırma işlemi istediği zaman **TRUE**. Bu, özgün tetikleme ayırma işlemi yürütülecek neden olur. Kanca işlevini, bu uygulamayı kullanarak toplamak ve geçerli ayırma işlemi ya da hata ayıklama yığının durumunun müdahale etmeden sonraki analiz gerçekleştirmek amacıyla ayırma bilgilerini kaydedin.

Kanca işlevini ana ayırma işlemini tetikleme ayırma işlemi çağrıldı ve başarısız durumunda kanca işlevini döndürmelidir olarak devam istediği zaman **FALSE**. Kanca işlevini, bu uygulamayı kullanarak çok çeşitli bellek koşulları benzetimi ve yığın durumları, uygulama her durumun nasıl işlediğini test etmek için hata ayıklama.

Kanca işlevini temizlemek için geçirmek **NULL** için **_CrtSetAllocHook**.

Hakkında daha fazla bilgi için **_CrtSetAllocHook** diğer bellek yönetimi işlevleri veya kendi istemci tanımlı kanca işlevlerini yazma nasıl ile kullanılabilir [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

> [!NOTE]
> **_CrtSetAllocHook** altında desteklenmiyor **/CLR: pure**. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de kaldırıldı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_CrtSetAllocHook**, bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>
