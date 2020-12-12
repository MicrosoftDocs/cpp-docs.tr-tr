---
description: 'Hakkında daha fazla bilgi edinin: _CrtIsMemoryBlock'
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
api_name:
- _CrtIsMemoryBlock
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
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: 81a4b515461a45f566f95728180013408ccda43a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319722"
---
# <a name="_crtismemoryblock"></a>_CrtIsMemoryBlock

Belirtilen bir bellek bloğunun yerel yığında olduğunu ve geçerli bir hata ayıklama yığını blok türü tanımlayıcısına sahip olduğunu doğrular (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Doğrulanacak bellek bloğunun başlangıcına yönelik işaretçi.

*boyutla*<br/>
Belirtilen bloğun boyutu (bayt).

*requestNumber*<br/>
Bloğun veya **null** ayırma numarası işaretçisi.

*filename*<br/>
Bloğu veya **null değerini** isteyen kaynak dosyanın adı işaretçisi.

*onayın*<br/>
Kaynak dosyadaki satır numarası işaretçisi veya **null**.

## <a name="return-value"></a>Dönüş Değeri

**_CrtIsMemoryBlock** , belirtilen bellek bloğu yerel yığında bulunuyorsa ve geçerli bir hata ayıklama yığın blok türü tanımlayıcısına sahipse **true** değerini döndürür; Aksi takdirde, işlev **false** döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtIsMemoryBlock** işlevi, belirtilen bir bellek bloğunun uygulamanın yerel yığınında bulunduğunu ve geçerli bir blok türü tanımlayıcısına sahip olduğunu doğrular. Bu işlev, nesne ayırma sıra numarasını ve bellek bloğu ayırmanın ilk olarak istediği kaynak dosya adı/satır numarasını almak için de kullanılabilir. *RequestNumber*, *filename* veya *onayın* parametreleri için **null** olmayan değerler geçirmek **_CrtIsMemoryBlock** , yerel yığında blok bulursa, bu parametreleri bellek bloğunun hata ayıklama üstbilgisindeki değerlere ayarlamaya neden olur. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtIsMemoryBlock** çağrıları ön işleme sırasında kaldırılır.

**_CrtIsMemoryBlock** başarısız olursa, **yanlış** döndürür ve çıkış parametreleri varsayılan değerlere başlatılır: *requestNumber* ve **LineNumber** değeri 0 olarak ayarlanır ve *filename* **null** olarak ayarlanır.

Bu işlev **true** veya **false** döndürdüğünden, basit bir hata ayıklama hata işleme mekanizması oluşturmak için [_assert](assert-asserte-assert-expr-macros.md) makrolarından birine geçirilebilir. Aşağıdaki örnek, belirtilen adres yerel yığında bulunmuyorsa bir onaylama hatasına neden olur:

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

**_CrtIsMemoryBlock** diğer hata ayıklama işlevleri ve makroları ile nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. about [Macros](/visualstudio/debugger/macros-for-reporting). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

[_CrtIsValidHeapPointer](crtisvalidheappointer.md) konusunun örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
